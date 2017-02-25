---
title: "テクニカル ノート 71: MFC IOleCommandTarget の実装 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IOleCommandTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IOleCommandTarget インターフェイス"
  - "TN071"
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# テクニカル ノート 71: MFC IOleCommandTarget の実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 `IOleCommandTarget` インターフェイスは、オブジェクトを使用して、ディスパッチへのコンテナーは互いを表示します。  たとえば、オブジェクトのツール バーは、**印刷\[印刷プレビュー\]**、**\[保存\]**、`New`と **\[ズーム\]** などのコマンドのボタンが含まれる場合があります。  そのようなオブジェクトが `IOleCommandTarget`をサポートするコンテナーに埋め込まれている場合は、オブジェクトはボタンを有効にし、ユーザーがクリックした方法を処理するためのコンテナーにコマンドを送信する可能性があります。  コンテナーに埋め込みオブジェクトに出力する場合は埋め込みオブジェクトの `IOleCommandTarget` インターフェイスを通じてコマンドを送信することで、この要求を作成できます。  
  
 `IOleCommandTarget` は サーバーのメソッドを呼び出すことをクライアントが使用するオートメーションに似たインターフェイスです。  ただし、`IOleCommandTarget` を使用してプログラマが `IDispatch`の `Invoke` \(通常は高いメソッドを使用する必要がないため、オートメーション インターフェイスに、呼び出しの作成のオーバーヘッドを格納します。  
  
 MFC ではアクティブ ドキュメント コンテナーがサーバーにコマンドをディスパッチするように、`IOleCommandTarget` インターフェイスは Active ドキュメント サーバーで使用されます。  Active ドキュメント サーバーの `CDocObjectServerItem`クラス、インターフェイスでは、MFC \([TN038: MFC\/OLE IUnknown の実装](../mfc/tn038-mfc-ole-iunknown-implementation.md)を参照してください `IOleCommandTarget` インターフェイスを実装する型にマップされます。  
  
 `IOleCommandTarget` は、**COleFrameHook** クラスで実装されます。  **COleFrameHook** は 埋め込み先での編集のコンテナーのフレーム ウィンドウの機能を実装する非公開のな MFC クラスです。  **COleFrameHook** は、`IOleCommandTarget` インターフェイスを実装するために MFC インターフェイス マップを使用します。  `COleDocObjectItem`への順方向の `IOleCommandTarget` の OLE コマンド\-派生の Active ドキュメント コンテナーの**COleFrameHook** の実装。  ここでは、MFC の Active ドキュメント コンテナーが含まれる Active ドキュメント サーバーからメッセージを受け取ることができます。  
  
## MFC OLE コマンド マップ  
 MFC の開発者は、MFC OLE コマンド マップを使用して `IOleCommandTarget` を利用できます。  OLE コマンド マップでは、メッセージ マップなどのコマンド マップを含むクラスのメンバー関数の OLE コマンドを割り当てるために使用する可能性があるためです。  コマンド マップの作業、場所のマクロ OLE コマンドとコマンド ID を処理したいコマンドの OLE コマンド グループを指定する OLE コマンドを受け取ったときに送信 [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) メッセージを行う。  MFC は、標準 OLE コマンドに多数の定義済みのマクロを提供します。  Microsoft Office アプリケーションで使用するために設計された標準 OLE コマンドの一覧については、docobj.h で定義されている OLECMDID の列挙体を参照してください。  
  
 OLE コマンドが OLE コマンド マップを持つ MFC アプリケーションが受け取る場合、MFC はアプリケーションの OLE コマンド マップの要求されたコマンドのコマンド ID とコマンド グループが検索されます。  一致する場合、**WM\_COMMAND** メッセージが要求されたコマンドのコマンド ID を持つマップを含むアプリケーションにディスパッチされます。\(次 `ON_OLECMD` の説明を参照してください\)。これにより、アプリケーションにディスパッチされる OLE コマンドは、MFC で **WM\_COMMAND** メッセージになります。  **WM\_COMMAND** メッセージは標準 MFC [コマンド ルーティング](../mfc/command-routing.md) アーキテクチャを使用するアプリケーションのメッセージ マップを通じて、ルーティングされます。  
  
 メッセージ マップとは異なり、MFC OLE コマンド マップは ClassWizard ではサポートされていません。  MFC の開発者は、OLE コマンド マップ サポートと OLE コマンド マップ エントリを手動で追加する必要があります。  OLE コマンド マップは、起動時にアクティブ ドキュメントはコンテナーの埋め込み先編集が有効な **WM\_COMMAND** のメッセージ ルーティングのチェイン内の任意のクラスの MFC の Active ドキュメント サーバーに追加できます。  これらのクラスは、[CWinApp](../mfc/reference/cwinapp-class.md)[CView](../Topic/CView%20Class.md)、[CDocument](../Topic/CDocument%20Class.md)と [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)から派生されるアプリケーションのクラスが含まれています。  Active ドキュメント コンテナーで、OLE コマンド マップは [COleDocObjectItem](../Topic/COleDocObjectItem%20Class.md)\-派生クラスにのみ追加できます。  また、Active ドキュメント コンテナーで、**WM\_COMMAND** メッセージが `COleDocObjectItem`のメッセージ マップ\-派生クラスだけにディスパッチされます。  
  
## OLE コマンド マップ マクロ  
 コマンド クラスにマップの機能を追加するには、次のマクロを使用する:  
  
```  
  
DECLARE_OLECMD_MAP ()  
  
```  
  
 このマクロは、コマンド マップを含むクラスのクラス宣言で \(通常はヘッダー ファイル\) になります。  
  
```  
  
BEGIN_OLECMD_MAP(  
theClass  
,   
baseClass  
)  
  
```  
  
 `theClass`  
 コマンド マップを含むクラスの名前。  
  
 `baseClass`  
 コマンド マップを含むクラスの基本クラスの名前。  
  
 このマクロは、コマンド マップの開始位置を示します。  コマンド マップを含むクラスの実装ファイルにこのマクロを使用します。  
  
```  
  
END_OLECMD_MAP()  
  
```  
  
 このマクロは、コマンド マップの終了位置を示します。  コマンド マップを含むクラスの実装ファイルにこのマクロを使用します。  このマクロは **BEGIN\_OLECMD\_MAP** マクロに常に従う必要があります。  
  
```  
  
ON_OLECMD(  
pguid  
,   
olecmdid  
,   
id  
)  
  
```  
  
 `pguid`  
 OLE コマンドのコマンド グループの GUID へのポインター。  このパラメーターは、標準 OLE コマンド グループの **NULL** です。  
  
 *olecmdid*  
 起動するコマンドの OLE コマンド ID。  
  
 `id`  
 この OLE コマンドが呼び出されたときのコマンド マップを含むアプリケーションに送信する **WM\_COMMAND** メッセージ ID。  
  
 、処理したい OLE コマンドのエントリを追加するには、コマンドにマップ `ON_OLECMD` マクロを使用します。  OLE コマンドを受け取った場合、**WM\_COMMAND** されたメッセージに変換され、アプリケーションのメッセージ マップを通じて標準 MFC のコマンド ルーティング アーキテクチャを使用してルーティングされます。  
  
## 使用例  
 次の例に [OLECMDID\_PRINT](http://msdn.microsoft.com/library/windows/desktop/ms691264) OLE コマンドを処理するように MFC の Active ドキュメント サーバーに OLE コマンド処理機能を追加する方法を示します。  この例ではアクティブ ドキュメント サーバーである MFC アプリケーションを作成するために AppWizard を使用することを前提としています。  
  
1.  `CView`\-派生クラスのヘッダー ファイルはクラス宣言に、`DECLARE_OLECMD_MAP` マクロを追加します。  
  
    > [!NOTE]
    >  `CView`\- **WM\_COMMAND** のメッセージ ルーティング チェーンにある Active ドキュメント サーバー クラスの 1 であるため、派生クラスを使用します。  
  
    ```  
    class CMyServerView : public CView  
    {  
    protected: // create from serialization only  
       CMyServerView();  
       DECLARE_DYNCREATE(CMyServerView)  
       DECLARE_OLECMD_MAP()  
    . . .  
    };  
    ```  
  
2.  `CView`の実装ファイル\-派生クラスは、`BEGIN_OLECMD_MAP` と `END_OLECMD_MAP` マクロを追加する:  
  
    ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
  
    END_OLECMD_MAP()  
    ```  
  
3.  標準 OLE 印刷コマンドを処理するには、標準の印刷コマンドで OLE コマンド ID と **WM\_COMMAND** ID に **ID\_FILE\_PRINT** を指定するコマンドにマップ [ON\_OLECMD](../Topic/ON_OLECMD.md) マクロを追加します。  **ID\_FILE\_PRINT** AppWizard は 生成された MFC アプリケーションで使用される標準印刷コマンド ID です:  
  
    ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
       ON_OLECMD(NULL,OLECMDID_PRINT,ID_FILE_PRINT)  
    END_OLECMD_MAP()  
    ```  
  
 **OLECMDID\_PRINT** が標準 OLE コマンド ID であるため標準 OLE コマンド マクロの代わりに、afxdocob.h で定義されていることに注意してください `ON_OLECMD` マクロの代わりに使用できます。  `ON_OLECMD_PRINT` マクロは、上に示した `ON_OLECMD` マクロと同じタスクを実行します。  
  
 コンテナー アプリケーションはサーバーの `IOleCommandTarget` インターフェイスを通じてこのサーバーに **OLECMDID\_PRINT** コマンドを送信する場合は、MFC の印刷のコマンド ハンドラーはアプリケーションを印刷し、サーバーによりも呼び出されます。  前の手順で追加した印刷コマンドを呼び出す Active ドキュメント コンテナーのコードは次のようになります。:  
  
```  
void CContainerCntrItem::DoOleCmd()  
{  
   IOleCommandTarget *pCmd = NULL;  
   HRESULT hr = E_FAIL;  
   OLECMD ocm={OLECMDID_PRINT, 0};  
  
   hr = m_lpObject->QueryInterface(IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));  
   if(FAILED(hr))  
      return;  
  
   hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);  
   if(SUCCEEDED(hr) && (ocm.cmdf & OLECMDF_ENABLED))  
   {  
      //Command is available and enabled so call it  
      COleVariant vIn;  
      COleVariant vOut;  
      hr = pCmd->Exec(NULL, OLECMDID_PRINT,  
 OLECMDEXECOPT_DODEFAULT, &vIn, &vOut);  
      ASSERT(SUCCEEDED(hr));  
   }  
   pCmd->Release();  
}  
```  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)