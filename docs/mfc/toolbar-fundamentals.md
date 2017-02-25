---
title: "ツール バーに関する基本事項 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RT_TOOLBAR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーション ウィザード [C++], インストール (既定のアプリケーション ツール バーを)"
  - "コマンド ID, ツール バー ボタン"
  - "CToolBar クラス, 既定のツール バー (アプリケーション ウィザードの)"
  - "埋め込む (フレーム ウィンドウ クラスにツール バーを)"
  - "フレーム ウィンドウ クラス, ツール バー (埋め込み)"
  - "LoadBitmap メソッド, ツール バー"
  - "LoadToolBar メソッド"
  - "リソース [MFC], ツール バー"
  - "RT_TOOLBAR リソース"
  - "SetButtons メソッド"
  - "ツール バー コントロール [MFC], コマンド ID"
  - "ツール バー コントロール [MFC], ツール バー (アプリケーション ウィザードを使用して作成した)"
  - "ツール バー エディター, アプリケーション ウィザード"
  - "ツール バー [C++], 追加 (アプリケーション ウィザードを使用して既定値を)"
  - "ツール バー [C++], 作成"
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ツール バーに関する基本事項
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、アプリケーション ウィザードのオプションを選択して、アプリケーションに既定のツール バーを追加できる基本的な MFC の実装について説明します。  ここでは、次の内容について説明します。  
  
-   [アプリケーション ウィザードのツール バー](#_core_the_appwizard_toolbar_option)  
  
-   [コードのツールバー](#_core_the_toolbar_in_code)  
  
-   [ツールバー リソースの編集](#_core_editing_the_toolbar_resource)  
  
-   [複数のツール バー](#_core_multiple_toolbars)  
  
##  <a name="_core_the_appwizard_toolbar_option"></a> アプリケーション ウィザード ツール バー オプション  
 既定のボタンを含む一つのツール バーを取得するには、User Interface Features というページの標準ドッキング ツール バー オプションを選択します。  これにより、アプリケーションにコードを追加する:  
  
-   ツールバー オブジェクトを作成します。  
  
-   ドッキングすると、ドッキング機能を含むツール バーを管理します。  
  
##  <a name="_core_the_toolbar_in_code"></a> コードのツールバー  
 ツール バーは、アプリケーションの **CMainFrame** クラスのデータ メンバーとして宣言する [CToolBar](../mfc/reference/ctoolbar-class.md) オブジェクトです。  つまり、ツール バー オブジェクトはメイン フレーム ウィンドウ オブジェクトに埋め込まれます。  これは、フレーム ウィンドウを破棄するときにフレーム ウィンドウを作成し、ツール バーを破棄すると MFC がツール バーを意味します。  次の部分クラス宣言は、マルチ ドキュメント インターフェイス \(MDI\) アプリケーションでは、埋め込まれたな埋め込まれたなツール バーとステータス バーのデータ メンバーを示します。  また、`OnCreate` のメンバー関数のオーバーライドを示します。  
  
 [!CODE [NVC_MFCListView#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCListView#6)]  
  
 ツール バーの作成を **CMainFrame::OnCreate**に発生します。  MFC は、フレームのウィンドウを作成すると表示される前に [OnCreate](../Topic/CWnd::OnCreate.md) を呼び出しますが。  アプリケーション ウィザードで生成された既定 `OnCreate` は次のツール バー:タスクを実行します。  
  
1.  `CToolBar` オブジェクトの [作成](../Topic/CToolBar::Create.md) メンバー関数を [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) の基になるオブジェクトを作成するために呼び出されます。  
  
2.  [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) をツール バー リソース情報を読み込むために呼び出されます。  
  
3.  呼び出しは、ドッキング、フローティング、ツール ヒントを有効にするために機能します。  これらの呼び出しの詳細については、「[フローティング ツール バーとドッキング](../mfc/docking-and-floating-toolbars.md)」を参照してください。  
  
> [!NOTE]
>  MFC の一般的なサンプル [DOCKTOOL](../top/visual-cpp-samples.md) は、新旧の MFC ツール バーの図が含まれています。  **COldToolbar** を使用する `LoadToolBar` \(\) ではなくツール バーは `LoadBitmap` と `SetButtons`、手順 2 の呼び出しが必要です。  新しいツール バーには `LoadToolBar`を呼び出す必要があります。  
  
 フローティング、ドッキング、ツール ヒントの呼び出しは省略可能です。  必要に応じて `OnCreate` でこれらの行を削除できます。  結果は、固定、フローティング状態になったり、redock とツール ヒントを表示することができるツール バーです。  
  
##  <a name="_core_editing_the_toolbar_resource"></a> ツールバー リソースの編集  
 、アプリケーション ウィザードで取得する既定のツール バーは、MFC Version 4.0 で導入された **RT\_TOOLBAR** のカスタム リソースに基づいています。  [ツールバー エディター](../mfc/toolbar-editor.md)のこのリソースを編集できます。  エディターでボタンを追加、削除、再配置が容易になります。  これは Visual C\+\+ の一般的なグラフィックス エディターによく似ているボタンのグラフィカル エディターが含まれます。  以前のバージョンの Visual C\+\+ のツール バーを編集した場合は、タスクがはるかに簡単になります。  
  
 コマンドにツール バー ボタンを追加するには、ボタンに `ID_MYCOMMAND`などのコマンド ID が表示されます。  ツール バー エディターのプロパティ ページでボタンのコマンド ID を指定します。  コマンドのハンドラー関数を作成します \(詳細については、" [関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md) を参照してください。  
  
 **RT\_TOOLBAR** のリソースを新しい [CToolBar](../mfc/reference/ctoolbar-class.md) メンバー関数を使用します。  [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) は、[LoadBitmap](../Topic/CToolBar::LoadBitmap.md) のボタン スタイルを設定し、ビットマップ イメージとボタンをアタッチするツール バー ボタン イメージのビットマップを読み込むようによう先と [SetButtons](../Topic/CToolBar::SetButtons.md) を受け取ります。  
  
 ツール バー エディターを使用する方法の詳細については、「[ツール バー エディター](../mfc/toolbar-editor.md)」を参照してください。  
  
##  <a name="_core_multiple_toolbars"></a> 複数のツール バー  
 アプリケーション ウィザードには、1 種類の既定のツールを提供します。  アプリケーションで複数のツール バーが必要な場合は、既定のツール バーのウィザードで生成されたコードに基づいて追加のツール バーのコードをシミュレートできます。  
  
 コマンドの結果ツール バーを表示するには、必要があります:  
  
-   新規ツール バーをツール バー エディターで作成し、[LoadToolbar](../Topic/CToolBar::LoadToolBar.md) のメンバー関数の `OnCreate` を読み込んでください。  
  
-   メイン フレーム ウィンドウ クラスに [CToolBar](../mfc/reference/ctoolbar-class.md) オブジェクトを埋め込みます。  
  
-   ドッキングするに `OnCreate` の適切な関数呼び出しを行うと、ツール バーをフローティングに、スタイルなどを設定します。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [MFC ツール バーの実装 \(ツール バーの概要情報\)](../mfc/mfc-toolbar-implementation.md)  
  
-   [ツール バーのフローティングとドッキング](../mfc/docking-and-floating-toolbars.md)  
  
-   [ツール バーのツール ヒント](../Topic/Toolbar%20Tool%20Tips.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) クラスと [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) クラス  
  
-   [ToolBar コントロールの使用](../Topic/Working%20with%20the%20Toolbar%20Control.md)  
  
-   [古いツール バーを使用する](../Topic/Using%20Your%20Old%20Toolbars.md)  
  
## 参照  
 [MFC ツール バーの実装](../mfc/mfc-toolbar-implementation.md)