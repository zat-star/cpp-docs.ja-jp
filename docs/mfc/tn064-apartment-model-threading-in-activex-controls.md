---
title: "テクニカル ノート 64: ActiveX コントロールにおけるアパートメント モデルのスレッド処理 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.controls.activex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アパートメント モデルのスレッド化"
  - "コンテナー [C++], マルチスレッド"
  - "マルチスレッド コンテナー"
  - "OLE コントロール, コンテナー サポート"
  - "TN064"
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 64: ActiveX コントロールにおけるアパートメント モデルのスレッド処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このテクニカル ノートは、ActiveX コントロールのアパートメント モデルのスレッドを有効にする方法について説明します。  アパートメント モデルのスレッドが Visual C\+\+ Version 4.2 以降だけでサポートされることに注意してください。  
  
## アパートメント モデルのスレッドは何ですか。  
 アパートメント モデルはサポートの埋め込みオブジェクトのアプローチ、マルチスレッド アプリケーション コンテナー内の ActiveX コントロールなどです。  アプリケーションで複数のスレッドを持つ場合もありますが、埋め込みオブジェクトのインスタンスごとに 1 文字の「アパートメントに割り当てられ」、1 のスレッドだけで実行されます。  つまり、コントロール インスタンスへの呼び出しはすべて、同じスレッドで発生します。  
  
 ただし、コントロールの同じ型の異なるインスタンスは異なるアパートメント内に割り当てられている場合があります。  したがって、コントロールの複数のインスタンスが共通のデータ \(たとえば、静的またはグローバル データ\) を共有する場合、この共有データへのアクセス、クリティカル セクションなどの同期オブジェクトによって保護する必要があります。  
  
 アパートメント スレッド モデルの完全な詳細については、*OLE Programmer's Reference*の [プロセスおよびスレッド](http://msdn.microsoft.com/library/windows/desktop/ms684841) を参照してください。  
  
## 理由アパートメント モデルのスレッドをサポートします。  
 アパートメント モデルのスレッドをサポートするコントロールは、アパートメント モデルをサポートするマルチスレッド コンテナー アプリケーションで使用できます。  アパートメント モデルのスレッドを有効にしない場合は、コントロールで使用できるコンテナーの可能性を制限します。  
  
 アパートメント モデルのスレッドを有効にすると、特ににほとんど共有データがある場合、ほとんどのコントロールに簡単です。  
  
## 共有データの保護  
 コントロールが共有データ、静的メンバー変数など、それへのアクセスに使用するデータは、クリティカル セクションに複数のスレッドが同時にデータを変更できないように保護する必要があります。  クリティカル セクションをこのように設定すると、コントロール クラスの `CCriticalSection` クラスの静的メンバー変数を宣言します。  `Lock` を使用してこのクリティカル セクション オブジェクトの **ロック解除** のメンバー関数は、どこにでもコード共有データにアクセスします。  
  
 検討のすべてのインスタンスで共有される文字列を保持する必要があります。たとえば、コントロール クラス。  この文字列は、クリティカル セクション変数である場合、保護されたな静的メンバーに保持できます。  コントロールのクラス宣言があります。:  
  
```  
class CSampleCtrl : public COleControl  
{  
    ...  
    static CString _strShared;  
    static CCriticalSection _critSect;  
};  
```  
  
 クラスの実装は、これらの変数の定義が含まれている T:  
  
```  
int CString CSampleCtrl::_strShared;  
CCriticalSection CSampleCtrl::_critSect;  
```  
  
 `_strShared` の静的メンバーにアクセスするには、クリティカル セクションを保護することがあります:  
  
```  
void CSampleCtrl::SomeMethod()  
{  
    _critSect.Lock();  
    if (_strShared.Empty())  
        _strShared = "<text>";  
    _critSect.Unlock();  
    ...  
}  
```  
  
## アパートメント モデルに対応するコントロールの登録  
 アパートメント モデルのスレッドをサポートするコントロールは *クラスの*id\\ の**InprocServer32** キーの下のクラス ID のレジストリ エントリの「アパートメント」の値と名前付きの値「ThreadingModel」を追加することで、レジストリでこの機能を示す必要があります。  このキーを自動的にコントロールに登録します。`AfxOleRegisterControlClass`に 6 番目の `afxRegApartmentThreading` フラグを渡します。:  
  
```  
BOOL CSampleCtrl::CSampleCtrlFactory::UpdateRegistry(BOOL bRegister)  
{  
    if (bRegister)  
        return AfxOleRegisterControlClass(  
            AfxGetInstanceHandle(),  
            m_clsid,  
            m_lpszProgID,  
            IDS_SAMPLE,  
            IDB_SAMPLE,  
            afxRegApartmentThreading,  
            _dwSampleOleMisc,  
            _tlid,  
            _wVerMajor,  
            _wVerMinor);  
    else  
        return AfxOleUnregisterClass(m_clsid, m_lpszProgID);  
}  
```  
  
 コントロール プロジェクトを Visual C\+\+ 4.1 以降で ControlWizard によって生成されるため、このフラグは既にコードにあります。  変更は、スレッド モデルを登録する必要はありません。  
  
 プロジェクトが ControlWizard の旧バージョンで作成された場合、既存のコードに 6 番目のパラメーターとしてブール値があります。  既存のパラメーターが TRUE の場合、`afxRegInsertable | afxRegApartmentThreading`に変更します。  既存のパラメーターが FALSE の場合、`afxRegApartmentThreading`に変更します。  
  
 コントロールがアパートメント モデルのスレッドの規則に従って、このパラメーターを `afxRegApartmentThreading` を渡す必要があります。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)