---
title: "AFX メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SB_LINELEFT
- SB_THUMBTRACK
- AFX_TOOLTIP_TYPE_EDIT
- AFX_WM_ON_HSCROLL
- SB_PAGERIGHT
- AFX_WM_RESETPROMPT
- AFX_WM_CHANGE_RIBBON_CATEGORY
- AFX_TOOLTIP_TYPE_MINIFRAME
- AFX_WM_CUSTOMIZETOOLBAR
- AFX_WM_CHANGE_ACTIVE_TAB
- AFX_WM_ACCGETOBJECT
- AFX_WM_TOOLBARMENU
- AFX_TOOLTIP_TYPE_DOCKBAR
- AFX_WM_CUSTOMIZEHELP
- AFX_WM_ON_GET_TAB_TOOLTIP
- AFX_WM_ON_RIBBON_CUSTOMIZE
- AFX_WM_ON_DRAGCOMPLETE
- AFX_WM_RESETTOOLBAR
- AFX_WM_ON_MOVETOTABGROUP
- AFX_WM_CHECKEMPTYMINIFRAME
- AFX_WM_GETDOCUMENTCOLORS
- SB_RIGHT
- AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU
- AFX_WM_ACCGETSTATE
- SB_PAGELEFT
- SB_ENDSCROLL
- AFX_WM_ON_CANCELTABMOVE
- AFX_TOOLTIP_TYPE_TAB
- AFX_WM_WINDOW_HELP
- AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM
- AFX_WM_SHOWREGULARMENU
- AFX_TOOLTIP_TYPE_TOOLBAR
- AFX_WM_CHANGE_CURRENT_FOLDER
- AFX_WM_UPDATETOOLTIPS
- AFX_WM_ON_MOVE_TAB
- AFX_WM_CHANGING_ACTIVE_TAB
- AFX_WM_RESETMENU
- AFX_WM_GETDRAGBOUNDS
- AFX_WM_RESETCONTEXTMENU
- AFX_TOOLTIP_TYPE_BUTTON
- AFX_WM_ON_CLOSEPOPUPWINDOW
- AFX_TOOLTIP_TYPE_TOOLBOX
- AFX_WM_CHANGEVISUALMANAGER
- SB_LINERIGHT
- AFX_WM_ON_RENAME_TAB
- AFX_TOOLTIP_TYPE_DEFAULT
- AFX_WM_ON_TABGROUPMOUSEMOVE
- SB_LEFT
- AFX_WM_DELETETOOLBAR
- AFX_WM_PROPERTY_CHANGED
- AFX_TOOLTIP_TYPE_ALL
- AFX_WM_ACCHITTEST
- AFX_WM_ON_AFTER_SHELL_COMMAND
- AFX_WM_ON_PRESS_CLOSE_BUTTON
- AFX_WM_RESETKEYBOARD
- AFX_WM_ON_MOVETABCOMPLETE
- AFX_WM_CREATETOOLBAR
- SB_THUMBPOSITION
- AFX_WM_POSTSETPREVIEWFRAME
dev_langs:
- C++
helpviewer_keywords:
- AFX messages
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: f9e63f47a8df69b52a6a12688e84602981d20dae
ms.openlocfilehash: 345c84e763d82cd8d13fc842dc57c49f133e39f0
ms.lasthandoff: 03/21/2017

---
# <a name="afx-messages"></a>AFX メッセージ
これらのメッセージは、MFC で使用されます。  
  
## <a name="messages"></a>[メッセージ]  
 次の表には、MFC ライブラリで使用されているメッセージが表示されます。  
  
||||||  
|-|-|-|-|-|  
|メッセージ|説明|[入力] `wParam`|`lParam`(すべてのパラメーターは [in] 特に明記しない限り) です。|戻り値|  
|AFX_WM_ACCGETOBJECT|使用しません。|使用しません。|該当なし。|該当なし。|  
|AFX_WM_ACCGETSTATE|ユーザー補助のサポートに使用されます。 このメッセージを送信`CMFCPopupMenu`または`CMFCRibbonPanelMenu`現在の要素の状態を取得します。|メニュー ボタンまたは区切り記号である可能性がある要素のインデックス。|使用しません。|Elementâ€™ 状態です。 インデックスが有効でない場合は-1 メニューのボタンは特別な属性を持たない場合は 0 です。 それ以外の場合に、次のフラグの組み合わせです。<br /><br /> TBBS_DISABLED â €"項目が無効になっています<br /><br /> TBBS_CHECKED â €"アイテムのチェック<br /><br /> TBBS_BUTTON â €"項目が標準のプッシュ ボタン<br /><br /> TBBS_PRESSED â €"ボタンが押される<br /><br /> TBBS_INDETERMINATE â €"未定義の状態<br /><br /> TBBS_SEPARATOR - メニュー ボタンでは、この要素形式は、他のメニュー項目間の分離|  
|AFX_WM_CHANGE_ACTIVE_TAB|フレームワークは、このメッセージをサイズ変更可能なコントロール バーのコントロールに送信します。 通知を受信するには、このメッセージを処理`CMFCTabCtrl`オブジェクトをユーザーには、アクティブなタブが変更されたとき。|タブのインデックス。|使用しません。|0 以外。|  
|AFX_WM_CHANGE_CURRENT_FOLDER|フレームワークでは、このメッセージを送信の親に`CMFCShellListCtrl`ユーザーが、現在のフォルダーを変更するとき。|使用しません。|使用しません。|使用しません。|  
|AFX_WM_CHANGEVISUALMANAGER|フレームワークでは、現在のビジュアル マネージャーを変更したときに、すべてのフレーム ウィンドウにこのメッセージを送信します。 このメッセージに応答してでは、フレーム ウィンドウは、その領域を再計算し、必要に応じてその他のパラメーターを調整します。 このイベントを通知する必要がある場合は、アプリケーションで AFX_WM_CHANGEVISUALMANAGER メッセージを処理できます。 基本クラスのハンドラーを呼び出す必要があります (`OnChangeVisualManager`) フレームワークの内部であることを確認する処理は、このイベントが実行されます。|使用しません。|使用しません。|使用しません。|  
|AFX_WM_CHANGING_ACTIVE_TAB|親に送信される`CMFCTabCtrl`オブジェクトです。  通知を受信する場合は、このメッセージを処理`CMFCTabCtrl`オブジェクトをユーザーがタブをリセットします。|タブをアクティブ化のインデックス。|使用しません。|0 以外。|  
|AFX_WM_CHECKEMPTYMINIFRAME|内部使用のみ。|該当なし。|該当なし。|該当なし。|  
|AFX_WM_CREATETOOLBAR|送信された`CMFCToolBarsListPropertyPage`カスタマイズ プロセス中に、ユーザーが新しいツールバーを作成するとします。 カスタム CMFCToolBar から派生したオブジェクトのインスタンスを作成するには、このメッセージを処理することができます。 このメッセージを処理して、独自のツールバーを作成した場合は、既定のハンドラーに呼び出しを省略します。|使用しません。|ツールバーの名前を表す文字列へのポインター。|新しく作成したツールバーへのポインター。 NULL では、ツールバーの作成が取り消されたことを示します。|  
|AFX_WM_CUSTOMIZEHELP|カスタマイズのプロパティ シートからメイン フレーム ウィンドウに送信される`CMFCToolbarCustomize``Dialog`押されたとき、**ヘルプ**ボタンまたは F1 キーを押す。|カスタマイズのプロパティ シートの現在のページを指定します。|ポインター、`CMFCToolbarCustomize``Dialog`オブジェクトです。|0 を返します。|  
|AFX_WM_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize``Dialog`にユーザーが新しいツールバーを作成している親フレームを通知するには、このメッセージを送信します。|`TRUE`カスタマイズが開始されると、`FALSE`カスタマイズが完了するとします。|使用しません。|0 を返します。|  
|AFX_WM_DELETETOOLBAR|ユーザーがカスタマイズ モードでツールバーを削除しようとしているときに、メイン フレーム ウィンドウに送信されます。<br /><br /> ユーザーがカスタマイズ モードでツールバーを削除すると、多くのアクションを実行するには、このメッセージを処理します。 また、既定のハンドラーを呼び出す必要があります (`OnToolbarDelete`)、ツールバーを削除します。 既定のハンドラーでは、ツールバーを削除することであるかどうかを示す値を返します。|使用しません。|ポインター、`CMFCToolBar`削除するオブジェクト。|0 以外の場合、ツールバーを削除できません。それ以外の場合 0 を返します。|  
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton`ドキュメントの色を取得するメイン フレーム ウィンドウには、このメッセージを送信します。|使用しません。|[入力、出力]ポインター、`CList<COLORREF, COLORREF>`オブジェクトです。|0 を返します。|  
|AFX_WM_GETDRAGBOUNDS|内部使用のみ。|該当なし。|該当なし。|該当なし。|  
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|ユーザーがリボン リスト項目を強調表示したときに、メイン フレーム ウィンドウに送信されます。|強調表示されている項目のインデックス|ポインター`CMFCBaseRibbonElement`|使用しません。|  
|AFX_WM_ON_AFTER_SHELL_COMMAND|親に送信される`CMFCShellListCtrl`または`CMFCShellTreeCtrl`ユーザーのシェル コマンドの実行が終了したときを制御します。|ユーザーが実行したコマンドの ID|使用しません。|アプリケーションでは、このメッセージを処理する場合は&0; を返します。|  
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|フレームワークでは、ポップアップ メニューが表示される前に、リボンの親にこのメッセージを送信します。 このメッセージを処理し、ポップアップ メニューをいつでも変更できます。|使用しません。|ポインター`CMFCBaseRibbonElement`|使用しません。|  
|AFX_WM_ON_CANCELTABMOVE|内部使用のみ。|該当なし。|該当なし。||  
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|フレームワークでは、アクティブなリボン コントロール カテゴリを変更したときをメインフレームにこのメッセージを送信します。|使用しません。|ポインター、`CMFCRibbonBar`のカテゴリが変更されています。|使用しません。|  
|AFX_WM_ON_CLOSEPOPUPWINDOW|フレームワークの所有者に通知するには、このメッセージを送信`CMFCDesktopAlertWnd`ウィンドウの期限が終了することです。|使用しません。|ポインター`CMFCDesktopAlertWnd`オブジェクトです。|使用しません。|  
|AFX_WM_ON_DRAGCOMPLETE|内部使用のみ。|該当なし。|該当なし。|該当なし。|  
|AFX_WM_ON_GET_TAB_TOOLTIP|タブ期間は、カスタム ツール ヒントが有効になっている場合、タブのツールヒントを表示しようとしていますが、メイン フレーム ウィンドウに送信されます。|使用しません。|ポインター、`CMFCTabToolTipInfo`構造体。|使用しません。|  
|AFX_WM_ON_HSCROLL|サイズ変更可能なコントロール バーのコントロールに送信されます。 通知を受信するには、このメッセージを処理`CMFCTabCtrl`タブ ウィジェットの水平スクロール バーのスクロール イベントが発生したときのオブジェクトします。|下位ワードは、スクロール バーの値をユーザーを示すには要求のスクロールを指定します。  詳細については、このトピックで後に示す表を参照してください。|使用しません。|0 以外。|  
|AFX_WM_ON_MOVE_TAB|新しい位置にタブをドラッグすると、タブ付きウィンドウの親に送信されます。|元の位置でタブの&0; から始まるインデックス。|[out]タブの新しい位置の&0; から始まるインデックス。|0 を返します。|  
|AFX_WM_ON_MOVETABCOMPLETE|内部使用のみ。|該当なし。|該当なし。|該当なし。|  
|AFX_WM_ON_MOVETOTABGROUP|ユーザーでは、1 つのタブ付きグループ間 MDI 子ウィンドウを移動するときに、メイン フレーム ウィンドウに送信されます。|タブ付きウィンドウを識別するハンドル (`CMFCTabCtrl`) MDI 子ウィンドウが削除されています。|[out]タブ付きウィンドウを識別するハンドル (`CMFCTabCtrl`) MDI 子ウィンドウに挿入されました。|無視されます。|  
|AFX_WM_ON_PRESS_CLOSE_BUTTON|親に送信される`CDockablePane`ユーザーがクリックしたとき、**閉じる**コントロール バーのキャプション ボタンをクリックします。|使用しません。|ユーザーがクリックすると、ドッキング可能ペインへのポインター、**閉じる** ボタンをクリックします。|`TRUE`場合は、ウィンドウを閉じることができません。それ以外の場合は FALSE。|  
|AFX_WM_ON_RENAME_TAB|ユーザーが編集可能なタブを名前変更後に、タブ付きウィンドウの親に送信されます。|名前を変更したタブの&0; から始まるインデックス。|[out]新しいタブ名を含む文字列へのポインター。|アプリケーションは、このメッセージを処理する場合は&0; 以外。フレームワークがへの呼び出しを抑制する`CMFCBaseTabCtrl::SetTabLabel`です。  場合は、0 が返される`CMFCBaseTabCtrl::SetTabLabel`はフレームワークによって呼び出されます。|  
|AFX_WM_ON_RIBBON_CUSTOMIZE|ユーザーのカスタマイズの開始時に、親のフレームに送信されます。 カスタマイズ ダイアログ ボックスを表示する場合は、このメッセージを処理します。|使用しません。|コントロールへのポインター、リボンをカスタマイズできます。|以外の場合は、アプリケーションは、このメッセージを処理し、独自のカスタマイズ ダイアログ ボックスが表示されます。 アプリケーションが&0; を返す場合、フレームワークによって、組み込みのカスタマイズ ダイアログ ボックスが表示されます。|  
|AFX_WM_ON_TABGROUPMOUSEMOVE|内部使用のみ。|該当なし。|該当なし。|該当なし。|  
|AFX_WM_POSTSETPREVIEWFRAME|ユーザーが印刷プレビュー モードを変更したメイン フレームに通知されます。|`TRUE`印刷プレビュー モードが設定されていることを示します。 `FALSE`その印刷プレビュー モードがオフを示します。|使用しません。|使用しません。|  
|AFX_WM_PROPERTY_CHANGED|プロパティ グリッド コントロールの所有者に送信された (`CMFCPropertyGridCtrl`)、ユーザーが選択されているプロパティの値を変更するとします。|プロパティ リストのコントロールの ID。|プロパティへのポインター (`CMFCProp``ertyGridProperty`) に変更します。|使用しません。|  
|AFX_WM_RESETCONTEXTMENU|ユーザーがカスタマイズするときに、コンテキスト メニューをリセットしたときに、メイン フレーム ウィンドウに送信されます。|コンテキスト メニューのリソース ID です。|現在のコンテキスト メニューへのポインター`CMFCPopupMenu`します。|使用しません。|  
|AFX_WM_RESETKEYBOARD|フレームワークでは、ユーザーがカスタマイズ中にすべてのキーボード アクセラレータをリセットしたときに、このメッセージをメイン フレーム ウィンドウに送信します。|使用しません。|使用しません。|使用しません。|  
|AFX_WM_RESETMENU|フレームワークでは、このメッセージを送信] メニューの [所有者 (フレーム ウィンドウ) をカスタマイズするときに、ユーザーがアプリケーション フレーム メニューを再設定すると|メニュー リソースの id。|使用しません。|使用しません。|  
|AFX_WM_RESETPROMPT|フレームワークは、ツールバーからツールバーをユーザーのリセット ダイアログ ボックスをカスタマイズするときに、このメッセージを送信します。 既定のハンドラーでは、ユーザーがツールバーをリセットするかどうかを確認するメッセージ ボックスが表示されます。|使用しません。|使用しません。|使用しません。|  
|AFX_WM_RESETTOOLBAR|A`CMFCToolBar`ツールバーを復元すると、元の状態は、リソースから読み込まれたオブジェクトはこのメッセージを送信します。 ツール バー ボタンからそのクラスの派生を再挿入するには、このメッセージを処理`CMFCToolbarButton`します。 詳細については、「`CMFCToolbarComboBoxButton`」を参照してください。|状態が復元されたツールバーのリソース ID。|使用しません。|0 を返します。|  
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton`オブジェクトは、ユーザーが標準のメニュー ボタンをクリックすると、その所有者にこのメッセージを送信します。 使用するたびにこのメッセージの処理`CMFCToolbarMenuButton`ユーザーがボタンをクリックしたときに、ポップアップ メニューを表示します。|メッセージを送信するボタンのコマンド ID。|カーソルの画面座標。 下位ワードは、x 座標を指定します。 上位の単語では、y 座標を指定します。|使用しません。|  
|AFX_WM_TOOLBARMENU|クライアントまたはウィンドウの非クライアント領域にマウス ポインターを置いた状態でマウスの右ボタンを離したときに、メイン フレーム ウィンドウに送信されます。|使用しません。|マウス ポインターの画面座標。 下位ワードは、x 座標を指定します。 上位の単語では、y 座標を指定します。|アプリケーションは、このメッセージを処理する場合は&0;それ以外の場合、0 以外の値を設定します。|  
|AFX_WM_UPDATETOOLTIPS|ツールヒント コントロールを再作成することを示すために、すべてのツールヒントの所有者に送信されます。|このメッセージを処理するコントロールの型。 使用可能な値の一覧については、このトピックの後半の表を参照してください。|使用しません。|使用しません。|  
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog`ユーザーがクリックすると、このメッセージを親フレームを送信、**ヘルプ**クリックするかをクリックしてヘルプ モードに入った、**ヘルプ**キャプション ボタンまたは F1 キーを押す。|使用しません。|インスタンスへのポインター`CMFCWindowsManagerDialog`します。|使用しません。|  
  
 次の表に、値の下位ワードを`lParam`AFX_WM_HSCROLL メソッドのパラメーター。  
  
|||  
|-|-|  
|値|説明|  
|SB_ENDSCROLL|ユーザーがスクロールを終了します。|  
|SB_LEFT|ユーザーは、左上にスクロールします。|  
|SB_RIGHT|ユーザーは、右下にスクロールします。|  
|SB_LINELEFT|ユーザーは、1 つの単位で左側をスクロールします。|  
|SB_LINERIGHT|ユーザーは、1 つの単位で右にスクロールします。|  
|SB_PAGELEFT|ユーザーは、左ウィンドウの幅をスクロールします。|  
|SB_PAGERIGHT|ユーザーは、ウィンドウの幅によって右にスクロールします。|  
|SB_THUMBPOSITION|ユーザーがスクロール ボックス (つまみ) をドラッグし、マウス ボタンを解放します。 上位ワードは、ドラッグ操作の最後にスクロール ボックスの位置を示します。|  
|SB_THUMBTRACK|ユーザーがスクロール ボックスをドラッグします。 AFX_WM_ON_HSCROLL メッセージは、ユーザーがマウス ボタンを離すまでこの値を繰り返し送信されます。 上位ワードは、スクロール ボックスをドラッグして位置を示します。|  
  
> [!NOTE]
>  上位ワード、`lParam`下位ワードが SB_THUMBPOSITION または SB_THUMBTRACK の場合、パラメーターをスクロール ボックスの現在の位置を指定します。 それ以外の場合、この単語は使用されません。  
  
 次の表に、フラグの値、 `lParam` AFX_WM_UPDATETOOLTIPS メッセージのパラメーター。  
  
|||  
|-|-|  
|フラグ|値|  
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|  
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|  
|AFX_TOOLTIP_TYPE_TAB|0x0004|  
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|  
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|  
|AFX_TOOLTIP_TYPE_EDIT|0x0020|  
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|  
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|  
|AFX_TOOLTIP_TYPE_ALL|0 xffff|  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

