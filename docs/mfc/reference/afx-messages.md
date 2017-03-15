---
title: "AFX メッセージ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SB_LINELEFT"
  - "SB_THUMBTRACK"
  - "AFX_TOOLTIP_TYPE_EDIT"
  - "AFX_WM_ON_HSCROLL"
  - "SB_PAGERIGHT"
  - "AFX_WM_RESETPROMPT"
  - "AFX_WM_CHANGE_RIBBON_CATEGORY"
  - "AFX_TOOLTIP_TYPE_MINIFRAME"
  - "AFX_WM_CUSTOMIZETOOLBAR"
  - "AFX_WM_CHANGE_ACTIVE_TAB"
  - "AFX_WM_ACCGETOBJECT"
  - "AFX_WM_TOOLBARMENU"
  - "AFX_TOOLTIP_TYPE_DOCKBAR"
  - "AFX_WM_CUSTOMIZEHELP"
  - "AFX_WM_ON_GET_TAB_TOOLTIP"
  - "AFX_WM_ON_RIBBON_CUSTOMIZE"
  - "AFX_WM_ON_DRAGCOMPLETE"
  - "AFX_WM_RESETTOOLBAR"
  - "AFX_WM_ON_MOVETOTABGROUP"
  - "AFX_WM_CHECKEMPTYMINIFRAME"
  - "AFX_WM_GETDOCUMENTCOLORS"
  - "SB_RIGHT"
  - "AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU"
  - "AFX_WM_ACCGETSTATE"
  - "SB_PAGELEFT"
  - "SB_ENDSCROLL"
  - "AFX_WM_ON_CANCELTABMOVE"
  - "AFX_TOOLTIP_TYPE_TAB"
  - "AFX_WM_WINDOW_HELP"
  - "AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM"
  - "AFX_WM_SHOWREGULARMENU"
  - "AFX_TOOLTIP_TYPE_TOOLBAR"
  - "AFX_WM_CHANGE_CURRENT_FOLDER"
  - "AFX_WM_UPDATETOOLTIPS"
  - "AFX_WM_ON_MOVE_TAB"
  - "AFX_WM_CHANGING_ACTIVE_TAB"
  - "AFX_WM_RESETMENU"
  - "AFX_WM_GETDRAGBOUNDS"
  - "AFX_WM_RESETCONTEXTMENU"
  - "AFX_TOOLTIP_TYPE_BUTTON"
  - "AFX_WM_ON_CLOSEPOPUPWINDOW"
  - "AFX_TOOLTIP_TYPE_TOOLBOX"
  - "AFX_WM_CHANGEVISUALMANAGER"
  - "SB_LINERIGHT"
  - "AFX_WM_ON_RENAME_TAB"
  - "AFX_TOOLTIP_TYPE_DEFAULT"
  - "AFX_WM_ON_TABGROUPMOUSEMOVE"
  - "SB_LEFT"
  - "AFX_WM_DELETETOOLBAR"
  - "AFX_WM_PROPERTY_CHANGED"
  - "AFX_TOOLTIP_TYPE_ALL"
  - "AFX_WM_ACCHITTEST"
  - "AFX_WM_ON_AFTER_SHELL_COMMAND"
  - "AFX_WM_ON_PRESS_CLOSE_BUTTON"
  - "AFX_WM_RESETKEYBOARD"
  - "AFX_WM_ON_MOVETABCOMPLETE"
  - "AFX_WM_CREATETOOLBAR"
  - "SB_THUMBPOSITION"
  - "AFX_WM_POSTSETPREVIEWFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX メッセージ"
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# AFX メッセージ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらのメッセージは、MFC で使用されます。  
  
## メッセージ  
 MFC ライブラリで使用されるメッセージを次の表に示します。  
  
||||||  
|-|-|-|-|-|  
|メッセージ|説明|\[入力\] `wParam`|`lParam` \(特に明記されていない限り、すべてのパラメーターは \[入力\] です\)|戻り値|  
|AFX\_WM\_ACCGETOBJECT|使用しません。|使用しません。|使用できません。|使用できません。|  
|AFX\_WM\_ACCGETSTATE|ユーザー補助のサポートに使用されます。  現在の要素の状態を取得するには、このメッセージを `CMFCPopupMenu` または `CMFCRibbonPanelMenu` に送信します。|要素のインデックス \(メニュー ボタンまたは区切り記号になります\)。|使用しません。|要素の状態。  インデックスが無効の場合は \-1。メニュー ボタンに特別な属性がない場合は 0。  それ以外の場合は、次のフラグの組み合わせです。<br /><br /> TBBS\_DISABLED – 項目は無効です。<br /><br /> TBBS\_CHECKED – 項目はチェックされています。<br /><br /> TBBS\_BUTTON – 項目は標準のプッシュ ボタンです。<br /><br /> TBBS\_PRESSED – ボタンは押された状態になっています。<br /><br /> TBBS\_INDETERMINATE – 未定義の状態です。<br /><br /> TBBS\_SEPARATOR \- メニュー ボタンではなく、この要素は他のメニュー項目を区切っています。|  
|AFX\_WM\_CHANGE\_ACTIVE\_TAB|フレームワークは、このメッセージをサイズ変更可能なコントロール バー コントロールに送信します。  ユーザーがアクティブなタブを変更したときに `CMFCTabCtrl` オブジェクトから通知を受け取るには、このメッセージを処理します。|タブのインデックス。|使用しません。|0 以外。|  
|AFX\_WM\_CHANGE\_CURRENT\_FOLDER|ユーザーが現在のフォルダーを変更すると、フレームワークはこのメッセージを `CMFCShellListCtrl` の親に送信します。|使用しません。|使用しません。|使用しません。|  
|AFX\_WM\_CHANGEVISUALMANAGER|ユーザーが現在のビジュアル マネージャーを変更すると、フレームワークはこのメッセージをすべてのフレーム ウィンドウに送信します。  このメッセージへの応答で、フレーム ウィンドウはその領域を再計算し、必要に応じて他のパラメーターを調整します。  このイベントに関する通知を受け取る場合は、アプリケーションで AFX\_WM\_CHANGEVISUALMANAGER メッセージを処理できます。  基本クラスのハンドラー \(`OnChangeVisualManager`\) を呼び出して、フレームワークによりこのイベントの内部処理が実行されるようにする必要があります。|使用しません。|使用しません。|使用しません。|  
|AFX\_WM\_CHANGING\_ACTIVE\_TAB|`CMFCTabCtrl` オブジェクトの親に送信されます。ユーザーがタブをリセットしたときに `CMFCTabCtrl` オブジェクトから通知を受け取る場合は、このメッセージを処理します。|アクティブになっているタブのインデックス。|使用しません。|0 以外。|  
|AFX\_WM\_CHECKEMPTYMINIFRAME|内部でのみ使用されます。|使用できません。|使用できません。|使用できません。|  
|AFX\_WM\_CREATETOOLBAR|ユーザーがカスタマイズ処理中に新しいツール バーを作成した場合に、`CMFCToolBarsListPropertyPage` から送信されます。  このメッセージを処理すると、カスタム CMFCToolBar 派生オブジェクトをインスタンス化できます。  このメッセージを処理して独自のツール バーを作成した場合は、既定のハンドラーの呼び出しを省略します。|使用しません。|ツール バーの名前を含む文字列へのポインター。|新しく作成されたツール バーへのポインター。  NULL は、ツール バーの作成がキャンセルされたことを示しています。|  
|AFX\_WM\_CUSTOMIZEHELP|ユーザーが **\[ヘルプ\]** ボタンまたは F1 キーを押したときに、カスタマイズ プロパティ シート `CMFCToolbarCustomize``Dialog` からメイン フレーム ウィンドウに送信されます。|カスタマイズ プロパティ シートのアクティブなページを指定します。|`CMFCToolbarCustomize` `Dialog` オブジェクトへのポインター。|ゼロ。|  
|AFX\_WM\_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize` `Dialog` は、ユーザーが新しいツール バーを作成したことを親フレームに通知するためにこのメッセージを送信します。|カスタマイズが開始された場合は `TRUE`。カスタマイズが終了した場合は `FALSE`。|使用しません。|ゼロ。|  
|AFX\_WM\_DELETETOOLBAR|ユーザーがカスタマイズ モードでツール バーを削除しようとしたときに、メイン フレーム ウィンドウに送信されます。<br /><br /> ユーザーがカスタマイズ モードでツール バーを削除するときに追加のアクションを実行するには、このメッセージを処理します。  さらに、ツール バーを削除する既定のハンドラー \(`OnToolbarDelete`\) も呼び出す必要があります。  既定のハンドラーは、ツール バーを削除できるかどうかを示す値を返します。|使用しません。|削除される `CMFCToolBar` オブジェクトへのポインター。|ツール バーを削除できない場合は 0 以外。それ以外の場合は 0。|  
|AFX\_WM\_GETDOCUMENTCOLORS|`CMFCColorMenuButton` は、ドキュメントの色を取得するために、このメッセージをメイン フレーム ウィンドウに送信します。|使用しません。|\[入力、出力\] `CList<COLORREF, COLORREF>` オブジェクトへのポインター。|ゼロ。|  
|AFX\_WM\_GETDRAGBOUNDS|内部でのみ使用されます。|使用できません。|使用できません。|使用できません。|  
|AFX\_WM\_HIGHLIGHT\_RIBBON\_LIST\_ITEM|ユーザーがリボン リスト項目を強調表示したときに、メイン フレーム ウィンドウに送信されます。|強調表示された項目のインデックス。|`CMFCBaseRibbonElement` へのポインター。|使用しません。|  
|AFX\_WM\_ON\_AFTER\_SHELL\_COMMAND|ユーザーがシェル コマンドの実行を完了したときに、`CMFCShellListCtrl` コントロールまたは `CMFCShellTreeCtrl` コントロールの親に送信されます。|ユーザーが実行したコマンドの ID。|使用しません。|アプリケーションがこのメッセージを処理する場合は、0 を返します。|  
|AFX\_WM\_ON\_BEFORE\_SHOW\_RIBBON\_ITEM\_MENU|フレームワークは、ポップアップ メニューが表示される前にこのメッセージをリボンの親に送信します。  いつでもこのメッセージを処理して、ポップアップ メニューを変更できます。|使用しません。|`CMFCBaseRibbonElement` へのポインター。|使用しません。|  
|AFX\_WM\_ON\_CANCELTABMOVE|内部でのみ使用されます。|使用できません。|使用できません。||  
|AFX\_WM\_ON\_CHANGE\_RIBBON\_CATEGORY|ユーザーがアクティブなリボン コントロール カテゴリを変更すると、フレームワークはこのメッセージをメイン フレームに送信します。|使用しません。|カテゴリが変更された `CMFCRibbonBar` へのポインター。|使用しません。|  
|AFX\_WM\_ON\_CLOSEPOPUPWINDOW|フレームワークは、ウィンドウが閉じられようとしていることを、`CMFCDesktopAlertWnd` のオーナーに通知するために、このメッセージを送信します。|使用しません。|`CMFCDesktopAlertWnd` オブジェクトへのポインター。|使用しません。|  
|AFX\_WM\_ON\_DRAGCOMPLETE|内部でのみ使用されます。|使用できません。|使用できません。|使用できません。|  
|AFX\_WM\_ON\_GET\_TAB\_TOOLTIP|カスタム ツールヒントが有効な場合、タブのツールヒントがタブ ウィンドウに表示されようとしたときに、メイン フレーム ウィンドウに送信されます。|使用しません。|`CMFCTabToolTipInfo` 構造体へのポインター。|使用しません。|  
|AFX\_WM\_ON\_HSCROLL|サイズ変更可能なコントロール バー コントロールに送信されます。  タブ付きウィジェット水平スクロール バーでスクロール イベントが発生したときに、`CMFCTabCtrl` オブジェクトから通知を受け取る場合には、このメッセージを処理します。|下位ワードは、ユーザーのスクロール要求を示すスクロール バー値を指定します。詳細については、このトピックで後に示す表を参照してください。|使用しません。|0 以外。|  
|AFX\_WM\_ON\_MOVE\_TAB|ユーザーがタブを新しい位置にドラッグしたときに、タブ付きウィンドウの親に送信されます。|元の位置にあるタブの 0 から始まるインデックス。|\[出力\] 新しい位置にあるタブの 0 から始まるインデックス。|ゼロ。|  
|AFX\_WM\_ON\_MOVETABCOMPLETE|内部でのみ使用されます。|使用できません。|使用できません。|使用できません。|  
|AFX\_WM\_ON\_MOVETOTABGROUP|ユーザーが MDI 子ウィンドウをあるタブ付きグループから別のタブ付きグループに移動したときに、メイン フレーム ウィンドウに送信されます。|MDI 子ウィンドウが削除されたタブ付きウィンドウ \(`CMFCTabCtrl`\) へのハンドル。|\[出力\] MDI 子ウィンドウが挿入されたタブ付きウィンドウ \(`CMFCTabCtrl`\) へのハンドル。|無視されます。|  
|AFX\_WM\_ON\_PRESS\_CLOSE\_BUTTON|ユーザーがコントロール バーのキャプションの閉じるボタンをクリックしたときに、`CDockablePane` の親に送信されます。|使用しません。|ユーザーが閉じるボタンをクリックしたドッキング可能ペインへのポインター。|ペインを閉じることができない場合は `TRUE`。それ以外の場合は FALSE。|  
|AFX\_WM\_ON\_RENAME\_TAB|ユーザーが編集可能なタブの名前を変更した後、タブ付きウィンドウの親に送信されます。|名前が変更されたタブの 0 から始まるインデックス。|\[出力\] 新しいタブ名を含む文字列へのポインター。|アプリケーションがこのメッセージを処理する場合は 0 以外。フレームワークは、`CMFCBaseTabCtrl::SetTabLabel` の呼び出しを抑制します。ゼロが返された場合、`CMFCBaseTabCtrl::SetTabLabel` はフレームワークによって呼び出されます。|  
|AFX\_WM\_ON\_RIBBON\_CUSTOMIZE|ユーザーがカスタマイズを開始したときに、親フレームに送信されます。  独自のカスタマイズ ダイアログ ボックスを表示する場合は、このメッセージを処理します。|使用しません。|カスタマイズするリボン コントロールへのポインター。|アプリケーションがこのメッセージを処理して、独自のカスタマイズ ダイアログ ボックスを表示する場合は、0 以外。  アプリケーションが 0 を返す場合、フレームワークは組み込みのカスタマイズ ダイアログ ボックスを表示します。|  
|AFX\_WM\_ON\_TABGROUPMOUSEMOVE|内部でのみ使用されます。|使用できません。|使用できません。|使用できません。|  
|AFX\_WM\_POSTSETPREVIEWFRAME|ユーザーが印刷プレビュー モードを変更したときに、メイン フレームに通知するために送信されます。|`TRUE` は、印刷プレビュー モードが設定されていることを示します。  `FALSE` は、印刷プレビュー モードがオフになっていることを示します。|使用しません。|使用しません。|  
|AFX\_WM\_PROPERTY\_CHANGED|ユーザーが選択されたプロパティの値を変更したときに、プロパティ グリッド コントロールのオーナー \(`CMFCPropertyGridCtrl`\) に送信されます。|プロパティ リストのコントロール ID。|変更されたプロパティ \(`CMFCProp``ertyGridProperty`\) へのポインター。|使用しません。|  
|AFX\_WM\_RESETCONTEXTMENU|ユーザーがカスタマイズ中にコンテキスト メニューをリセットしたときに、メイン フレーム ウィンドウに送信されます。|コンテキスト メニューのリソース ID。|現在のコンテキスト メニュー `CMFCPopupMenu` へのポインター。|使用しません。|  
|AFX\_WM\_RESETKEYBOARD|ユーザーがカスタマイズ中にすべてのキーボード アクセラレータをリセットすると、フレームワークはこのメッセージをメイン フレーム ウィンドウに送信します。|使用しません。|使用しません。|使用しません。|  
|AFX\_WM\_RESETMENU|ユーザーがカスタマイズ中にアプリケーション フレーム メニューをリセットすると、フレームワークはこのメッセージをメニューのオーナー \(フレーム ウィンドウ\) に送信します。|メニュー リソース ID。|使用しません。|使用しません。|  
|AFX\_WM\_RESETPROMPT|ユーザーがツール バーのカスタマイズ ダイアログ ボックスからツール バーをリセットすると、フレームワークはこのメッセージを送信します。  既定のハンドラーは、ユーザーにツール バーをリセットするかどうかの確認を求めるメッセージ ボックスを表示します。|使用しません。|使用しません。|使用しません。|  
|AFX\_WM\_RESETTOOLBAR|ツール バーが元の状態に復元される \(つまり、リソースから読み込まれる\) と、`CMFCToolBar` オブジェクトはこのメッセージを送信します。  クラスが `CMFCToolbarButton` から派生したツール バー ボタンを挿入し直すには、このメッセージを処理します。  詳細については、「`CMFCToolbarComboBoxButton`」を参照してください。|状態が復元されたツール バーのリソース ID。|使用しません。|ゼロ。|  
|AFX\_WM\_SHOWREGULARMENU|ユーザーが標準のメニュー ボタンをクリックすると、`CMFCToolbarMenuButton` オブジェクトはこのメッセージをそのオーナーに送信します。  ユーザーがボタンをクリックしたときに `CMFCToolbarMenuButton` を使用してポップアップ メニューを表示するたびに、このメッセージを処理します。|メッセージを送信するボタンのコマンド ID。|カーソルの画面座標。  下位ワードは、x 座標を指定します。  上位ワードは、y 座標を指定します。|使用しません。|  
|AFX\_WM\_TOOLBARMENU|マウス ポインターがペインのクライアント領域または非クライアント領域にあるときに、ユーザーがマウスの右ボタンを離すと、メイン フレーム ウィンドウに送信されます。|使用しません。|マウス ポインターの画面座標。  下位ワードは、x 座標を指定します。  上位ワードは、y 座標を指定します。|アプリケーションがこのメッセージを処理する場合は 0。それ以外の場合は 0 以外。|  
|AFX\_WM\_UPDATETOOLTIPS|ツールヒント コントロールを再作成する必要があることを示すために、すべてのツールヒントのオーナーに送信されます。|このメッセージを処理する必要があるコントロールの型。  使用できる値の一覧は、このトピックで後に示す表を参照してください。|使用しません。|使用しません。|  
|AFX\_WM\_WINDOW\_HELP|ユーザーが **\[ヘルプ\]** ボタンをクリックしたとき、つまり、**\[ヘルプ\]** キャプション ボタンまたは F1 キーをクリックすることによりヘルプ モードに入ったときに、`CMFCWindowsManagerDialog` はこのメッセージを親フレームに送信します。|使用しません。|`CMFCWindowsManagerDialog` のインスタンスへのポインター。|使用しません。|  
  
 AFX\_WM\_HSCROLL メソッドの `lParam` パラメーターの下位ワードの値を次の表に示します。  
  
|||  
|-|-|  
|値|説明|  
|SB\_ENDSCROLL|ユーザーがスクロールを終了するとき。|  
|SB\_LEFT|ユーザーが左上にスクロールするとき。|  
|SB\_RIGHT|ユーザーが右下にスクロールするとき。|  
|SB\_LINELEFT|ユーザーが 1 単位左にスクロールするとき。|  
|SB\_LINERIGHT|ユーザーが 1 単位右にスクロールするとき。|  
|SB\_PAGELEFT|ユーザーがウィンドウの幅ごとに左にスクロールするとき。|  
|SB\_PAGERIGHT|ユーザーがウィンドウの幅ごとに右にスクロールするとき。|  
|SB\_THUMBPOSITION|ユーザーがスクロール ボックス \(つまみ\) をドラッグし、マウス ボタンを離したとき。  上位ワードは、ドラッグ操作の終点のスクロール ボックスの位置を示します。|  
|SB\_THUMBTRACK|ユーザーがスクロール ボックスをドラッグしている間。  ユーザーがマウス ボタンを離すまで、AFX\_WM\_ON\_HSCROLL メッセージはこの値で繰り返し送信されます。  上位ワードは、スクロール ボックスがドラッグされた位置を示します。|  
  
> [!NOTE]
>  下位ワードが SB\_THUMBPOSITION または SB\_THUMBTRACK の場合、`lParam` パラメーターの上位ワードはスクロール ボックスの現在の位置を指定します。それ以外の場合は、このワードは使用されません。  
  
 AFX\_WM\_UPDATETOOLTIPS メッセージの `lParam` パラメーターのフラグ値を次の表に示します。  
  
|||  
|-|-|  
|フラグ|値|  
|AFX\_TOOLTIP\_TYPE\_DEFAULT|0x0001|  
|AFX\_TOOLTIP\_TYPE\_TOOLBAR|0x0002|  
|AFX\_TOOLTIP\_TYPE\_TAB|0x0004|  
|AFX\_TOOLTIP\_TYPE\_MINIFRAME|0x0008|  
|AFX\_TOOLTIP\_TYPE\_DOCKBAR|0x0010|  
|AFX\_TOOLTIP\_TYPE\_EDIT|0x0020|  
|AFX\_TOOLTIP\_TYPE\_BUTTON|0x0040|  
|AFX\_TOOLTIP\_TYPE\_TOOLBOX|0x0080|  
|AFX\_TOOLTIP\_TYPE\_ALL|0xFFFF|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)