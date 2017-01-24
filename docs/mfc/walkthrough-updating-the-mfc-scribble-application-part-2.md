---
title: "チュートリアル: MFC Scribble アプリケーションの更新 (パート 2) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "チュートリアル [C++]"
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
caps.latest.revision: 36
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# チュートリアル: MFC Scribble アプリケーションの更新 (パート 2)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このチュートリアルの[パート 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) では、Office Fluent リボンを従来の Scribble アプリケーションに追加する方法を説明しました。  ここでは、ユーザーがメニューやコマンドの代わりに使用できるリボン パネルやコントロールを追加する方法を説明します。  
  
## 必須コンポーネント  
 [Visual C\+\+ のサンプル](../top/visual-cpp-samples.md)  
  
##  <a name="top"></a> セクション  
 このパートは、次のセクションで構成されています。  
  
-   [リボンへの新しいパネルの追加](#addNewPanel)  
  
-   [リボンへのヘルプ パネルの追加](#addHelpPanel)  
  
-   [リボンへのペン パネルの追加](#addPenPanel)  
  
-   [リボンへのカラー ボタンの追加](#addColorButton)  
  
-   [ドキュメント クラスへのカラー メンバーの追加](#addColorMember)  
  
-   [設定の初期化と保存](#initPenSave)  
  
##  <a name="addNewPanel"></a> リボンへの新しいパネルの追加  
 次の手順では、ツール バーとステータス バーの表示\/非表示を制御する 2 つのチェック ボックスがある **\[ビュー\]** パネルの追加方法と、マルチ ドキュメント インターフェイス \(MDI: Multiple Document Interface\) の作成と配置を制御する垂直方向の分割ボタンがある **\[ウィンドウ\]** パネルの追加方法を説明します。  
  
#### リボン バーに \[表示\] パネルと \[ウィンドウ\] パネルを追加するには  
  
1.  ステータス バーとツール バーを切り替える 2 つのチェック ボックスがある、「`表示`」という名前のパネルを作成します。  
  
    1.  **\[ツールボックス\]** から、パネルを **\[ホーム\]** カテゴリにドラッグします。  2 つのチェック ボックスをパネルにドラッグします。  
  
    2.  パネルをクリックして、そのプロパティを修正します。  **\[キャプション\]** を「`表示`」に変更します。  
  
    3.  1 つ目のチェック ボックスをクリックして、そのプロパティを修正します。  **\[ID\]** を「`ID_VIEW_TOOLBAR`」に変更し、**\[キャプション\]** を「`ツール バー`」に変更します。  
  
    4.  2 つ目のチェック ボックスをクリックして、そのプロパティを修正します。  **\[ID\]** を「`ID_VIEW_STATUS_BAR`」に変更し、**\[キャプション\]** を「`ステータス バー`」に変更します。  
  
2.  分割ボタンのある「`ウィンドウ`」という名前のパネルを作成します。  ユーザーが分割ボタンをクリックすると、ショートカット メニューに \(Scribble アプリケーションで定義した\) 3 つのコマンドが表示されます。  
  
    1.  **\[ツールボックス\]** から、パネルを **\[ホーム\]** カテゴリにドラッグします。  ボタンをパネルにドラッグします。  
  
    2.  パネルをクリックして、そのプロパティを修正します。  **\[キャプション\]** を「`ウィンドウ`」に変更します。  
  
    3.  ボタンをクリックします。  **\[キャプション\]**、**\[キー\]**、**\[Large Image Index\]**、**\[分割モード\]** を、それぞれ「`ウィンドウ`」、「`w`」、「`1`」、「`False`」に変更します。  次 **\[項目エディター\]** ダイアログ ボックスを開くに **\[メニュー アイテム\]** の横にある省略記号 \(**...**\) をクリックします。  
  
    4.  **\[追加\]** を 3 回クリックして、ボタンを 3 つ追加します。  
  
    5.  1 つ目のボタンをクリックし、**\[キャプション\]** を「`新しいウィンドウ`」に変更し、**\[ID\]** を「`ID_WINDOW_NEW`」に変更します。  
  
    6.  2 つ目のボタンをクリックし、**\[キャプション\]** を「`重ねて表示`」に変更し、**\[ID\]** を「`ID_WINDOW_CASCADE`」に変更します。  
  
    7.  3 つ目のボタンをクリックし、**\[キャプション\]** を「`並べて表示`」に変更し、**\[ID\]** を「`ID_WINDOW_TILE_HORZ`」に変更します。  
  
3.  変更内容を保存し、アプリケーションをビルドして実行します。  **\[表示\]** パネルと **\[ウィンドウ\]** パネルが表示されます。  ボタンをクリックして、正しく機能することを確認します。  
  
 \[[セクション](#top)\]  
  
##  <a name="addHelpPanel"></a> リボンへのヘルプ パネルの追加  
 これで、Scribble アプリケーションで定義されている 2 つのメニュー項目を、**\[ヘルプのトピック\]** と **\[Scribble バージョン情報\]** という名前のリボン ボタンに割り当てることができます。  これらのボタンは、**\[ヘルプ\]** という名前の新しいパネルに追加されます。  
  
#### ヘルプ パネルを追加するには  
  
1.  **\[ツールボックス\]** から、パネルを **\[ホーム\]** カテゴリにドラッグします。  2 つのボタンをパネルにドラッグします。  
  
2.  パネルをクリックして、そのプロパティを修正します。  **\[キャプション\]** を「`ヘルプ`」に変更します。  
  
3.  1 つ目のボタンをクリックします。  **\[キャプション\]** を「`ヘルプのトピック`」に変更し、**\[ID\]** を「`ID_HELP_FINDER`」に変更します。  
  
4.  2 つ目のボタンをクリックします。  **\[キャプション\]** を「`バージョン情報...`」に変更し、**\[ID\]** を「`ID_APP_ABOUT`」に変更します。  
  
5.  変更内容を保存し、アプリケーションをビルドして実行します。  2 つのリボン ボタンのある **\[ヘルプ\]** パネルが表示されます。  
  
    > [!IMPORTANT]
    >  **\[ヘルプ トピック\]** ボタンをクリックすると、Scribble アプリケーションは、圧縮された HTML ヘルプ ファイル \(.chm\) によって指定された *your\_project\_name*.chm を開きます。  そのため、プロジェクトが名前付き Scribble でない場合は、ヘルプ ファイルの名前をプロジェクト名に変更する必要があります。  
  
 \[[セクション](#top)\]  
  
##  <a name="addPenPanel"></a> リボンへのペン パネルの追加  
 ここでは、ペンの太さと色を制御するボタンを表示するパネルを追加します。  このパネルには、太いペンと細いペンを切り替えるチェック ボックスが含まれます。  この機能は、Scribble アプリケーションの **\[太い線\]** メニュー項目に似ています。  
  
 元の Scribble アプリケーションでは、ユーザーは、メニューの **\[ペンの太さ\]** をクリックしたときに表示されるダイアログ ボックスでペンの太さを選択しました。  このリボン バーには新しいコントロールのための場所が十分にあるため、ダイアログ ボックスをリボン上の 2 つのコンボ ボックスで置き換えることができます。  1 つのコンボ ボックスは細いペンの太さを調整し、もう 1 つのコンボ ボックスでは太い線の太さを調整します。  
  
#### リボンにペン パネルとコンボ ボックスを追加するには  
  
1.  **\[ツールボックス\]** から、パネルを **\[ホーム\]** カテゴリにドラッグします。  次に、チェック ボックスと 2 つのコンボ ボックスをパネルにドラッグします。  
  
2.  パネルをクリックして、そのプロパティを修正します。  **\[キャプション\]** を「`ペン`」に変更します。  
  
3.  チェック ボックスをクリックします。  **\[キャプション\]** を「`太さ`」に変更し、**\[ID\]** を「`ID_PEN_THICK_OR_THIN`」に変更します。  
  
4.  1 つ目のコンボ ボックスをクリックします。  **\[キャプション\]**、**\[ID\]**、**\[テキスト\]**、**\[種類\]**、**\[データ\]** を、それぞれ「`細いペン`」、「`ID_PEN_THIN_WIDTH`」、「`2`」、「`ドロップダウン リスト`」、「`1;2;3;4;5;6;7;8;9;`」に変更します。  
  
5.  2 つ目のコンボ ボックスをクリックします。  **\[キャプション\]**、**\[ID\]**、**\[テキスト\]**、**\[種類\]**、**\[データ\]** を、それぞれ「`太いペン`」、「`ID_PEN_THICK_WIDTH`」、「`5`」、「`ドロップダウン リスト`」、「`5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`」に変更します。  
  
6.  新しいコンボ ボックスは既存のメニュー項目には対応していません。  したがって、それぞれのペン オプションに対するメニュー項目を作成する必要があります。  
  
    1.  **\[リソース ビュー\]** ウィンドウで、IDR\_SCRIBBTYPE メニュー リソースを開きます。  
  
    2.  **\[ペン\]** をクリックして **\[ペン\]** メニューを開きます。  次 `Thi&n のペン`を **\[ここへ入力\]** をクリックします入力します。  
  
    3.  今入力した文字列を右クリックすると **\[プロパティ\]** ウィンドウが表示されます。ここで、ID プロパティを「`ID_PEN_THIN_WIDTH`」に変更します。  
  
    4.  また、ペン メニューの各項目に対するイベント ハンドラーを作成する必要もあります。  先ほど作成した文字列を右クリックし、**\[イベント ハンドラーの追加\]** をクリックします **\[Thi&n のペン\]** メニュー項目を示します。  イベント ハンドラー ウィザードが表示されます。  
  
    5.  このウィザードの **\[クラス リスト\]** ボックスで **\[CScribbleDoc\]** をクリックし、次に **\[追加と編集\]** ボタンをクリックします。  これで、`CScribbleDoc::OnPenThinWidth` という名前のイベント ハンドラーが作成されます。  
  
    6.  次のコードを `CScribbleDoc::OnPenThinWidth` に追加します。  
  
        ```  
        // Get a pointer to the ribbon bar  
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();  
        ASSERT_VALID(pRibbon);  
        // Get a pointer to the Thin Width combo box  
        CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(  
           CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));  
        //Get the selected value  
        int nCurSel = pThinComboBox->GetCurSel();  
        if (nCurSel >= 0)  
        {  
           m_nThinWidth = atoi(pThinComboBox->GetItem(nCurSel));  
        }  
        // Create a new pen using the selected width  
        ReplacePen();    
        ```  
  
7.  次に、太いペンのメニュー項目とイベント ハンドラーを作成します。  
  
    1.  **\[リソース ビュー\]** ウィンドウで、IDR\_SCRIBBTYPE メニュー リソースを開きます。  
  
    2.  **\[ペン\]** をクリックして \[ペン\] メニューを開きます。  次 `Thic&k のペン`を **\[ここへ入力\]** をクリックします入力します。  
  
    3.  今入力したテキストを右クリックすると、**\[プロパティ\]** ウィンドウが表示されます。  ID プロパティを「`ID_PEN_THICK_WIDTH`」に変更します。  
  
    4.  直前に作成した **\[太いペン\]** メニュー項目を右クリックし、**\[イベント ハンドラーの追加\]** をクリックします。  イベント ハンドラー ウィザードが表示されます。  
  
    5.  このウィザードの **\[クラス リスト\]** ボックスで **\[CScribbleDoc\]** をクリックし、次に **\[追加と編集\]** ボタンをクリックします。  これで、`CScribbleDoc::OnPenThickWidth` という名前のイベント ハンドラーが作成されます。  
  
    6.  次のコードを `CScribbleDoc::OnPenThickWidth` に追加します。  
  
        ```  
        // Get a pointer to the ribbon bar  
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();  
        ASSERT_VALID(pRibbon);  
        CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(  
           CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));  
        // Get the selected value  
        int nCurSel = pThickComboBox->GetCurSel();  
        if (nCurSel >= 0)  
        {  
           m_nThickWidth = atoi(pThickComboBox->GetItem(nCurSel));  
        }  
        // Create a new pen using the selected width  
        ReplacePen();  
        ```  
  
8.  変更内容を保存し、アプリケーションをビルドして実行します。  新しいボタンとコンボ ボックスが表示されます。  フリーハンドでさまざまな太さのペンを使用してみます。  
  
 \[[セクション](#top)\]  
  
##  <a name="addColorButton"></a> ペン パネルへのカラー ボタンの追加  
 次は、カラーでフリーハンド描画できる [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) オブジェクトを追加します。  
  
#### ペン パネルにカラー ボタンを追加するには  
  
1.  カラー ボタンを追加する前に、カラー ボタンのメニュー項目を作成します。  **\[リソース ビュー\]** ウィンドウで、IDR\_SCRIBBTYPE メニュー リソースを開きます。  **\[ペン\]** メニュー項目をクリックして \[ペン\] メニューを開きます。  次 `&Color`を **\[ここへ入力\]** をクリックします入力します。  今入力したテキストを右クリックすると、**\[プロパティ\]** ウィンドウが表示されます。  ID を「`ID_PEN_COLOR`」に変更します。  
  
2.  ここで、カラー ボタンを追加します。  **\[ツールボックス\]** から、カラー ボタンを **\[ペン\]** パネルにドラッグします。  
  
3.  カラー ボタンをクリックします。  **\[キャプション\]**、**\[ID\]**、**\[Simple Look\]**、**\[Large Image Index\]**、**\[分割モード\]** を、それぞれ「`カラー`」、「`ID_PEN_COLOR`」、「`True`」、「`1`」、「`False`」に変更します。  
  
4.  変更内容を保存し、アプリケーションをビルドして実行します。  新しいカラー ボタンが **\[ペン\]** パネルに表示されます。  ただし、イベント ハンドラーがないため、このボタンを使用できません。  次の手順では、カラー ボタンのイベント ハンドラーを追加する方法を説明します。  
  
 \[[セクション](#top)\]  
  
##  <a name="addColorMember"></a> ドキュメント クラスへのカラー メンバーの追加  
 元の Scribble アプリケーションにはカラー ペンがないため、その実装を作成する必要があります。  ドキュメントのペン カラーを格納するには、新しいメンバーをドキュメント クラス `CscribbleDoc.` に追加します。  
  
#### ドキュメント クラスにカラー メンバーを追加するには  
  
1.  scribdoc.h の `CScribbleDoc` クラスで `// Attributes` セクションを探します。  `m_nThickWidth` データ メンバーの定義の後に、次のコード行を追加します。  
  
    ```  
    // Current pen color  
    COLORREF   m_penColor;  
    ```  
  
2.  各ドキュメントには、ユーザーが既に描画したストロークの一覧があります。  各ストロークは、`CStroke` オブジェクトによって定義されます。  `CStroke` クラスには、ペン カラーに関する情報は含まれません。  したがって、このクラスを修正する必要があります。  scribdoc.h の `CStroke` クラスで、`m_nPenWidth` データ メンバーの後に次のコード行を追加します。  
  
    ```  
    // Pen color for the stroke  
    COLORREF   m_penColor;  
    ```  
  
3.  scribdoc.h に、新しい `CStroke` コンストラクターを追加し、そのパラメーターで幅とカラーを指定します。  次のコード行を `CStroke(UINT nPenWidth);` ステートメントの後に追加します。  
  
    ```  
    CStroke(UINT nPenWidth, COLORREF penColor);  
    ```  
  
4.  scribdoc.cpp に、新しい `CStroke` コンストラクターの実装を追加します。  `CStroke::CStroke(UINT nPenWidth)` コンストラクターの実装の後に、次のコードを追加します。  
  
    ```  
    // Constructor that uses the document's current width and color  
    CStroke::CStroke(UINT nPenWidth, COLORREF penColor)  
    {  
       m_nPenWidth = nPenWidth;  
       m_penColor = penColor;  
       m_rectBounding.SetRectEmpty();  
    }  
    ```  
  
5.  `CStroke::DrawStroke` メソッドの 2 行目を次のように変更します。  
  
    ```  
    if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))  
    ```  
  
6.  ドキュメント クラスに対する既定のペン カラーを設定します。  scribdoc.cpp では、`m_nThickWidth = 5;` ステートメントの後に、次のコードを `CScribbleDoc::InitDocument` に追加します。  
  
    ```  
    // default pen color is black  
    m_penColor = RGB(0,0,0);   
    ```  
  
7.  scribdoc.cpp で、`CScribbleDoc::NewStroke` メソッドの最初の行を次のように変更します。  
  
    ```  
    CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);  
    ```  
  
8.  `CScribbleDoc::ReplacePen` メソッドの最終行を次のように変更します。  
  
    ```  
    m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);  
    ```  
  
9. 前の手順では、`m_penColor` メンバーを追加しました。  次に、メンバーを設定するカラー ボタンのイベント ハンドラーを作成します。  
  
    1.  **\[リソース ビュー\]** ウィンドウで、IDR\_SCRIBBTYPE メニュー リソースを開きます。  
  
    2.  **\[カラー\]** メニュー項目を右クリックし、**\[イベント ハンドラーの追加\]** をクリックします。  **イベント ハンドラー ウィザード**が表示されます。  
  
    3.  このウィザードの **\[クラス リスト\]** ボックスで **\[CScribbleDoc\]** をクリックし、次に **\[追加と編集\]** ボタンをクリックします。  この操作によって `CScribbleDoc::OnPenColor` イベント ハンドラー スタブが作成されます。  
  
10. `CScribbleDoc::OnPenColor` イベント ハンドラーのスタブを次のコードで置き換えます。  
  
    ```  
    void CScribbleDoc::OnPenColor()  
    {  
    // Change pen color to reflect color button's current selection  
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();  
    ASSERT_VALID(pRibbon);  
    CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(  
       CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));  
    m_penColor = pColorBtn->GetColor();  
    // Create new pen using the selected color  
    ReplacePen();  
    }  
    ```  
  
11. 変更を保存し、アプリケーションをビルドして実行します。  カラー ボタンを押して、ペンのカラーを変更できるようになります。  
  
 \[[セクション](#top)\]  
  
##  <a name="initPenSave"></a> 設定の初期化と保存  
 次に、ペンのカラーと太さを初期化します。  最後に、カラー描画をファイルに保存し、ファイルから読み込みます。  
  
#### リボン バーのコントロールを初期化するには  
  
1.  リボン バーのペンを初期化します。  
  
     scribdoc.cpp で、`CScribbleDoc::InitDocument` メソッドの `m_sizeDoc = CSize(200,200)` ステートメントの後に次のコードを追加します。  
  
    ```  
    // Reset the ribbon UI to its initial values  
    CMFCRibbonBar* pRibbon =   
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();  
    ASSERT_VALID(pRibbon);  
    CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(  
       CMFCRibbonColorButton,   
       pRibbon->FindByID(ID_PEN_COLOR));  
    // Set ColorButton to black  
    pColorBtn->SetColor(RGB(0,0,0));    
    CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(  
       CMFCRibbonComboBox,   
       pRibbon->FindByID(ID_PEN_THIN_WIDTH));  
    // Set Thin pen combobox to 2  
    pThinComboBox->SelectItem(1);   
    CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(  
       CMFCRibbonComboBox,   
       pRibbon->FindByID(ID_PEN_THICK_WIDTH));  
    // Set Thick pen combobox to 5  
    pThickComboBox->SelectItem(0);  
    ```  
  
2.  ファイルにカラー描画を保存します。  scribdoc.cpp で、`CStroke::Serialize` メソッドの `ar << (WORD)m_nPenWidth;` ステートメントの後に、次のコードを追加します。  
  
    ```  
    ar << (COLORREF)m_penColor;  
    ```  
  
3.  最後に、ファイルからカラー描画を読み込みます。  `CStroke::Serialize` メソッドの `m_nPenWidth = w;` ステートメントの後に、次のコード行を追加します。  
  
    ```  
    ar >> m_penColor;  
    ```  
  
4.  次に、カラーでフリーハンド描画し、それをファイルに保存します。  
  
 \[[セクション](#top)\]  
  
## 結論  
 ここでは、MFC Scribble アプリケーションの更新を行いました。  既存のアプリケーションを修正するときに、そのガイドとしてこのチュートリアルを使用してください。  
  
## 参照  
 [チュートリアル](../mfc/walkthroughs-mfc.md)   
 [チュートリアル: MFC Scribble アプリケーションの更新 \(パート 1\)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)