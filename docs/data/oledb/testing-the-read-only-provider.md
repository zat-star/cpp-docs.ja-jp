---
title: "読み取り専用プロバイダーのテスト | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB プロバイダー, 呼び出し"
  - "OLE DB プロバイダー, テスト"
  - "テスト (プロバイダーを)"
  - "テスト, OLE DB プロバイダー"
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 読み取り専用プロバイダーのテスト
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロバイダーをテストするにはコンシューマーが必要です。  これには、プロバイダーに対応する機能がコンシューマーでサポートされている必要があります。  OLE DB コンシューマー テンプレートは、OLE DB を取り囲む薄いラップであり、プロバイダーの COM オブジェクトに相当します。  ソースはコンシューマー テンプレートに付属しているため、これを使用してプロバイダーを簡単にデバッグできます。  また、コンシューマー テンプレートを使うと、コンシューマー アプリケーションを少ないコードで短時間に開発できます。  
  
 このトピックの例では、MFC アプリケーション ウィザードのテスト コンシューマー用の既定のアプリケーションを作成します。  テスト アプリケーションは、OLE DB コンシューマー テンプレート コードが追加された単純なダイアログです。  
  
### テスト アプリケーションを作成するには  
  
1.  **\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  
  
2.  \[プロジェクトの種類\] ペインで、**\[Visual C\+\+ プロジェクト\]** フォルダーを選択します。  テンプレート ペインの **\[MFC アプリケーション\]** をクリックします。  
  
3.  プロジェクト名に「TestProv」と入力し、**\[OK\]** をクリックします。  
  
     MFC アプリケーション ウィザードが表示されます。  
  
4.  **\[アプリケーションの種類\]** ページの \[ダイアログ ベース\] を選択します。  
  
5.  **\[高度な機能\]** ページの \[オートメーション\] を選択し、\[完了\] をクリックします。  
  
> [!NOTE]
>  **CTestProvApp::InitInstance** に **CoInitialize** を追加した場合、アプリケーションはオートメーション サポートを必要としません。  
  
 \[TestProv\] ダイアログ ボックス \(IDD\_TESTPROV\_DIALOG\) は、リソース ビューで選択して、表示したり編集したりできます。  行セットの各文字列用に 1 つずつ、合計 2 つのリスト ボックスをダイアログ ボックスに配置します。  リスト ボックスが選択されているときに **Alt** キーを押しながら **Enter** キーを押し、\[スタイル\] タブをクリックして \[並べ替え\] チェック ボックスをオフにすることにより、両方のリスト ボックスの並べ替えプロパティをオフにします。  また、ダイアログ ボックスには、ファイルをフェッチする \[Run\] ボタンを配置します。  完成した \[TestProv\] ダイアログ ボックスには、"String 1" および "String 2" というラベルの付いた 2 つのリスト ボックスが作成されます。また、**\[OK\]**、\[キャンセル\]、および \[Run\] の各ボタンもあります。  
  
 ダイアログ クラスのヘッダー ファイル \(この場合は TestProvDlg.h\) を開きます。  ヘッダー ファイルで、クラス宣言の外側に次のコードを追加します。  
  
```  
////////////////////////////////////////////////////////////////////////  
// TestProvDlg.h  
  
class CProvider   
{  
// Attributes  
public:  
   char   szField1[16];  
   char   szField2[16];  
  
   // Binding Maps  
BEGIN_COLUMN_MAP(CProvider)  
   COLUMN_ENTRY(1, szField1)  
   COLUMN_ENTRY(2, szField2)  
END_COLUMN_MAP()  
};  
```  
  
 このコードは、どの列が行セットに入るかを定義するユーザー レコードを表します。  クライアントは、**IAccessor::CreateAccessor** を呼び出すときにこれらのエントリを使用して連結する列を指定します。  OLE DB コンシューマー テンプレートを使用して、列を動的に連結することもできます。  COLUMN\_ENTRY マクロは、プロバイダーの PROVIDER\_COLUMN\_ENTRY マクロに相当するクライアント側のマクロです。  2 つの COLUMN\_ENTRY マクロは、2 つの文字列の序数、型、長さ、およびデータ メンバーを指定します。  
  
 **Ctrl** キーを押しながら \[Run\] ボタンをダブルクリックすることにより、\[Run\] ボタンのハンドラー関数を追加します。  関数に次のコードを配置します。  
  
```  
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
void CtestProvDlg::OnRun()  
{  
   CCommand<CAccessor<CProvider> > table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
      return;  
  
   while (table.MoveNext() == S_OK)  
   {  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
   }  
}  
```  
  
 `CCommand`、`CDataSource`、`CSession` の各クラスは、すべて OLE DB コンシューマー テンプレートに属します。  各クラスは、プロバイダーの COM オブジェクトと同じ動作をします。  `CCommand` オブジェクトは、ヘッダー ファイルで宣言された `CProvider` クラスをテンプレート パラメーターとして使用します。  `CProvider` パラメーターは、プロバイダーからデータにアクセスするために使用するバインディングを表します。  データ ソース、セッション、およびコマンドの `Open` :コードを次に示します。  
  
```  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
 上記の各クラスを開くコードでは、それぞれのクラスに対応する COM オブジェクトがプロバイダーに作成されます。  プロバイダーを特定するには、プロバイダーの ProgID を使用します。  ProgID は、システム レジストリから取得するか、MyProvider.rgs ファイルを検索 \(プロバイダーのディレクトリを開き、ProgID キーを検索\) することで取得できます。  
  
 MyData.txt ファイルは、MyProv サンプルに含まれています。  独自のファイルを作成するには、エディターを使用して偶数個の文字を入力し、各文字間で Enter キーを押します。  ファイルを移動した場合はパス名を変更してください。  
  
 `table.Open` 行で "c:\\\\samples\\\\myprov\\\\MyData.txt" という文字列を渡します。  `Open` 呼び出しにステップ インすると、この文字列がプロバイダーの `SetCommandText` メソッドに渡されることがわかります。  これは、`ICommandText::Execute` メソッドが使用した文字列です。  
  
 データをフェッチするには、テーブルに対して `MoveNext` を呼び出します。  `MoveNext` は、**IRowset::GetNextRows**、`GetRowCount`、および `GetData` の各関数を呼び出します。  それ以上行がない場合 \(つまり、行セットの現在位置が `GetRowCount` を超えた場合\) は、ループが終了します。  
  
```  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 それ以上行がない場合、プロバイダーは **DB\_S\_ENDOFROWSET** を返します。  **DB\_S\_ENDOFROWSET** 値はエラーではありません。  `S_OK` が返されなかった場合は、データ フェッチのループを終了するようにしてください。行の有無の判断に SUCCEEDED マクロは使用しないでください。  
  
 これで、プログラムをビルドしてテストできるようになります。  
  
## 参照  
 [単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)