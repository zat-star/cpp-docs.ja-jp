---
title: "チュートリアル: ツール バーへのコントロールの追加 | Microsoft Docs"
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
  - "[ユーザー設定] ダイアログ ボックス, 追加 (コントロールを)"
  - "ツール バー, 追加 (コントロールを)"
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# チュートリアル: ツール バーへのコントロールの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、Windows コントロールを含むツール バー ボタンをツール バーに追加する方法を説明します。  MFC では、ツール バー ボタンは、[CMFCToolBarButton クラス](../mfc/reference/cmfctoolbarbutton-class.md) の派生クラス、たとえば、[CMFCToolBarComboBoxButton クラス](../Topic/CMFCToolBarComboBoxButton%20Class.md), [CMFCToolBarEditBoxButton クラス](../Topic/CMFCToolBarEditBoxButton%20Class.md)、[CMFCDropDownToolbarButton クラス](../mfc/reference/cmfcdropdowntoolbarbutton-class.md)、[CMFCToolBarMenuButton クラス](../mfc/reference/cmfctoolbarmenubutton-class.md) などであることが必要です。  
  
## ツール バーへのコントロールの追加  
 ツール バーにコントロールを追加するには、次の手順を実行します。  
  
1.  親ツール バー リソースでボタンのダミー リソース ID を予約します。  Visual Studio でツール バー エディターを使用してボタンを作成する方法の詳細については、「[Toolbar Editor](../mfc/toolbar-editor.md)」を参照してください。  
  
2.  親ツール バーのすべてのビットマップでボタンのツール バー イメージ \(ボタン アイコン\) を予約します。  
  
3.  `AFX_WM_RESETTOOLBAR` メッセージを処理するメッセージ ハンドラーで、次の操作を行います。  
  
    1.  `CMFCToolbarButton` 派生クラスを使用して、ボタン コントロールを作成します。  
  
    2.  [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) を使用して、ダミー ボタンを新しいコントロールに置き換えます。  `ReplaceButton` はボタン オブジェクトをコピーしてそのコピーを保持するため、開発者はスタックでボタン オブジェクトを作成できます。  
  
> [!NOTE]
>  アプリケーションでカスタマイズを有効にしているとき、再コンパイル後に更新したコントロールがアプリケーションのツール バーに表示されるようにするには、**\[カスタマイズ\]** ダイアログ ボックスの **\[ツール バー\]** タブの **\[リセット\]** ボタンを使用して、ツール バーをリセットすることが必要になる場合があります。  ツール バーの状態は Windows レジストリに保存され、アプリケーションの起動中に `ReplaceButton` メソッドが実行された後、レジストリ情報が読み込まれ適用されます。  
  
## ツール バー コントロールとカスタマイズ  
 **\[カスタマイズ\]** ダイアログ ボックスの **\[コマンド\]** タブには、アプリケーションで使用できるコマンドの一覧が表示されます。  既定では、**\[カスタマイズ\]** ダイアログ ボックスはアプリケーション メニューを処理し、各メニュー カテゴリで標準ツール バー ボタンの一覧を作成します。  ツール バー コントロールが提供する拡張機能を保持するには、**\[カスタマイズ\]** ダイアログ ボックスで、標準ツール バー ボタンをカスタム コントロールに置き換える必要があります。  
  
 カスタマイズを有効にする場合は、[CMFCToolBarsCustomizeDialog クラス](../mfc/reference/cmfctoolbarscustomizedialog-class.md) クラスを使用して、カスタマイズ ハンドラー `OnViewCustomize` で **\[カスタマイズ\]** ダイアログ ボックスを作成します。  [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md) を呼び出して **\[カスタマイズ\]** ダイアログ ボックスを表示する前に、[CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md) を呼び出して、標準のボタンを新しいコントロールに置き換えます。  
  
## 例 : \[Find\] コンボ ボックスの作成  
 ここでは、`Find` コンボ ボックスを作成する方法について説明します。このコンボ ボックスはツール バーに表示され、最近使用した検索文字列が表示されます。  ユーザーはコントロールに文字列を入力した後、Enter キーを押してドキュメントを検索するか、Esc キーを押してフォーカスをメイン フレームに戻します。  ここでは、ドキュメントが [CEditView クラス](../Topic/CEditView%20Class.md) 派生ビューに表示されていることを前提としています。  
  
### Find コントロールの作成  
 まず、`Find` コンボ ボックス コントロールを作成します。  
  
1.  アプリケーション リソースにボタンとコマンドを追加します。  
  
    1.  アプリケーション リソースで、`ID_EDIT_FIND` コマンド ID を持つ新しいボタンをアプリケーションのツール バー、およびツール バーに関連付けられたビットマップに追加します。  
  
    2.  ID\_EDIT\_FIND コマンド ID を使用して新しいメニュー項目を作成します。  
  
    3.  新しい文字列 "Find the text\\nFind" を文字列テーブルに追加し、`ID_EDIT_FIND_COMBO` コマンド ID を割り当てます。  この ID は、`Find` コンボ ボックスのコマンド ID として使用されます。  
  
        > [!NOTE]
        >  `ID_EDIT_FIND` は `CEditView` によって処理される標準のコマンドであるため、このコマンド用の特別なハンドラーを実装する必要はありません。ただし、新しいコマンド `ID_EDIT_FIND_COMBO` のハンドラーを実装する必要があります。  
  
2.  [CComboBox クラス](../mfc/reference/ccombobox-class.md) から派生した新しい `CFindComboBox` クラスを作成します。  
  
3.  `CFindComboBox` クラスで、`PreTranslateMessage` 仮想メソッドをオーバーライドします。  このメソッドにより、コンボ ボックスは [WM\_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) メッセージを処理できます。  ユーザーが Esc キーを押す \(`VK_ESCAPE`\) と、フォーカスがメイン フレーム ウィンドウに戻ります。  ユーザーが Enter キーを押す \(`VK_ENTER`\) と、`ID_EDIT_FIND_COMBO` コマンド ID を含む `WM_COMMAND` メッセージがメイン フレーム ウィンドウにポストされます。  
  
4.  [CMFCToolBarComboBoxButton クラス](../Topic/CMFCToolBarComboBoxButton%20Class.md) から派生した `Find` コンボ ボックス ボタンのクラスを作成します。  この例では、`CFindComboButton` という名前が付いています。  
  
5.  `CMFCToolbarComboBoxButton` のコンストラクターは、3 つのパラメーター \(ボタンのコマンド ID、ボタン イメージのインデックス、およびコンボ ボックスのスタイル\) を受け取ります。  これらのパラメーターを次のように設定します。  
  
    1.  `ID_EDIT_FIND_COMBO` をコマンド ID として渡します。  
  
    2.  [CCommandManager::GetCmdImage](http://msdn.microsoft.com/ja-jp/4094d08e-de74-4398-a483-76d27a742dca) を `ID_EDIT_FIND` と共に使用して、イメージのインデックスを取得します。  
  
    3.  使用可能なコンボ ボックス スタイルの一覧については、「[コンボ ボックス スタイル](../mfc/reference/combo-box-styles.md)」を参照してください。  
  
6.  `CFindComboButton` クラスで、`CMFCToolbarComboBoxButton::CreateCombo` メソッドをオーバーライドします。  ここで、`CFindComboButton` オブジェクトを作成し、オブジェクトへのポインターを返す必要があります。  
  
7.  コンボ ボタンを永続化するには、[IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) マクロを使用します。  ワークスペース マネージャーは、ボタンの状態を自動的に読み込み、Windows レジストリに保存します。  
  
8.  ドキュメント ビューで `ID_EDIT_FIND_COMBO` ハンドラーを実装します。  すべての `Find` コンボ ボックス ボタンを取得するには、[CMFCToolBar::GetCommandButtons](../Topic/CMFCToolBar::GetCommandButtons.md) を `ID_EDIT_FIND_COMBO` と共に使用します。  カスタマイズにより、同じコマンド ID を持つ複数のボタンが存在する可能性があります。  
  
9. ID\_EDIT\_FIND メッセージ ハンドラー `OnFind` で、[CMFCToolBar::IsLastCommandFromButton](../Topic/CMFCToolBar::IsLastCommandFromButton.md) を使用して、検索コマンドが `Find` コンボ ボックスから送信されたかどうかを判断します。  該当する場合は、テキストを検索し、検索文字列をコンボ ボックスに追加します。  
  
### メイン ツール バーへの Find コントロールの追加  
 ツール バーにコンボ ボックス ボタンを追加するには、次の手順を実行します。  
  
1.  メイン フレーム ウィンドウに `AFX_WM_RESETTOOLBAR` メッセージ ハンドラー `OnToolbarReset` を実装します。  
  
    > [!NOTE]
    >  アプリケーションの起動中にツール バーが初期化されたとき、またはカスタマイズ中にツール バーがリセットされたときに、フレームワークはこのメッセージをメイン フレーム ウィンドウに送信します。  どちらの場合も、標準のツール バー ボタンをカスタム `Find` コンボ ボックス ボタンに置き換える必要があります。  
  
2.  `AFX_WM_RESETTOOLBAR` ハンドラーで、ツール バー ID、つまり `AFX_WM_RESETTOOLBAR` メッセージの `WPARAM` を確認します。  ツール バー ID が、`Find` コンボ ボックス ボタンを含むツール バーの ID と同じ場合、[CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) を呼び出して、`Find` ボタン \(コマンド ID が `ID_EDIT_FIND)` のボタン\) を `CFindComboButton` オブジェクトに置き換えます。  
  
    > [!NOTE]
    >  `ReplaceButton` はボタン オブジェクトをコピーしてそのコピーを保持するため、開発者はスタックで `CFindComboBox` オブジェクトを作成できます。  
  
### \[カスタマイズ\] ダイアログ ボックスへの Find コントロールの追加  
 カスタマイズ ハンドラー `OnViewCustomize` で、[CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md) を呼び出して、`Find` ボタン \(コマンド ID が `ID_EDIT_FIND)` のボタン\) を `CFindComboButton` オブジェクトに置き換えます。  
  
## 参照  
 [階層図](../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBar クラス](../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton クラス](../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton クラス](../Topic/CMFCToolBarComboBoxButton%20Class.md)   
 [CMFCToolBarsCustomizeDialog クラス](../mfc/reference/cmfctoolbarscustomizedialog-class.md)