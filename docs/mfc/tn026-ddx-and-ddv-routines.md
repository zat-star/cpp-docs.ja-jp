---
title: "テクニカル ノート 26: DDX ルーチンおよび DDV ルーチン | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DDX"
  - "DDV"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DDV (ダイアログ データ バリデーション), プロシージャ"
  - "DDX (ダイアログ データ エクスチェンジ), プロシージャ"
  - "TN026"
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# テクニカル ノート 26: DDX ルーチンおよび DDV ルーチン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 ここでは、ダイアログをダイアログ データ エクスチェンジ \(DDX\) とダイアログ データ検証 \(DDV\) のアーキテクチャについて説明します。  また、DDX\_ または DDV\_ プロシージャを記述、ルーチンを使用するには、ClassWizard を拡張する方法について説明します。  
  
## ダイアログ データ エクスチェンジの概要  
 すべてのダイアログ データの関数は C\+\+ コードで実行されます。  特別なリソースまたは魔法マクロはありません。  機能の中心は、ダイアログ データ エクスチェンジ \(DDX\)、および検証を行う、ダイアログ クラスでオーバーライドされた仮想関数です。  これは、このフォームに必要です:  
  
```  
void CMyDialog::DoDataExchange(CDataExchange* pDX)  
{  
    CDialog::DoDataExchange(pDX);    // call base class  
  
    //{{AFX_DATA_MAP(CMyDialog)  
        <data_exchange_function_call>  
        <data_validation_function_call>  
    //}}AFX_DATA_MAP  
}  
```  
  
 特殊な形式の AFX コメントは ClassWizard がこの関数内のコードを検索し、編集することができます。  コードは、特殊な形式のコメント外に ClassWizard と互換性のない配置する必要があります。  
  
 上の例では、\<data\_exchange\_function\_call は\> フォームにです:  
  
```  
DDX_Custom(pDX, nIDC, field);  
```  
  
 data\_validation\_function\_call と \<は\> 省略可能では、フォームに T:  
  
```  
DDV_Custom(pDX, field, ...);  
```  
  
 複数の DDX\_\/DDV\_のペアは `DoDataExchange` の各関数に含まれていることがあります。  
  
 MFC に用意されているすべてのルーチン ダイアログ データ エクスチェンジとダイアログ データ検証ルーチンの一覧については、「afxdd\_.h」を参照してください。  
  
 ダイアログ データは、そのです: **CMyDialog** クラスのメンバー データ。  そのような構造体そのものには格納されません。  
  
## メモ  
 、この「ダイアログ データを呼び出しますが、すべての機能が `CWnd` から派生したクラスで使用でき、ダイアログに限定されません。  
  
 データの初期値は `//{{AFX_DATA_INIT` と `//}}AFX_DATA_INIT` のコメント ブロックの標準 C\+\+ のコンストラクターでは、一般に設定されます。  
  
 `CWnd::UpdateData` は `DoDataExchange`の呼び出しの初期化とエラー処理を行う操作です。  
  
 データ交換と検証を実行するに `CWnd::UpdateData` をいつでも呼び出すことができます。  既定で `UpdateData` \(true\) の既定の `CDialog::OnOK` ハンドラーと `UpdateData`で既定 `CDialog::OnInitDialog` \(FALSE\) が呼び出されます。  
  
 DDV\_ ルーチンは、その *フィールド*の DDX\_ ルーチンに従う必要があります。  
  
## そのですか。  
 ダイアログ データを使用するための次のコードを理解する必要はありません。  ただし、これが背後でどのように動作するかを理解すると、独自の交換または検証手順を書き込むことができます。  
  
 `DoDataExchange` のメンバー関数は `Serialize` のメンバー関数とよく似ています。クラスのメンバー データ from\/to 外部フォーム \(この場合はダイアログのコントロール\) に対するデータを取得または設定する必要があります。  `pDX` パラメーターはデータを交換するためのコンテキストでは、`CObject::Serialize`に `CArchive` パラメーターに似ています。  `pDX` \(`CDataExchange` オブジェクト\) に `CArchive` と同様に方向フラグの場合は方向フラグがあります:  
  
-   **\!m\_bSaveAndValidate**がコントロールに、状態データを読み込めば。  
  
-   `m_bSaveAndValidate`が、コントロールの状態データを設定する。  
  
 検証は `m_bSaveAndValidate` が設定されたときにのみ発生します。  `m_bSaveAndValidate` の値は `CWnd::UpdateData`を Boolean パラメーターによって決まります。  
  
 `CDataExchange` の 3 個の他の重要なメンバーがあります:  
  
-   `m_pDlgWnd`: コントロールを含むウィンドウ \(通常はダイアログ\)。  これは DDX\_ と DDV\_ のグローバル関数の呼び出し元は、DDX\/DDV ルーチンに" this "渡す必要があることを防ぐこと。  
  
-   `PrepareCtrl`と `PrepareEditCtrl`: データ交換にダイアログ コントロールを準備します。  検証が失敗した場合、フォーカスを設定するために、コントロールのハンドル。  `PrepareCtrl` は nonedit のコントロールに使用され、`PrepareEditCtrl`、エディット コントロールに使用されます。  
  
-   **失敗**: 入力エラーをユーザーに通知するメッセージ ボックスが育てた後に呼び出されます。  このルーチンは、最後のコントロール \(`PrepareCtrl`\/`PrepareEditCtrl`への最後のオーダー\) にフォーカスを復元し、例外をスローします。  このメンバー関数は DDX\_ と DDV\_ 両方ルーチンから呼び出されることがあります。  
  
## ユーザーの拡張  
 既定 DDX\/DDV の機能を拡張する方法はいくつかあります。  次の操作を行うことができます。  
  
-   新しいデータ型を追加します。  
  
    ```  
    CTime  
    ```  
  
-   新しい交換手順 \(DDX\_ \= "と"または"\) を追加します。  
  
    ```  
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);  
    ```  
  
-   新しい検証手順 \(DDV\_ \= "と"または"\) を追加します。  
  
    ```  
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);  
    // make sure time is in the future or past  
    ```  
  
-   検証手順に任意の式を渡します。  
  
    ```  
    DDV_MinMax(pDX, age, 0, m_maxAge);  
    ```  
  
    > [!NOTE]
    >  このような任意の式は ClassWizard で編集できない、特別な書式のコメントの外に移動する必要があります \(\/\/ {{AFX\_DATA\_MAP \(CMyClass\)\)。  
  
 **DoDialogExchange** メンバー関数を混合交換と検証関数を呼び出して条件またはそのほかの有効な C\+\+ のステートメントが格納されます。  
  
```  
//{{AFX_DATA_MAP(CMyClass)  
DDX_Check(pDX, IDC_SEX, m_bFemale);  
DDX_Text(pDX, IDC_EDIT1, m_age);  
//}}AFX_DATA_MAP  
if (m_bFemale)  
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);  
else  
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);  
```  
  
> [!NOTE]
>  上記のように、このようなコードは ClassWizard で編集できない、特別な形式のコメント外でのみ使用してください。  
  
## ClassWizard サポート  
 ClassWizard は ClassWizard のユーザー インターフェイスに独自の DDX\_ と DDV\_ ルーチンを統合することによって DDX\/DDV のカスタマイズのサブセットをサポートします。  これを行うには、プロジェクトまたはさまざまなプロジェクトの DDX と DDV 特定のルーチンを再利用することを計画している場合にのみ、コストされます。  
  
 これを行うには、特別なエントリが DDX.CLW \(以前のバージョンの Visual C\+\+ では APSTUDIO.INI にこの情報を格納した\) またはプロジェクトの .CLW ファイルで行われます。  特別なエントリがプロジェクトの .CLW ファイルの\[\]の概要情報セクションまたは\\Program の Files\\Microsoft ビジュアル Studio\\Visual C\+\+\\bin ディレクトリの DDX.CLW ファイルの ExtraDDX \[\]セクションに入力できます。  存在しない場合 DDX.CLW ファイルを作成する必要があります。  特定のプロジェクトにのみカスタム DDX\_\/DDV\_ルーチンを使用する場合 .CLW プロジェクト ファイルの概要のヒント\[\]セクションにエントリを追加します。  多くのプロジェクトのルーチンを使用する場合 DDX.CLW の\[\] ExtraDDX セクションにエントリを追加します。  
  
 これらの特殊なエントリの一般的な書式は次のとおりです。:  
  
```  
ExtraDDXCount=n  
```  
  
 数値は、どこに n ExtraDDX ですか。続行する行  
  
```  
ExtraDDX?=<keys>;<vb-keys>; <prompt>; <type>; <initValue>; <DDX_Proc>  
[;<DDV_Proc>; <prompt1>; <arg1>; [<prompt2>; <fmt2>]]  
```  
  
 か。1 番目の– n の DDX が定義されるリストに入力されるアクションです。  
  
 各フィールドは、「区切ります; 」文字。  フィールドと目的について、次に説明します。  
  
 \<キー\>  
 \= 示すダイアログ コントロールにはこの変数の型が許可される単一文字のリスト。  
  
 E \= 編集します  
  
 C \= 2 状態チェック ボックス  
  
 c \= 状態チェック ボックス  
  
 R \= 最初にグループのオプション ボタン  
  
 L \= nonsorted リスト ボックス  
  
 l \= 並べ替えられたリスト ボックス  
  
 M \= コンボ ボックス \(と項目の編集\)  
  
 N nonsorted \= ドロップの一覧  
  
 n \= 並べ替えられたドロップの一覧  
  
 1 つが \= 末尾に DDX の挿入がリスト \(既定\) 追加したヘッダーに追加されている場合は、これが「コントロール」プロパティを転送する DDX ルーチンに対して一般的に使用されます。  
  
 \<vb キー\>  
 このフィールドは VBX のコントロールへの 16 ビットの製品のみで使用されます \(VBX コントロールは 32 ビットの製品ではサポートされていません\)  
  
 \<プロンプト\>  
 プロパティにコンボ ボックス \(引用符なし\) に配置する文字列  
  
 \<type\>  
 ヘッダー ファイルに表示されるため、型の識別子を Single。  たとえば、上の例では DDX\_Time と、CTime に設定されます。  
  
 \<vb キー\>  
 このバージョンでは使用しない場合は常に空です。  
  
 \<initValue\>  
 初期値— 0 または空白。  これが NULL の場合、初期化の行は\/\/に書き込まれません{{実装ファイルの AFX\_DATA\_INIT セクション。  null のエントリが適切な初期化を保証するコンストラクターを持つ C\+\+ オブジェクトにする必要があります \(`CString`、`CTime`など\)。  
  
 \<DDX\_Proc\>  
 DDX\_ プロシージャの単一の ID。  C\+\+ の関数名は、「DDX\_」で開始する必要があります DDX\_Proc の ID に「DDX\_ \<」は\> 含まれません。  上の例では、DDX\_Proc\>  \< 識別子は時間です。  したがって、ClassWizard が実装ファイルに関数呼び出しを記述するときに{{AFX\_DATA\_MAP セクション、DDX\_ にこの名前を付けされ、DDX\_Time まで進みます。  
  
 \<コメント\>  
 この DDX の変数のダイアログに表示するコメント アウトします。  次に、Text を置き、通常 DDX\/DDV のペア実行されるアクションを記述する文字列を指定します。  
  
 \<DDV\_Proc\>  
 エントリの DDV の部分は省略可能です。  DDX すべてのルーチンに対応する DDV ルーチンがありません。  多くの場合、転送の整数部分として検証の結果を含むと便利です。  これは、頻繁に ClassWizard がパラメーターなしで DDV ルーチンをサポートしていないため、DDV ルーチンにパラメーターが必要になった場合です。  
  
 \<引数\>  
 DDV\_ プロシージャの単一の ID。  C\+\+ の関数名は、「DDV\_」で開始する必要が DDX\_Proc の ID に「DDX\_ \<」は\> 含まれません。  
  
 1 または 2 DDV の引数で指定する:  
  
 \<promptX\>  
 編集項目の場所に文字列 \(アクセラレータ用と &\)  
  
 \<fmtX\>  
 引数の型の書式指定文字、1 の  
  
 d \= int  
  
 u \= 符号なし  
  
 D \= long int \(つまり、Long\)  
  
 U \=、符号なし \(つまり、DWORD\)  
  
 f \= float  
  
 F \= double  
  
 s \= 文字列  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)