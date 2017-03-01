---
title: "CWnd クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWnd
dev_langs:
- C++
helpviewer_keywords:
- windows [C++]
- window objects [C++]
- CWnd class
ms.assetid: 49a832ee-bc34-4126-88b3-bc1d9974f6c4
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ab9007e512f5af43bdace06796fb8487ffebc8e6
ms.lasthandoff: 02/24/2017

---
# <a name="cwnd-class"></a>CWnd クラス
Microsoft Foundation Class ライブラリにあるすべてのウィンドウ クラスの基本機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CWnd : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWnd::CWnd](#cwnd)|`CWnd` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWnd::accDoDefaultAction](#accdodefaultaction)|オブジェクトの既定のアクションを実行するために、フレームワークによって呼び出されます。|  
|[CWnd::accHitTest](#acchittest)|画面上の指定された位置にある子要素または子オブジェクトを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::accLocation](#acclocation)|指定されたオブジェクトの現在の画面位置を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::accNavigate](#accnavigate)|コンテナー内の他のユーザー インターフェイス要素を走査するため、可能な場合はそのオブジェクトを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::accSelect](#accselect)|選択を変更するため、または指定されたオブジェクトのキーボード フォーカスを移動するために、フレームワークによって呼び出されます。|  
|[CWnd::AnimateWindow](#animatewindow)|関連付けられたウィンドウ オブジェクトをアニメーション化します。|  
|[CWnd::ArrangeIconicWindows](#arrangeiconicwindows)|すべての最小化 (アイコン化) された子ウィンドウを整列します。|  
|[CWnd::Attach](#attach)|Windows ハンドルを `CWnd` オブジェクトに関連付けます。|  
|[CWnd::BeginModalState](#beginmodalstate)|フレーム ウィンドウをモーダルにします。|  
|[CWnd::BeginPaint](#beginpaint)|描画用の `CWnd` を準備します。|  
|[CWnd::BindDefaultProperty](#binddefaultproperty)|タイプ ライブラリに示されているように、呼び出し元オブジェクトの既定の単純バインド プロパティを、データ ソース コントロールに関連付けられているカーソルにバインドします。|  
|[Cwnd::bindproperty](#bindproperty)|データ バインディング コントロールのカーソル バインド プロパティをデータ ソース コントロールにバインドし、そのリレーションシップを MFC バインド マネージャーに登録します。|  
|[CWnd::BringWindowToTop](#bringwindowtotop)|`CWnd` を重なったウィンドウのスタックの最上位に移動します。|  
|[CWnd::CalcWindowRect](#calcwindowrect)|クライアントの四角形からウィンドウ四角形を計算するために呼び出されます。|  
|[CWnd::CancelToolTips](#canceltooltips)|ツール ヒント コントロールを無効にします。|  
|[CWnd::CenterWindow](#centerwindow)|ウィンドウをその親ウィンドウの中央に揃えます。|  
|[CWnd::ChangeClipboardChain](#changeclipboardchain)|クリップボード ビューアーのチェインから `CWnd` を削除します。|  
|[CWnd::CheckDlgButton](#checkdlgbutton)|チェック マークをボタン コントロールの横に配置したり、ボタン コントロールから削除したりします。|  
|[CWnd::CheckRadioButton](#checkradiobutton)|指定されたオプション ボタンにチェック マークを付け、指定されたボタンのグループにある他のすべてのオプション ボタンからチェック マークを削除します。|  
|[CWnd::ChildWindowFromPoint](#childwindowfrompoint)|子ウィンドウがある場合、指定された点を含む子ウィンドウを判断します。|  
|[CWnd::ClientToScreen](#clienttoscreen)|ディスプレイ上の指定された点または四角形のクライアント座標を画面座標に変換します。|  
|[CWnd::CloseWindow](#closewindow)|ウィンドウを最小化します。|  
|[CWnd::ContinueModal](#continuemodal)|ウィンドウのモーダル ステータスを継続します。|  
|[Cwnd::create](#create)|`CWnd` オブジェクトに関連付けられる子ウィンドウを作成し、初期化します。|  
|[CWnd::CreateAccessibleProxy](#createaccessibleproxy)|指定されたオブジェクトの Active Accessibility プロキシを作成します。|  
|[CWnd::CreateCaret](#createcaret)|システム キャレットの新しい形を作成し、そのキャレットの所有権を取得します。|  
|[Cwnd::createcontrol](#createcontrol)|MFC プログラムでは `CWnd` オブジェクトによって表される ActiveX コントロールを作成します。|  
|[とき](#createex)|Windows のオーバーラップ ウィンドウ、ポップアップ ウィンドウ、または子ウィンドウを作成し、`CWnd` オブジェクトに関連付けます。|  
|[CWnd::CreateGrayCaret](#creategraycaret)|灰色のブロックでシステム キャレットを作成し、そのキャレットの所有権を取得します。|  
|[CWnd::CreateSolidCaret](#createsolidcaret)|純色のブロックでシステム キャレットを作成し、そのキャレットの所有権を取得します。|  
|[CWnd::DeleteTempMap](#deletetempmap)|`FromHandle` 関数で作成した一時的な `CWnd` オブジェクトをすべて削除するために、`CWinApp` のアイドル処理ハンドラーによって自動的に呼び出されます。|  
|[に](#destroywindow)|関連付けられている Windows のウィンドウを破棄します。|  
|[CWnd::Detach](#detach)|`CWnd` オブジェクトから Windows のハンドルを切り離し、そのハンドルを返します。|  
|[CWnd::DlgDirList](#dlgdirlist)|リスト ボックスにファイル リストまたはディレクトリ リストを設定します。|  
|[CWnd::DlgDirListComboBox](#dlgdirlistcombobox)|コンボ ボックスにファイル リストまたはディレクトリ リストを設定します。|  
|[CWnd::DlgDirSelect](#dlgdirselect)|リスト ボックスから現在の選択を取得します。|  
|[CWnd::DlgDirSelectComboBox](#dlgdirselectcombobox)|コンボ ボックスから現在の選択を取得します。|  
|[CWnd::DragAcceptFiles](#dragacceptfiles)|ドラッグされたファイルがウィンドウで読み込まれることを示します。|  
|[CWnd::DragDetect](#dragdetect)|マウスをキャプチャし、ユーザーが左ボタンを離すか、Esc キーを押すか、または指定した点を中心にしたドラッグ四角形の外にマウスを移動するまで、移動を追跡します。|  
|[CWnd::DrawAnimatedRects](#drawanimatedrects)|アイコンを開く動作や、ウィンドウの最小化または最大化の動作を、ワイヤ フレームの四角形のアニメーションで表します。|  
|[CWnd::DrawCaption](#drawcaption)|キャプションを描画します。|  
|[かかわらず](#drawmenubar)|メニュー バーを再描画します。|  
|[CWnd::EnableActiveAccessibility](#enableactiveaccessibility)|ユーザー定義の `Active Accessibility` 関数を有効にします。|  
|[CWnd::EnableDynamicLayout](#enabledynamiclayout)|ユーザーがウィンドウのサイズを変更したときに、子ウィンドウの位置とサイズを動的に調整できるようにします。|  
|[CWnd::EnableD2DSupport](#enabled2dsupport)|ウィンドウの `D2D` のサポートを有効または無効にします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。|  
|[CWnd::EnableScrollBar](#enablescrollbar)|スクロール バーの矢印の一方または両方を有効または無効にします。|  
|[CWnd::EnableScrollBarCtrl](#enablescrollbarctrl)|兄弟スクロール バーのコントロールを有効または無効にします。|  
|[CWnd::EnableToolTips](#enabletooltips)|ツール ヒント コントロールを有効にします。|  
|[CWnd::EnableTrackingToolTips](#enabletrackingtooltips)|トラッキング モードのツール ヒント コントロールを有効にします。|  
|[CWnd::EnableWindow](#enablewindow)|マウス入力およびキーボード入力を有効または無効にします。|  
|[CWnd::EndModalLoop](#endmodalloop)|ウィンドウのモーダル ステータスを終了します。|  
|[CWnd::EndModalState](#endmodalstate)|フレーム ウィンドウをモーダルからモードレスに変更します。|  
|[CWnd::EndPaint](#endpaint)|描画の終了を示します。|  
|[CWnd::ExecuteDlgInit](#executedlginit)|ダイアログ リソースを開始します。|  
|[CWnd::FilterToolTipMessage](#filtertooltipmessage)|ダイアログ ボックス内のコントロールに関連付けられているタイトルまたはテキストを取得します。|  
|[:Findwindow](#findwindow)|ウィンドウのハンドルを返します。ウィンドウのハンドルはそのウィンドウ名とウィンドウ クラスによって識別されます。|  
|[CWnd::FindWindowEx](#findwindowex)|ウィンドウのハンドルを返します。ウィンドウのハンドルはそのウィンドウ名とウィンドウ クラスによって識別されます。|  
|[CWnd::FlashWindow](#flashwindow)|ウィンドウを&1; 回フラッシュします。|  
|[CWnd::FlashWindowEx](#flashwindowex)|ウィンドウをフラッシュし、追加の機能を実行します。|  
|[CWnd::FromHandle](#fromhandle)|ウィンドウのハンドルが指定されている場合、`CWnd` オブジェクトへのポインターを返します。 `CWnd` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CWnd` オブジェクトが生成され、関連付けられます。|  
|[CWnd::FromHandlePermanent](#fromhandlepermanent)|ウィンドウのハンドルが指定されている場合、`CWnd` オブジェクトへのポインターを返します。 `CWnd` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CWnd` オブジェクトが生成され、関連付けられます。|  
|[CWnd::get_accChild](#get_accchild)|指定された子の `IDispatch` インターフェイスのアドレスを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accChildCount](#get_accchildcount)|このオブジェクトに属する子の数を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accDefaultAction](#get_accdefaultaction)|オブジェクトの既定のアクションを記述する文字列を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accDescription](#get_accdescription)|指定されたオブジェクトの外観を記述する文字列を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accFocus](#get_accfocus)|キーボード フォーカスを保持するオブジェクトを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accHelp](#get_acchelp)|オブジェクトのために、フレームワークによって呼び出される**ヘルプ**プロパティの文字列です。|  
|[CWnd::get_accHelpTopic](#get_acchelptopic)|指定されたオブジェクトに関連付けられている `WinHelp` ファイルの完全パスと、そのファイル内の適切なトピックの識別子を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accKeyboardShortcut](#get_acckeyboardshortcut)|指定されたオブジェクトのショートカット キーまたはアクセス キーを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accName](#get_accname)|指定されたオブジェクトの名前を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accParent](#get_accparent)|オブジェクトの親の `IDispatch` インターフェイスを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accRole](#get_accrole)|指定されたオブジェクトの役割を記述する情報を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accSelection](#get_accselection)|このオブジェクトの選択されている子を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accState](#get_accstate)|指定されたオブジェクトの現在の状態を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accValue](#get_accvalue)|指定されたオブジェクトの値を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::GetActiveWindow](#getactivewindow)|アクティブなウィンドウを取得します。|  
|[CWnd::GetAncestor](#getancestor)|指定したウィンドウの祖先ウィンドウ オブジェクトを取得します。|  
|[CWnd::GetCapture](#getcapture)|マウス キャプチャを持つ `CWnd` を取得します。|  
|[CWnd::GetCaretPos](#getcaretpos)|キャレットの現在位置を示すクライアント座標を取得します。|  
|[CWnd::GetCheckedRadioButton](#getcheckedradiobutton)|ボタンのグループ内で現在チェックされているオプション ボタンの ID を返します。|  
|[CWnd::GetClientRect](#getclientrect)|`CWnd` クライアント領域の寸法を取得します。|  
|[CWnd::GetClipboardOwner](#getclipboardowner)|クリップボードの現在のオーナーへのポインターを取得します。|  
|[CWnd::GetClipboardViewer](#getclipboardviewer)|クリップボード ビューアーのチェインの最初のウィンドウへのポインターを取得します。|  
|[CWnd::GetControlUnknown](#getcontrolunknown)|不明な ActiveX コントロールへのポインターを取得します。|  
|[:Getdc](#getdc)|クライアント領域のディスプレイ コンテキストを取得します。|  
|[CWnd::GetDCEx](#getdcex)|クライアント領域のディスプレイ コンテキストを取得し、描画中のクリッピングを有効にします。|  
|[CWnd::GetDCRenderTarget](#getdcrendertarget)|`CWnd` ウィンドウのデバイス コンテキスト (DC) レンダー ターゲットを取得します。|  
|[CWnd::GetDescendantWindow](#getdescendantwindow)|すべての子孫ウィンドウを検索し、指定された ID を持つウィンドウを返します。|  
|[揃える](#getdesktopwindow)|Windows のデスクトップ ウィンドウを取得します。|  
|[CWnd::GetDlgCtrlID](#getdlgctrlid)|`CWnd` が子ウィンドウの場合、この関数を呼び出すと、その ID 値が返されます。|  
|[:Getdlgitem](#getdlgitem)|指定されたダイアログ ボックスから指定された ID を持つコントロールを取得します。|  
|[CWnd::GetDlgItemInt](#getdlgitemint)|指定されたダイアログ ボックスにあるコントロールのテキストを整数値に変換します。|  
|[CWnd::GetDlgItemText](#getdlgitemtext)|コントロールに関連付けられているキャプションまたはテキストを取得します。|  
|[CWnd::GetDSCCursor](#getdsccursor)|データ ソース コントロールの DataSource、UserName、Password、および SQL プロパティで定義されている、基になるカーソルへのポインターを取得します。|  
|[CWnd::GetDynamicLayout](#getdynamiclayout)|動的レイアウト マネージャー オブジェクトへのポインターを取得します。|  
|[CWnd::GetExStyle](#getexstyle)|ウィンドウの拡張スタイルを返します。|  
|[CWnd::GetFocus](#getfocus)|現在入力フォーカスを持っている `CWnd` へのポインターを取得します。|  
|[CWnd::GetFont](#getfont)|現在のフォントを取得します。|  
|[CWnd::GetForegroundWindow](#getforegroundwindow)|手前のウィンドウ (ユーザーが現在作業しているトップレベル ウィンドウ) へのポインターを返します。|  
|[CWnd::GetIcon](#geticon)|アイコンへのハンドルを取得します。|  
|[CWnd::GetLastActivePopup](#getlastactivepopup)|`CWnd` が所有するポップアップ ウィンドウのうち、直前にアクティブだったウィンドウを調べます。|  
|[CWnd::GetLayeredWindowAttributes](#getlayeredwindowattributes)|レイヤード ウィンドウの不透明度および透明度のカラー キーを取得します。|  
|[とき](#getmenu)|指定されたメニューへのポインターを取得します。|  
|[CWnd::GetNextDlgGroupItem](#getnextdlggroupitem)|コントロールのグループ内で、指定されたコントロールの直前または次に位置するコントロールを検索します。|  
|[CWnd::GetNextDlgTabItem](#getnextdlgtabitem)|最初のコントロールを取得、 [WS_TABSTOP](window-styles.md)スタイルを指定したコントロールを依存して (または前)。|  
|[CWnd::GetNextWindow](#getnextwindow)|ウィンドウ マネージャーのリストから次 (または前) のウィンドウを返します。|  
|[CWnd::GetOleControlSite](#getolecontrolsite)|指定された ActiveX コントロールのカスタム サイトを取得します。|  
|[CWnd::GetOpenClipboardWindow](#getopenclipboardwindow)|現在クリップボードが開いているウィンドウへのポインターを取得します。|  
|[CWnd::GetOwner](#getowner)|`CWnd` のオーナーへのポインターを取得します。|  
|[CWnd::GetParent](#getparent)|`CWnd` の親ウィンドウがある場合、そのウィンドウを取得します。|  
|[CWnd::GetParentFrame](#getparentframe)|`CWnd` オブジェクトの親フレーム ウィンドウを取得します。|  
|[CWnd::GetParentOwner](#getparentowner)|子ウィンドウの親ウィンドウへのポインターを返します。|  
|[CWnd::GetProperty](#getproperty)|ActiveX コントロール プロパティを取得します。|  
|[CWnd::GetRenderTarget](#getrendertarget)|このウィンドウに関連付けられているレンダー ターゲットを取得します。|  
|[CWnd::GetSafeHwnd](#getsafehwnd)|`m_hWnd` を返します。`this` ポインターが `NULL` の場合は、`NULL` を返します。|  
|[CWnd::GetSafeOwner](#getsafeowner)|指定されたウィンドウのセーフ オーナーを取得します。|  
|[CWnd::GetScrollBarCtrl](#getscrollbarctrl)|兄弟スクロール バーのコントロールを返します。|  
|[CWnd::GetScrollBarInfo](#getscrollbarinfo)|指定されたスクロール バーの情報を取得します。|  
|[CWnd::GetScrollInfo](#getscrollinfo)|`SCROLLINFO` 構造体がスクロール バーについて保持している情報を取得します。|  
|[CWnd::GetScrollLimit](#getscrolllimit)|スクロール バーの限界値を取得します。|  
|[CWnd::GetScrollPos](#getscrollpos)|スクロール ボックスの現在位置を取得します。|  
|[CWnd::GetScrollRange](#getscrollrange)|指定されたスクロール バーの現在の最小位置と最大位置をコピーします。|  
|[状態](#getstyle)|現在のウィンドウ スタイルを返します。|  
|[CWnd::GetSystemMenu](#getsystemmenu)|アプリケーションがコピーおよび変更のためにコントロール メニューにアクセスできるようにします。|  
|[CWnd::GetTitleBarInfo](#gettitlebarinfo)|指定されたタイトル バーの情報を取得します。|  
|[CWnd::GetTopLevelFrame](#gettoplevelframe)|ウィンドウのトップレベルのフレーム ウィンドウを取得します。|  
|[CWnd::GetTopLevelOwner](#gettoplevelowner)|トップ レベルのウィンドウを取得します。|  
|[CWnd::GetTopLevelParent](#gettoplevelparent)|ウィンドウのトップレベルの親ウィンドウを取得します。|  
|[CWnd::GetTopWindow](#gettopwindow)|`CWnd` に属する第&1; レベルの子ウィンドウを返します。|  
|[CWnd::GetUpdateRect](#getupdaterect)|`CWnd` 更新領域を完全に囲む最小の四角形の座標を取得します。|  
|[CWnd::GetUpdateRgn](#getupdatergn)|`CWnd` 更新領域を取得します。|  
|[CWnd::GetWindow](#getwindow)|対象となるウィンドウとの間に指定された関係が成り立つウィンドウを返します。|  
|[CWnd::GetWindowContextHelpId](#getwindowcontexthelpid)|ヘルプ コンテキスト識別子を取得します。|  
|[CWnd::GetWindowDC](#getwindowdc)|キャプション バー、メニュー、スクロール バーを含むウィンドウ全体のディスプレイ コンテキストを取得します。|  
|[CWnd::GetWindowedChildCount](#getwindowedchildcount)|関連付けられている子ウィンドウの数を返します。|  
|[CWnd::GetWindowInfo](#getwindowinfo)|ウィンドウに関する情報を返します。|  
|[CWnd::GetWindowlessChildCount](#getwindowlesschildcount)|関連付けられているウィンドウなしの子ウィンドウの数を返します。|  
|[CWnd::GetWindowPlacement](#getwindowplacement)|ウィンドウの表示状態、通常の位置 (復元された位置)、最小化された位置、および最大表示された位置を取得します。|  
|[CWnd::GetWindowRect](#getwindowrect)|`CWnd` の画面座標を取得します。|  
|[CWnd::GetWindowRgn](#getwindowrgn)|ウィンドウのウィンドウ領域のコピーを取得します。|  
|[CWnd::GetWindowText](#getwindowtext)|ウィンドウのテキストまたはキャプション タイトル (ある場合) を返します。|  
|[CWnd::GetWindowTextLength](#getwindowtextlength)|ウィンドウのテキストまたはキャプション タイトルの長さを返します。|  
|[CWnd::HideCaret](#hidecaret)|ディスプレイ画面からキャレットを削除して非表示にします。|  
|[CWnd::HiliteMenuItem](#hilitemenuitem)|トップ レベル (メニュー バー) のメニュー項目の強調表示を設定または解除します。|  
|[CWnd::HtmlHelp](#htmlhelp)|HTML ヘルプ アプリケーションを起動するために呼び出されます。|  
|[CWnd::Invalidate](#invalidate)|クライアント領域全体を無効にします。|  
|[エディット](#invalidaterect)|指定された四角形を現在の更新領域に追加して、その四角形内のクライアント領域を無効にします。|  
|[CWnd::InvalidateRgn](#invalidatergn)|指定された領域を現在の更新領域に追加して、その領域内のクライアント領域を無効にします。|  
|[CWnd::InvokeHelper](#invokehelper)|ActiveX コントロール メソッドまたはプロパティを呼び出します。|  
|[CWnd::IsChild](#ischild)|`CWnd` が指定されたウィンドウの子ウィンドウか、または指定されたウィンドウの別の直系の子孫ウィンドウであるかを示します。|  
|[CWnd::IsD2DSupportEnabled](#isd2dsupportenabled)|`D2D` のサポートが有効かどうかを判定します。|  
|[CWnd::IsDialogMessage](#isdialogmessage)|指定されたメッセージがモードレス ダイアログ ボックス用かどうかを判断します。モードレス ダイアログ ボックス用のメッセージである場合は、そのメッセージを処理します。|  
|[CWnd::IsDlgButtonChecked](#isdlgbuttonchecked)|ボタン コントロールがチェックされているかどうかを判断します。|  
|[CWnd::IsDynamicLayoutEnabled](#isdynamiclayoutenabled)|このウィンドウで動的レイアウトが有効かどうかを判断します。 動的レイアウトが有効な場合は、ユーザーが親ウィンドウのサイズを変更したときに、子ウィンドウの位置とサイズを変更できます。|  
|[CWnd::IsIconic](#isiconic)|`CWnd` が最小化 (アイコン化) されているかどうかを判断します。|  
|[CWnd::IsTouchWindow](#istouchwindow)|`CWnd` でタッチ操作がサポートされているかどうかを示します。|  
|[CWnd::IsWindowEnabled](#iswindowenabled)|ウィンドウでマウス入力およびキーボード入力が有効かどうかを判断します。|  
|[CWnd::IsWindowVisible](#iswindowvisible)|ウィンドウが表示可能かどうかを判断します。|  
|[CWnd::IsZoomed](#iszoomed)|`CWnd` が最大表示されているかどうかを判断します。|  
|[メイン フレーム ウィンドウ](#killtimer)|システム タイマーを中止します。|  
|[CWnd::LockWindowUpdate](#lockwindowupdate)|指定されたウィンドウでの描画を無効化、または再有効化します。|  
|[CWnd::MapWindowPoints](#mapwindowpoints)|複数の点を `CWnd` の座標空間から他のウィンドウの座標空間へ変換 (マップ) します。|  
|[CWnd::MessageBox](#messagebox)|アプリケーションで用意されたメッセージとキャプションを含むウィンドウを作成し、表示します。|  
|[CWnd::ModifyStyle](#modifystyle)|現在のウィンドウ スタイルを変更します。|  
|[CWnd::ModifyStyleEx](#modifystyleex)|ウィンドウの拡張スタイルを変更します。|  
|[CWnd::MoveWindow](#movewindow)|`CWnd` の位置と寸法を変更します。|  
|[CWnd::NotifyWinEvent](#notifywinevent)|定義済みイベントが発生したことをシステムに通知します。|  
|[CWnd::OnAmbientProperty](#onambientproperty)|アンビエント プロパティ値を実装します。|  
|[CWnd::OnDrawIconicThumbnailOrLivePreview](#ondrawiconicthumbnailorlivepreview)|Windows 7 のタブのサムネイルに表示する、またはアプリケーションのピーク用にクライアントで表示するビットマップを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CWnd::OnHelp](#onhelp)|アプリケーション内で F1 ヘルプを (現在のコンテキストを使って) 処理します。|  
|[CWnd::OnHelpFinder](#onhelpfinder)|`ID_HELP_FINDER` コマンドおよび `ID_DEFAULT_HELP` コマンドを処理します。|  
|[CWnd::OnHelpIndex](#onhelpindex)|`ID_HELP_INDEX` コマンドを処理し、既定のヘルプ トピックを用意します。|  
|[CWnd::OnHelpUsing](#onhelpusing)|`ID_HELP_USING` コマンドを処理します。|  
|[CWnd::OnToolHitTest](#ontoolhittest)|点が指定されたツールの外接する四角形内にあるかどうかを判断し、そのツールに関する情報を取得します。|  
|[CWnd::OpenClipboard](#openclipboard)|クリップボードを開きます。 その他のアプリケーションでは、Windows までクリップボードを変更できません[CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035)関数が呼び出されます。|  
|[CWnd::PaintWindowlessControls](#paintwindowlesscontrols)|コントロール コンテナーのウィンドウなしのコントロールを描画します。|  
|[CWnd::PostMessage](#postmessage)|メッセージをアプリケーション キューに配置し、ウィンドウがメッセージを処理するのを待たずに制御を返します。|  
|[CWnd::PreCreateWindow](#precreatewindow)|`CWnd` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。|  
|[CWnd::PreSubclassWindow](#presubclasswindow)|により、前に発生するために必要なその他のサブクラス化[SubclassWindow](#subclasswindow)が呼び出されます。|  
|[CWnd::PreTranslateMessage](#pretranslatemessage)|ウィンドウ メッセージが Windows 関数の `TranslateMessage` および `DispatchMessage` にディスパッチされる前に、メッセージにフィルターをかけるために `CWinApp` によって使用されます。|  
|[CWnd::Print](#print)|指定されたデバイス コンテキストで現在のウィンドウを描画します。|  
|[CWnd::PrintClient](#printclient)|指定されたデバイス コンテキスト (通常はプリンター デバイス コンテキスト) で、さまざまなウィンドウを描画します。|  
|[CWnd::PrintWindow](#printwindow)|表示されているウィンドウを指定されたデバイス コンテキスト (通常はプリンター DC) にコピーします。|  
|[CWnd::RedrawWindow](#redrawwindow)|クライアント領域内の指定された四角形または領域を更新します。|  
|[CWnd::RegisterTouchWindow](#registertouchwindow)|Windows タッチのサポートを登録または登録解除します。|  
|[CWnd::ReleaseDC](#releasedc)|他のアプリケーションが使用できるように、クライアント デバイス コンテキストおよびウィンドウ デバイス コンテキストを解放します。|  
|[ため](#repositionbars)|クライアント領域のコントロール バーの位置を変更します。|  
|[CWnd::RunModalLoop](#runmodalloop)|モーダル ステータスであるウィンドウのメッセージを取得、変換、またはディスパッチします。|  
|[CWnd::ScreenToClient](#screentoclient)|ディスプレイ上の指定された点または四角形の画面座標をクライアント座標に変換します。|  
|[CWnd::ScrollWindow](#scrollwindow)|クライアント領域の内容をスクロールします。|  
|[CWnd::ScrollWindowEx](#scrollwindowex)|クライアント領域の内容をスクロールします。 `ScrollWindow` と同様に、追加機能があります。|  
|[CWnd::SendChildNotifyLastMsg](#sendchildnotifylastmsg)|子ウィンドウがタスクを処理できるように、親ウィンドウから子ウィンドウへ通知メッセージを送信します。|  
|[CWnd::SendDlgItemMessage](#senddlgitemmessage)|指定されたコントロールにメッセージを送信します。|  
|[CWnd::SendMessage](#sendmessage)|`CWnd` オブジェクトにメッセージを送信し、メッセージが処理されるまで待機します。|  
|[ハンドラー](#sendmessagetodescendants)|対象となるウィンドウのすべての子孫ウィンドウにメッセージを送信します。|  
|[CWnd::SendNotifyMessage](#sendnotifymessage)|指定されたメッセージをウィンドウに送信し、呼び出し元のスレッドがウィンドウを作成したかどうかに応じて、できるだけ早く制御を返します。|  
|[CWnd::SetActiveWindow](#setactivewindow)|ウィンドウをアクティブにします。|  
|[CWnd::SetCapture](#setcapture)|以降のすべてのマウス入力を `CWnd` に送信します。|  
|[CWnd::SetCaretPos](#setcaretpos)|指定された位置にキャレットを移動します。|  
|[CWnd::SetClipboardViewer](#setclipboardviewer)|クリップボードの内容が変更されるたびに通知を受けるウィンドウのチェインに `CWnd` を追加します。|  
|[CWnd::SetDlgCtrlID](#setdlgctrlid)|ウィンドウのウィンドウ ID またはコントロール ID を設定します (ダイアログ ボックス内のコントロールだけでなく、子ウィンドウの場合もあります)。|  
|[CWnd::SetDlgItemInt](#setdlgitemint)|コントロールのテキストを、整数値を表現する文字列に設定します。|  
|[CWnd::SetDlgItemText](#setdlgitemtext)|指定されたダイアログ ボックスにあるコントロールのキャプションまたはテキストを設定します。|  
|[:Setfocus](#setfocus)|入力フォーカスを要求します。|  
|[Cwnd::setfont](#setfont)|現在のフォントを設定します。|  
|[CWnd::SetForegroundWindow](#setforegroundwindow)|ウィンドウを作成したスレッドをフォアグラウンドに置き、そのウィンドウをアクティブにします。|  
|[CWnd::SetIcon](#seticon)|特定のアイコンへのハンドルを設定します。|  
|[CWnd::SetLayeredWindowAttributes](#setlayeredwindowattributes)|レイヤード ウィンドウの不透明度および透明度のカラー キーを設定します。|  
|[CWnd::SetMenu](#setmenu)|メニューを指定されたメニューに設定します。|  
|[CWnd::SetOwner](#setowner)|`CWnd` のオーナーを変更します。|  
|[CWnd::SetParent](#setparent)|親ウィンドウを変更します。|  
|[CWnd::SetProperty](#setproperty)|ActiveX コントロール プロパティを設定します。|  
|[CWnd::SetRedraw](#setredraw)|`CWnd` の変更内容を再描画したり、または再描画を禁止したりできます。|  
|[CWnd::SetScrollInfo](#setscrollinfo)|スクロール バーの情報を設定します。|  
|[CWnd::SetScrollPos](#setscrollpos)|スクロール ボックスの現在位置を設定します。また、指定されている場合は、新しい位置で表示されるようにスクロール バーを再描画します。|  
|[CWnd::SetScrollRange](#setscrollrange)|指定されたスクロール バーの最小位置と最大位置の値を設定します。|  
|[で](#settimer)|送信システム タイマーをインストール、 [WM_TIMER](#ontimer)がトリガーされたときのメッセージします。|  
|[CWnd::SetWindowContextHelpId](#setwindowcontexthelpid)|ヘルプ コンテキスト識別子を設定します。|  
|[CWnd::SetWindowPlacement](#setwindowplacement)|ウィンドウの表示状態、通常の位置 (復元された位置)、最小化された位置、および最大表示された位置を設定します。|  
|[CWnd::SetWindowPos](#setwindowpos)|子ウィンドウ、ポップアップ ウィンドウ、およびトップレベル ウィンドウのサイズ、位置、および順序付けを変更します。|  
|[は](#setwindowrgn)|ウィンドウ領域を設定します。|  
|[き](#setwindowtext)|ウィンドウ テキストまたはキャプション タイトル (ある場合) を指定されたテキストに設定します。|  
|[CWnd::ShowCaret](#showcaret)|ディスプレイ上のキャレット現在位置にキャレットを表示します。 キャレットは、表示されると自動的に点滅します。|  
|[CWnd::ShowOwnedPopups](#showownedpopups)|ウィンドウが所有するすべてのポップアップ ウィンドウを表示または非表示にします。|  
|[CWnd::ShowScrollBar](#showscrollbar)|スクロール バーを表示または非表示にします。|  
|[また](#showwindow)|ウィンドウを表示または非表示にします。|  
|[CWnd::SubclassDlgItem](#subclassdlgitem)|Windows コントロールを `CWnd` オブジェクトに関連付け、`CWnd` のメッセージ マップを通じてそのオブジェクトにメッセージを送信します。|  
|[CWnd::SubclassWindow](#subclasswindow)|ウィンドウを `CWnd` オブジェクトに関連付け、その `CWnd` のメッセージ マップを通じてメッセージがルーティングされるようにします。|  
|[CWnd::UnlockWindowUpdate](#unlockwindowupdate)|`CWnd::LockWindowUpdate` でロックされていたウィンドウのロックを解除します。|  
|[CWnd::UnsubclassWindow](#unsubclasswindow)|ウィンドウを切り離します、`CWnd`オブジェクト|  
|[:Updatedata](#updatedata)|ダイアログ ボックスのデータを初期化または取得します。|  
|[ダイアログ](#updatedialogcontrols)|ダイアログの各ボタンの状態および他のコントロールの状態を更新します。|  
|[CWnd::UpdateLayeredWindow](#updatelayeredwindow)|レイヤード ウィンドウの位置、サイズ、形状、内容、および透明度を更新します。|  
|[CWnd::UpdateWindow](#updatewindow)|クライアント領域を更新します。|  
|[CWnd::ValidateRect](#validaterect)|指定された四角形を現在の更新領域から削除して、その四角形内のクライアント領域を有効にします。|  
|[CWnd::ValidateRgn](#validatergn)|現在の更新領域から指定された領域を削除して、その領域内のクライアント領域を有効にします。|  
|[CWnd::WindowFromPoint](#windowfrompoint)|指定された点を含むウィンドウを識別します。|  
|[CWnd::WinHelp](#winhelp)|WinHelp アプリケーションを起動します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWnd::Default](#default)|既定のウィンドウ プロシージャを呼び出します。既定のウィンドウ プロシージャは、アプリケーションが処理しないウィンドウ メッセージに対する既定の処理を提供します。|  
|[CWnd::DefWindowProc](#defwindowproc)|既定のウィンドウ プロシージャを呼び出します。既定のウィンドウ プロシージャは、アプリケーションが処理しないウィンドウ メッセージに対する既定の処理を提供します。|  
|[CWnd::DoDataExchange](#dodataexchange)|ダイアログ データ エクスチェンジとダイアログ データ検証用です。 `UpdateData` によって呼び出されます。|  
|[CWnd::GetCurrentMessage](#getcurrentmessage)|ウィンドウが現在処理しているメッセージへのポインターを返します。 のみで呼び出すようにときに、 `On`*メッセージ*メッセージ ハンドラーのメンバー関数。|  
|[CWnd::InitDynamicLayout](#initdynamiclayout)|ウィンドウの動的レイアウトを初期化するために、フレームワークによって呼び出されます。|  
|[CWnd::LoadDynamicLayoutResource](#loaddynamiclayoutresource)|リソース ファイルから動的レイアウト情報を読み込みます。|  
|[CWnd::OnActivate](#onactivate)|`CWnd` がアクティブまたは非アクティブになるときに呼び出されます。|  
|[CWnd::OnActivateApp](#onactivateapp)|アプリケーションがアクティブまたは非アクティブになるときに呼び出されます。|  
|[CWnd::OnAppCommand](#onappcommand)|ユーザーがアプリケーションのコマンド イベントを生成するときに呼び出されます。|  
|[CWnd::OnAskCbFormatName](#onaskcbformatname)|クリップボード オーナーがクリップボードの内容を表示するときに、クリップボード ビューアーによって呼び出されます。|  
|[CWnd::OnCancelMode](#oncancelmode)|`CWnd` でマウスのキャプチャなどの内部モードを取り消すことができるようにするために呼び出されます。|  
|[CWnd::OnCaptureChanged](#oncapturechanged)|マウス キャプチャを失うウィンドウにメッセージを送信します。|  
|[CWnd::OnChangeCbChain](#onchangecbchain)|指定されたウィンドウがチェインから削除されようとしていることを通知します。|  
|[CWnd::OnChangeUIState](#onchangeuistate)|ユーザー インターフェイス (UI) 状態を変更する必要があるときに呼び出されます。|  
|[CWnd::OnChar](#onchar)|キーストロークが非システム文字に変換されるときに呼び出されます。|  
|[CWnd::OnCharToItem](#onchartoitem)|子のリスト ボックスから呼び出す、 [LBS_WANTKEYBOARDINPUT](list-box-styles.md)への応答でスタイル、 [WM_CHAR](#onchar)メッセージです。|  
|[CWnd::OnChildActivate](#onchildactivate)|`CWnd` のサイズや位置が変更されたり、`CWnd` がアクティブになったりした場合に、マルチ ドキュメント インターフェイス (MDI) 子ウィンドウに対して呼び出されます。|  
|[CWnd::OnChildNotify](#onchildnotify)|親ウィンドウによって呼び出されます。親ウィンドウにメッセージを送るコントロールが、コントロール通知に対応できるようにします。|  
|[CWnd::OnClipboardUpdate](#onclipboardupdate)|クリップボードの内容が変更されたときに呼び出されます。|  
|[CWnd::OnClose](#onclose)|`CWnd` を終了するシグナルとして呼び出されます。|  
|[CWnd::OnColorizationColorChanged](#oncolorizationcolorchanged)|非クライアント領域のレンダリングのポリシーが変更されたときに呼び出されます。|  
|[CWnd::OnCommand](#oncommand)|ユーザーがコマンドを選択すると呼び出されます。|  
|[CWnd::OnCompacting](#oncompacting)|Windows がシステム メモリの低下を検出すると呼び出されます。|  
|[CWnd::OnCompareItem](#oncompareitem)|子の並べ替えられたオーナー描画コンボ ボックスやリスト ボックス内の新しい項目の相対位置を判断するために、呼び出されます。|  
|[CWnd::OnCompositionChanged](#oncompositionchanged)|Desktop Window Manager (DWM) コンポジションを有効にするか無効にするときに、すべてのトップ レベル ウィンドウに対して呼び出されます。|  
|[CWnd::OnContextMenu](#oncontextmenu)|ウィンドウ内でマウスの右ボタンをクリックすると呼び出されます。|  
|[CWnd::OnCopyData](#oncopydata)|あるアプリケーションから他のアプリケーションにデータをコピーします。|  
|[CWnd::OnCreate](#oncreate)|ウィンドウの作成の一部として呼び出されます。|  
|[CWnd::OnCtlColor](#onctlcolor)|`CWnd` がコントロールの親である場合、コントロールの描画時に呼び出されます。|  
|[CWnd::OnDeadChar](#ondeadchar)|キーストロークが非システムのデッド文字 (アクセント記号付き文字など) に変換されるときに呼び出されます。|  
|[構造体](#ondeleteitem)|オーナー描画の子リスト ボックスやコンボ ボックスが破棄されるとき、または項目がコントロールから削除されるときに呼び出されます。|  
|[CWnd::OnDestroy](#ondestroy)|`CWnd` が破棄されているときに呼び出されます。|  
|[CWnd::OnDestroyClipboard](#ondestroyclipboard)|Windows を呼び出すことによって、クリップボードを空白にするときに呼び出されます[EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037)関数です。|  
|[CWnd::OnDeviceChange](#ondevicechange)|デバイスやコンピューターのハードウェア構成が変更されたときに、アプリケーションまたはデバイス ドライバーに通知します。|  
|[CWnd::OnDevModeChange](#ondevmodechange)|ユーザーがデバイス モードの設定を変更したときに、すべてのトップ レベルのウィンドウに対して呼び出されます。|  
|[CWnd::OnDrawClipboard](#ondrawclipboard)|クリップボードの内容が変更されるときに呼び出されます。|  
|[体](#ondrawitem)|オーナー描画の子ボタン コントロール、コンボ ボックス コントロール、リスト ボックス コントロール、またはメニューの外観を描画する必要があるときに呼び出されます。|  
|[CWnd::OnDropFiles](#ondropfiles)|ドロップされたファイルを受け取るように登録したウィンドウ上で、ユーザーがマウスの左ボタンを離したときに呼び出されます。|  
|[CWnd::OnEnable](#onenable)|`CWnd` が有効または無効になるときに呼び出されます。|  
|[CWnd::OnEndSession](#onendsession)|セッションが終了するときに呼び出されます。|  
|[CWnd::OnEnterIdle](#onenteridle)|モーダル ダイアログ ボックスまたはメニューがアイドル状態になることをアプリケーションのメイン ウィンドウ プロシージャに通知するために呼び出されます。|  
|[CWnd::OnEnterMenuLoop](#onentermenuloop)|メニュー モーダル ループに入るときに呼び出されます。|  
|[CWnd::OnEnterSizeMove](#onentersizemove)|影響を受けるウィンドウが移動またはサイズ変更のモーダル ループに入った後に呼び出されます。|  
|[CWnd::OnEraseBkgnd](#onerasebkgnd)|ウィンドウの背景を消去する必要があるときに呼び出されます。|  
|[CWnd::OnExitMenuLoop](#onexitmenuloop)|メニュー モーダル ループが終了したときに呼び出されます。|  
|[CWnd::OnExitSizeMove](#onexitsizemove)|影響を受けるウィンドウが移動またはサイズ変更のモーダル ループを終了した後に呼び出されます。|  
|[CWnd::OnFontChange](#onfontchange)|フォント リソースのプールの変更時に呼び出されます。|  
|[CWnd::OnGetDlgCode](#ongetdlgcode)|方向キーおよび Tab キーによる入力そのものをコントロールが処理できるように、そのコントロールに対して呼び出されます。|  
|[CWnd::OnGetMinMaxInfo](#ongetminmaxinfo)|Windows が最大表示されたときの位置や寸法、または最小や最大のトラッキング サイズを知る必要があるときに、必ず呼び出されます。|  
|[CWnd::OnHelpInfo](#onhelpinfo)|ユーザーが F1 キーを押したときに、フレームワークによって呼び出されます。|  
|[CWnd::OnHotKey](#onhotkey)|ユーザーがシステム全体でのショートカット キーを押したときに呼び出されます。|  
|[CWnd::OnHScroll](#onhscroll)|`CWnd` の水平スクロール バーをクリックすると、呼び出されます。|  
|[CWnd::OnHScrollClipboard](#onhscrollclipboard)|クリップボード オーナーがクリップボード内のイメージをスクロールし、適切な部分を無効にし、スクロール バーの値を更新する必要がある場合に呼び出されます。|  
|[CWnd::OnIconEraseBkgnd](#oniconerasebkgnd)|`CWnd` が最小化 (アイコン化) され、アイコンを描画する前にアイコンの背景を設定する必要があるときに呼び出されます。|  
|[CWnd::OnInitMenu](#oninitmenu)|メニューがアクティブになるときに呼び出されます。|  
|[CWnd::OnInitMenuPopup](#oninitmenupopup)|ポップアップ メニューがアクティブになるときに呼び出されます。|  
|[CWnd::OnInputDeviceChange](#oninputdevicechange)|I/O デバイスがシステムで追加または削除されたときに呼び出されます。|  
|[CWnd::OnInputLangChange](#oninputlangchange)|アプリケーションの入力言語が変更されると呼び出されます。|  
|[CWnd::OnInputLangChangeRequest](#oninputlangchangerequest)|ユーザーが新しい入力言語を選択するときに呼び出されます。|  
|[CWnd::OnKeyDown](#onkeydown)|非システム キーが押されると呼び出されます。|  
|[CWnd::OnKeyUp](#onkeyup)|非システム キーが離されると呼び出されます。|  
|[CWnd::OnKillFocus](#onkillfocus)|`CWnd` が入力フォーカスを失う直前に呼び出されます。|  
|[CWnd::OnLButtonDblClk](#onlbuttondblclk)|マウスの左ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnLButtonDown](#onlbuttondown)|マウスの左ボタンを押すと呼び出されます。|  
|[CWnd::OnLButtonUp](#onlbuttonup)|マウスの左ボタンを離すと呼び出されます。|  
|[CWnd::OnMButtonDblClk](#onmbuttondblclk)|マウスの中央ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnMButtonDown](#onmbuttondown)|マウスの中央ボタンを押すと呼び出されます。|  
|[CWnd::OnMButtonUp](#onmbuttonup)|マウスの中央ボタンを離すと呼び出されます。|  
|[CWnd::OnMDIActivate](#onmdiactivate)|MDI 子ウィンドウがアクティブまたは非アクティブになるときに呼び出されます。|  
|[CWnd::OnMeasureItem](#onmeasureitem)|オーナー描画の子コンボ ボックス、リスト ボックス、またはメニュー項目が作成されるときに呼び出されます。 `CWnd` は、コントロールの大きさを Windows に通知します。|  
|[CWnd::OnMenuChar](#onmenuchar)|ユーザーが押したメニューのニーモニック文字が、現在のメニューに組み込まれているニーモニックと一致しないときに呼び出されます。|  
|[CWnd::OnMenuDrag](#onmenudrag)|ユーザーがメニュー項目をドラッグするときに呼び出されます。|  
|[CWnd::OnMenuGetObject](#onmenugetobject)|マウス カーソルがメニュー項目に入るか、項目の中央から項目の上部または下部に移動したときに呼び出されます。|  
|[CWnd::OnMenuRButtonUp](#onmenurbuttonup)|カーソルがメニュー項目にあるときに、マウスの右ボタンを離すと呼び出されます。|  
|[CWnd::OnMenuSelect](#onmenuselect)|ユーザーがメニュー項目を選択するときに呼び出されます。|  
|[CWnd::OnMouseActivate](#onmouseactivate)|カーソルが非アクティブ ウィンドウにあるときに、マウス ボタンを押すと呼び出されます。|  
|[CWnd::OnMouseHover](#onmousehover)|前回の呼び出しで指定された期間のウィンドウのクライアント領域にカーソルを合わせるときに呼び出されます[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)します。|  
|[CWnd::OnMouseHWheel](#onmousehwheel)|現在のウィンドウが Desktop Window Manager (DWM) によって構成され、そのウィンドウが最大化されるときに呼び出されます。|  
|[CWnd::OnMouseLeave](#onmouseleave)|カーソルが前回の呼び出しで指定されたウィンドウのクライアント領域を離れたときに呼び出されます[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)します。|  
|[CWnd::OnMouseMove](#onmousemove)|マウスのカーソルの移動時に呼び出されます。|  
|[CWnd::OnMouseWheel](#onmousewheel)|マウス ホイールの回転時に呼び出されます。 Windows NT 4.0 メッセージ処理を使用します。|  
|[CWnd::OnMove](#onmove)|`CWnd` の位置が変更されると、呼び出されます。|  
|[CWnd::OnMoving](#onmoving)|ユーザーが `CWnd` オブジェクトを移動中であることを示します。|  
|[CWnd::OnNcActivate](#onncactivate)|アクティブまたは非アクティブ状態を示すために、非クライアント領域を変更する必要があるときに呼び出されます。|  
|[CWnd::OnNcCalcSize](#onnccalcsize)|クライアント領域のサイズと位置を計算する必要があるときに呼び出されます。|  
|[CWnd::OnNcCreate](#onnccreate)|前のバージョンと呼ばれる[OnCreate](#oncreate)非クライアント領域が作成されるときです。|  
|[CWnd::OnNcDestroy](#onncdestroy)|非クライアント領域が破棄されるときに呼び出されます。|  
|[CWnd::OnNcHitTest](#onnchittest)|`CWnd` がカーソルを含む場合、または `SetCapture` を使用してマウス入力をキャプチャした場合に、マウスを移動するごとに Windows によって呼び出されます。|  
|[CWnd::OnNcLButtonDblClk](#onnclbuttondblclk)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの左ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnNcLButtonDown](#onnclbuttondown)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの左ボタンを押すと呼び出されます。|  
|[CWnd::OnNcLButtonUp](#onnclbuttonup)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの左ボタンを離すと呼び出されます。|  
|[CWnd::OnNcMButtonDblClk](#onncmbuttondblclk)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの中央ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnNcMButtonDown](#onncmbuttondown)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの中央ボタンを押すと呼び出されます。|  
|[CWnd::OnNcMButtonUp](#onncmbuttonup)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの中央ボタンを離すと呼び出されます。|  
|[CWnd::OnNcMouseHover](#onncmousehover)|前回の呼び出しで指定された期間のウィンドウの非クライアント領域にカーソルを合わせるときに呼び出されます[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)します。|  
|[CWnd::OnNcMouseLeave](#onncmouseleave)|カーソルが前回の呼び出しで指定されたウィンドウの非クライアント領域を離れると、フレームワークが、このメンバー関数を呼び出す[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)します。|  
|[CWnd::OnNcMouseMove](#onncmousemove)|`CWnd` の非クライアント領域内でカーソルが移動するときに呼び出されます。|  
|[CWnd::OnNcPaint](#onncpaint)|非クライアント領域を描画する必要があるときに呼び出されます。|  
|[CWnd::OnNcRButtonDblClk](#onncrbuttondblclk)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの右ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnNcRButtonDown](#onncrbuttondown)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの右ボタンを押すと呼び出されます。|  
|[CWnd::OnNcRButtonUp](#onncrbuttonup)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの右ボタンを離すと呼び出されます。|  
|[CWnd::OnNcRenderingChanged](#onncrenderingchanged)|非クライアント領域のレンダリングのポリシーが変更されたときに呼び出されます。|  
|[CWnd::OnNcXButtonDblClk](#onncxbuttondblclk)|カーソルがウィンドウの非クライアント領域内にある間にユーザーが XBUTTON1 または XBUTTON2 をダブルクリックすると呼び出されます。|  
|[CWnd::OnNcXButtonDown](#onncxbuttondown)|カーソルがウィンドウの非クライアント領域内にある間にユーザーがマウスの XBUTTON1 または XBUTTON2 を押すと呼び出されます。|  
|[CWnd::OnNcXButtonUp](#onncxbuttonup)|カーソルがウィンドウの非クライアント領域内にある間にユーザーがマウスの XBUTTON1 または XBUTTON2 を離すと呼び出されます。|  
|[CWnd::OnNextMenu](#onnextmenu)|右方向キーまたは左方向キーでメニュー バーとシステム メニューを切り替えたときに呼び出されます。|  
|[CWnd::OnNotify](#onnotify)|コントロールでイベントが発生したこと、またはコントロールが情報を必要としていることを親ウィンドウに通知するために、フレームワークによって呼び出されます。|  
|[CWnd::OnNotifyFormat](#onnotifyformat)|現在のウィンドウが WM_NOTIFY 通知メッセージで ANSI 構造体または Unicode 構造体を受け入れるかどうかを判断するために呼び出されます。|  
|[CWnd::OnPaint](#onpaint)|ウィンドウの一部を再描画するために呼び出されます。|  
|[CWnd::OnPaintClipboard](#onpaintclipboard)|クリップボード ビューアーのクライアント領域の再描画が必要なときに呼び出されます。|  
|[CWnd::OnPaletteChanged](#onpalettechanged)|カラー パレットを使用するウィンドウによる論理パレットの実体化とクライアント領域の更新を許可するために呼び出されます。|  
|[CWnd::OnPaletteIsChanging](#onpaletteischanging)|あるアプリケーションで論理パレットが実体化されるときに、他のアプリケーションに通知します。|  
|[CWnd::OnParentNotify](#onparentnotify)|子ウィンドウを作成または破棄するか、カーソルが子ウィンドウの上にあるときにマウス ボタンをクリックすると呼び出されます。|  
|[Cwnd::onpowerbroadcast](#onpowerbroadcast)|電源管理イベントが発生したときに呼び出されます。|  
|[CWnd::OnQueryDragIcon](#onquerydragicon)|最小化 (アイコン化) された `CWnd` をユーザーがドラッグするときに呼び出されます。|  
|[CWnd::OnQueryEndSession](#onqueryendsession)|ユーザーが Windows セッションを終了するときに呼び出されます。|  
|[CWnd::OnQueryNewPalette](#onquerynewpalette)|もうすぐ入力フォーカスを受け取ることを、`CWnd` に通知します。|  
|[CWnd::OnQueryOpen](#onqueryopen)|`CWnd` がアイコンであり、ユーザーがそのアイコンを開こうとしたときに呼び出されます。|  
|[CWnd::OnQueryUIState](#onqueryuistate)|ウィンドウのユーザー インターフェイス (UI) 状態を取得するために呼び出されます。|  
|[CWnd::OnRawInput](#onrawinput)|現在のウィンドウが生の入力を取得するときに呼び出されます。|  
|[CWnd::OnRButtonDblClk](#onrbuttondblclk)|マウスの右ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnRButtonDown](#onrbuttondown)|マウスの右ボタンを押すと呼び出されます。|  
|[CWnd::OnRButtonUp](#onrbuttonup)|マウスの右ボタンを離すと呼び出されます。|  
|[CWnd::OnRenderAllFormats](#onrenderallformats)|オーナー アプリケーションが破棄され、そのフォーマットすべてのレンダリングが必要なときに呼び出されます。|  
|[CWnd::OnRenderFormat](#onrenderformat)|遅延レンダリングされた固有フォーマットのレンダリングが必要なときに、クリップボード オーナーに対して呼び出されます。|  
|[CWnd::OnSessionChange](#onsessionchange)|セッション状態の変更をアプリケーションに通知するために呼び出されます。|  
|[CWnd::OnSetCursor](#onsetcursor)|マウス入力がキャプチャされずに、ウィンドウ内のカーソルが移動された場合に呼び出されます。|  
|[CWnd::OnSetFocus](#onsetfocus)|`CWnd` が入力フォーカスを取得すると呼び出されます。|  
|[CWnd::OnSettingChange](#onsettingchange)|Win32 `SystemParametersInfo` 関数がシステム全体の設定を変更するときに呼び出されます。|  
|[CWnd::OnShowWindow](#onshowwindow)|`CWnd` が非表示になるか表示されるときに呼び出されます。|  
|[ボトムレス](#onsize)|`CWnd` のサイズが変更された後に呼び出されます。|  
|[CWnd::OnSizeClipboard](#onsizeclipboard)|クリップボード ビューアー ウィンドウのクライアント領域のサイズが変更されたときに呼び出されます。|  
|[CWnd::OnSizing](#onsizing)|四角形のサイズを変更中であることを示します。|  
|[CWnd::OnSpoolerStatus](#onspoolerstatus)|プリント マネージャーのキューでジョブが追加または削除されるたびに、プリント マネージャーから呼び出されます。|  
|[CWnd::OnStyleChanged](#onstylechanged)|示します、 [:setwindowlong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows 関数は、1 つ以上のウィンドウのスタイルが変更されます。|  
|[CWnd::OnStyleChanging](#onstylechanging)|示して、 [:setwindowlong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows の機能が&1; つ以上のウィンドウのスタイルを変更しようとしています。|  
|[CWnd::OnSysChar](#onsyschar)|キーストロークがシステム文字に変換されるときに呼び出されます。|  
|[CWnd::OnSysColorChange](#onsyscolorchange)|システム カラーの設定が変更されたときに、すべてのトップ レベル ウィンドウで呼び出されます。|  
|[CWnd::OnSysCommand](#onsyscommand)|ユーザーがコントロール メニューからコマンドを選択するとき、または最大化ボタンまたは最小化ボタンを選択するときに呼び出されます。|  
|[CWnd::OnSysDeadChar](#onsysdeadchar)|キーストロークがシステムのデッド文字 (アクセント記号付き文字など) に変換されるときに呼び出されます。|  
|[CWnd::OnSysKeyDown](#onsyskeydown)|ユーザーが Alt キーを押したまま他のキーを押すときに呼び出されます。|  
|[CWnd::OnSysKeyUp](#onsyskeyup)|Alt キーと一緒に押していたキーを離すときに呼び出されます。|  
|[CWnd::OnTCard](#ontcard)|ユーザーが編集可能なボタンをクリックしたときに呼び出されます。|  
|[CWnd::OnTimeChange](#ontimechange)|システム時間が変更された後、すべてのトップ レベルのウィンドウに対して呼び出されます。|  
|[CWnd::OnTimer](#ontimer)|指定された各間隔後に呼び出される[SetTimer](#settimer)します。|  
|[CWnd::OnTouchInput](#ontouchinput)|Windows タッチからの&1; つの入力を処理します。|  
|[CWnd::OnTouchInputs](#ontouchinputs)|Windows タッチからの複数の入力を処理します。|  
|[CWnd::OnUniChar](#onunichar)|キーが押されるときに呼び出されます。 これは、現在のウィンドウにキーボード フォーカスと[WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280)によってメッセージを変換、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)関数です。|  
|[CWnd::OnUnInitMenuPopup](#onuninitmenupopup)|ドロップダウン メニューやサブメニューが破棄されたときに呼び出されます。|  
|[CWnd::OnUpdateUIState](#onupdateuistate)|指定したウィンドウとすべての子ウィンドウのユーザー インターフェイス (UI) 状態を変更するときに呼び出されます。|  
|[CWnd::OnUserChanged](#onuserchanged)|ユーザーがログオンまたはログオフした後に呼び出されます。|  
|[CWnd::OnVKeyToItem](#onvkeytoitem)|所有するリスト ボックスから呼び出す`CWnd`に応えて、 [WM_KEYDOWN](#onkeydown)メッセージです。|  
|[ために](#onvscroll)|ウィンドウの垂直スクロール バーをクリックすると呼び出されます。|  
|[CWnd::OnVScrollClipboard](#onvscrollclipboard)|オーナーがクリップボード内のイメージをスクロールし、適切な部分を無効にし、さらに、スクロール バーの値を更新する必要がある場合に呼び出されます。|  
|[CWnd::OnWindowPosChanged](#onwindowposchanged)|呼び出しの結果として、サイズ、位置、または Z オーダーが変更されたときと呼ばれる[SetWindowPos](#setwindowpos)または別のウィンドウ管理関数です。|  
|[CWnd::OnWindowPosChanging](#onwindowposchanging)|サイズ、位置、または Z オーダーは呼び出しの結果として変更するときに呼び出されます[SetWindowPos](#setwindowpos)または別のウィンドウ管理関数です。|  
|[CWnd::OnWinIniChange](#onwininichange)|Windows 初期化ファイルの WIN.INI が変更された後、すべてのトップ レベル ウィンドウに対して呼び出されます。|  
|[返送](#onwndmsg)|ウィンドウのメッセージが処理されたかどうかを示します。|  
|[CWnd::OnXButtonDblClk](#onxbuttondblclk)|カーソルがウィンドウのクライアント領域内にある間にユーザーが XBUTTON1 または XBUTTON2 をダブルクリックすると呼び出されます。|  
|[CWnd::OnXButtonDown](#onxbuttondown)|カーソルがウィンドウのクライアント領域内にある間にユーザーが XBUTTON1 または XBUTTON2 を押すと呼び出されます。|  
|[CWnd::OnXButtonUp](#onxbuttonup)|カーソルがウィンドウのクライアント領域内にある間にユーザーが XBUTTON1 または XBUTTON2 を離すと呼び出されます。|  
|[:Postncdestroy](#postncdestroy)|既定では、この仮想関数を呼び出す[OnNcDestroy](#onncdestroy)ウィンドウが破棄された後に機能します。|  
|[CWnd::ReflectChildNotify](#reflectchildnotify)|メッセージをソースに反映するヘルパー関数です。|  
|[CWnd::ReflectLastMsg](#reflectlastmsg)|最後のメッセージを子ウィンドウに反映します。|  
|[CWnd::ResizeDynamicLayout](#resizedynamiclayout)|ウィンドウで動的レイアウトが有効な場合、子ウィンドウのレイアウトを調整するためにウィンドウのサイズが変更されると、フレームワークによって呼び出されます。|  
|[CWnd::WindowProc](#windowproc)|`CWnd` にウィンドウ プロシージャを提供します。 既定では、メッセージ マップを通じてメッセージをディスパッチします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CWnd::operator hwnd の分離](#operator_hwnd)|ウィンドウへのハンドルを取得するために呼び出します。|  
|[CWnd::operator! =](#operator_neq)|かどうかはウィンドウ ハンドルがあるウィンドウと同じ決定[m_hWnd](#m_hwnd)します。|  
|[CWnd::operator = =](#operator_eq_eq)|かどうかをウィンドウ ハンドルがあるウィンドウと同じ[m_hWnd](#m_hwnd)します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWnd::m_hWnd](#m_hwnd)|この `CWnd` に関連付けられている `HWND` を示します。|  
  
## <a name="remarks"></a>コメント  
 `CWnd` オブジェクトは、Windows のウィンドウとは異なりますが、両者は密接にリンクされています。 `CWnd` オブジェクトは、`CWnd` コンストラクターとデストラクターによって作成され、破棄されます。 Windows のウィンドウがによって作成された Windows の内部データ構造を手元には、**作成**メンバー関数によって破棄されると、`CWnd`仮想デストラクターです。 [DestroyWindow](#destroywindow)関数は、オブジェクトを破棄することがなく Windows のウィンドウを破棄します。  
  
 `CWnd`クラスと非表示にするメッセージ マップ機構、 **WndProc**関数です。 Windows の通知メッセージの受信が自動的に適切なメッセージ マップを通じてルーティング**に***メッセージ*`CWnd`メンバー関数。 オーバーライドする、**に***メッセージ*派生クラスでメンバーの特定のメッセージを処理するメンバー関数。  
  
 `CWnd` クラスでは、アプリケーションの Windows 子ウィンドウも作成できます。 アプリケーション固有のデータを格納するには、`CWnd` からクラスを派生させ、その派生クラスにメンバー変数を追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 子ウィンドウは&2; つのステップで作成します。 最初に、コンス トラクターを呼び出す`CWnd`を構築する、`CWnd`オブジェクトを呼び出し、[作成](#create)子ウィンドウを作成し、適用するメンバー関数を`CWnd`オブジェクトです。  
  
 ユーザーが子ウィンドウを終了したら、ウィンドウを削除してそのデータ構造体を破棄するために、`CWnd` オブジェクトを破棄するか、`DestroyWindow` メンバー関数を呼び出します。  
  
 Microsoft Foundation Class ライブラリでは、固有のウィンドウ タイプを提供するために、`CWnd` からさらにクラスが派生されています。 これらのクラスの多くは[CFrameWnd](../../mfc/reference/cframewnd-class.md)、 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)、 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)、 [CView](../../mfc/reference/cview-class.md)と[CDialog](../../mfc/reference/cdialog-class.md)、さらに派生用に設計されています。 コントロール クラスから派生した`CWnd`など[CButton](../../mfc/reference/cbutton-class.md)直接使用できる、またはさらに派生クラスを使用できます。  
  
 使用する方法について`CWnd`を参照してください[フレーム ウィンドウ](../../mfc/frame-windows.md)と[ウィンドウ オブジェクト](../../mfc/window-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWnd`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-nameaccdodefaultactiona--cwndaccdodefaultaction"></a><a name="accdodefaultaction"></a>CWnd::accDoDefaultAction  
 オブジェクトの既定のアクションを実行するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT accDoDefaultAction(VARIANT varChild);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 呼び出される既定のアクションがオブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトの既定のアクションを実行) するか、(オブジェクトの子要素のいずれかの既定のアクションを実行) する子の ID を指定できます。  
  
### <a name="return-value"></a>戻り値  
 成功すると、失敗した場合、COM エラー コードは S_OK を返します。 参照してください**値を返す**で[IAccessible::accDoDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318470)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC のにおいて[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-オブジェクトの既定のアクションを実行するクラスを派生します。 詳細については、次を参照してください。 [IAccessible::accDoDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318470)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameacchittesta--cwndacchittest"></a><a name="acchittest"></a>CWnd::accHitTest  
 画面上の指定された位置にある子要素または子オブジェクトを取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT accHitTest(
    long xLeft,  
    long yTop,  
    VARIANT* pvarChild);
```  
  
### <a name="parameters"></a>パラメーター  
 `xLeft`  
 (画面単位) にヒットする点の X 座標をテストします。  
  
 `yTop`  
 ヒットする点の Y 座標は、(画面単位) でテストします。  
  
 `pvarChild`  
 指定された位置にあるオブジェクトを識別する情報を受け取る`xLeft`と`yTop`です。 参照してください*pvarID*で[IAccessible::accHitTest](http://msdn.microsoft.com/library/windows/desktop/dd318471)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 成功すると、失敗した場合、COM エラー コードは S_OK を返します。 参照してください**値を返す**で**IAccessible::accHitTest**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC のにおいて[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(コントロールのウィンドウ ハンドル、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素がある場合、派生クラスです。  
  
 詳細については、次を参照してください。 [IAccessible::accHitTest](http://msdn.microsoft.com/library/windows/desktop/dd318471)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameacclocationa--cwndacclocation"></a><a name="acclocation"></a>CWnd::accLocation  
 指定されたオブジェクトの現在の画面位置を取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT accLocation(
    long* pxLeft,  
    long* pyTop,  
    long* pcxWidth,  
    long* pcyHeight,  
    VARIANT varChild);
```  
  
### <a name="parameters"></a>パラメーター  
 *pxLeft*  
 (画面単位)、オブジェクトの左上隅の x 座標を受け取ります。  
  
 *pyTop*  
 (画面単位)、オブジェクトの左上隅の y 座標を受け取ります。  
  
 *pcxWidth*  
 画面単位でオブジェクトの幅を受信します。  
  
 *pcyHeight*  
 画面単位でオブジェクトの高さを受信します。  
  
 `varChild`  
 取得する場所が、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトの情報を取得) するか、(オブジェクトの子要素に関する情報を取得) する子の ID を指定できます。  
  
### <a name="return-value"></a>戻り値  
 成功すると、失敗した場合、COM エラー コードは S_OK を返します。 参照してください**値を返す**で**IAccessible::accLocation**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 この関数をオーバーライドして`CWnd`-(コントロールのウィンドウ ハンドル、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素がある場合、派生クラスです。  
  
 詳細については、次を参照してください。 **IAccessible::accLocation**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameaccnavigatea--cwndaccnavigate"></a><a name="accnavigate"></a>CWnd::accNavigate  
 コンテナー内の他のユーザー インターフェイス要素を走査するため、可能な場合はそのオブジェクトを取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT accNavigate(
    long navDir,  
    VARIANT varStart,  
    VARIANT* pvarEndUpAt);
```  
  
### <a name="parameters"></a>パラメーター  
 `navDir`  
 移動する方向を指定します。 参照してください`navDir`で[IAccessible::accNavigate](http://msdn.microsoft.com/library/windows/desktop/dd318473)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `varStart`  
 開始オブジェクトを指定します。 参照してください`varStart`で**IAccessible::accNavigate**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 *pvarEndUpAt*  
 移行先のユーザー インターフェイス オブジェクトに関する情報を受け取ります。 参照してください*pvarEnd*で**IAccessible::accNavigate**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 成功すると、失敗した場合、COM エラー コードは S_OK を返します。 参照してください**値を返す**で**IAccessible::accNavigate**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC のにおいて[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(コントロールのウィンドウ ハンドル、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素がある場合、派生クラスです。  
  
 詳細については、次を参照してください。 [IAccessible::accNavigate](http://msdn.microsoft.com/library/windows/desktop/dd318473)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameaccselecta--cwndaccselect"></a><a name="accselect"></a>CWnd::accSelect  
 選択を変更するため、または指定されたオブジェクトのキーボード フォーカスを移動するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT accSelect(
    long flagsSelect,  
    VARIANT varChild);
```  
  
### <a name="parameters"></a>パラメーター  
 `flagsSelect`  
 現在の選択項目またはフォーカスを変更する方法を指定します。 参照してください`flagsSelect`で[IAccessible::accSelect](http://msdn.microsoft.com/library/windows/desktop/dd318474)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `varChild`  
 選択するオブジェクトを指定します。 このパラメーターには、CHILDID_SELF (オブジェクト自体を選択) するか、(オブジェクトの子のいずれかを選択) する子の ID を指定できます。  
  
### <a name="return-value"></a>戻り値  
 成功すると、失敗した場合、COM エラー コードは S_OK を返します。 参照してください**値を返す**で**IAccessible::accSelect**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC のにおいて[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(コントロールのウィンドウ ハンドル、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素がある場合、派生クラスです。  
  
 詳細については、次を参照してください。 [IAccessible::accSelect](http://msdn.microsoft.com/library/windows/desktop/dd318474)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameanimatewindowa--cwndanimatewindow"></a><a name="animatewindow"></a>CWnd::AnimateWindow  
 表示ウィンドウを非表示にするときに、特殊効果を生成します。  
  
```  
BOOL AnimateWindow(
    DWORD dwTime,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTime*  
 ミリ秒単位でアニメーションの再生にかかる時間を指定します。 アニメーションを再生する 200 ミリ秒がかかります。  
  
 `dwFlags`  
 アニメーションの種類を指定します。 使用可能な値の一覧については、次を参照してください。 [AnimateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632669)します。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[AnimateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632669)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namearrangeiconicwindowsa--cwndarrangeiconicwindows"></a><a name="arrangeiconicwindows"></a>CWnd::ArrangeIconicWindows  
 すべての最小化 (アイコン化) された子ウィンドウを整列します。  
  
```  
UINT ArrangeIconicWindows();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合のアイコンの 1 つの行の高さそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、またデスクトップ ウィンドウで、画面全体のアイコンを整列します。 [GetDesktopWindow](#getdesktopwindow)メンバー関数は、デスクトップ ウィンドウ オブジェクトへのポインターを取得します。  
  
 MDI クライアント ウィンドウで MDI 子ウィンドウを整列する[ある最小化された](../../mfc/reference/cmdiframewnd-class.md#mdiiconarrange)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&66;](../../mfc/reference/codesnippet/cpp/cwnd-class_1.cpp)]  
  
##  <a name="a-nameattacha--cwndattach"></a><a name="attach"></a>CWnd::Attach  
 Windows のウィンドウをアタッチ、`CWnd`オブジェクトです。  
  
```  
BOOL Attach(HWND hWndNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndNew`  
 Windows のウィンドウを識別するハンドルを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 この例では、アタッチとデタッチを使用して、MDI クライアントのウィンドウにマップする方法を示します。  
  
 [!code-cpp[NVC_MFCWindowing #&67;](../../mfc/reference/codesnippet/cpp/cwnd-class_2.h)]  
  
 [!code-cpp[NVC_MFCWindowing #&68;](../../mfc/reference/codesnippet/cpp/cwnd-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing #&69;](../../mfc/reference/codesnippet/cpp/cwnd-class_4.cpp)]  
  
##  <a name="a-namebeginmodalstatea--cwndbeginmodalstate"></a><a name="beginmodalstate"></a>CWnd::BeginModalState  
 フレーム ウィンドウをモーダルにします。  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="a-namebeginpainta--cwndbeginpaint"></a><a name="beginpaint"></a>CWnd::BeginPaint  
 準備`CWnd`の描画および塗りつぶし、`PAINTSTRUCT`ペイントに関する情報をデータ構造体。  
  
```  
CDC* BeginPaint(LPPAINTSTRUCT lpPaint);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPaint`  
 指す、 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)描画の情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 デバイス コンテキストを識別する`CWnd`です。 ポインターが一時的である可能性がありの範囲を超えていない格納されている必要があります[EndPaint](#endpaint)します。  
  
### <a name="remarks"></a>コメント  
 塗りつぶしの構造には、完全に更新領域と、バック グラウンドが消去されているかどうかを指定するフラグを囲む最小の四角形を含む RECT データ構造体が含まれています。  
  
 更新領域では設定されて、 [Invalidate](#invalidate)、 [InvalidateRect](#invalidaterect)、または[戻り](#invalidatergn)メンバー関数およびサイズを変更、移動を作成、スクロール、またはクライアント領域に影響するその他の操作を実行後のシステムです。 更新領域が消去されるのマークされている場合`BeginPaint`送信、 [WM_ONERASEBKGND](#onerasebkgnd)メッセージです。  
  
 呼び出す必要はありません、`BeginPaint`以外のメンバー関数への応答内、 [WM_PAINT](#onpaint)メッセージです。 呼び出すたび、`BeginPaint`メンバー関数への呼び出しが一致する必要があります、 [EndPaint](#endpaint)メンバー関数。 キャレットが描画される領域の場合、`BeginPaint`メンバー関数には、カレットの消去を自動的に非表示になります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&70;](../../mfc/reference/codesnippet/cpp/cwnd-class_5.cpp)]  
  
##  <a name="a-namebinddefaultpropertya--cwndbinddefaultproperty"></a><a name="binddefaultproperty"></a>CWnd::BindDefaultProperty  
 呼び出し元のオブジェクトの既定単純なバインドされたプロパティ (エディット コントロール) など、タイプ ライブラリでマークされたを基になるデータ ソース コントロールのデータ ソース、ユーザー名、パスワード、および SQL のプロパティで定義されているカーソルにバインドします。  
  
```  
void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 データ ソース コントロールに連結するのには、データ バインド コントロールのプロパティのように DISPID を指定します。  
  
 `vtProp`  
 バインドするプロパティの種類を指定します-たとえば、 `VT_BSTR`、 **VT_VARIANT**、という具合です。  
  
 `szFieldName`  
 データ ソース管理のプロパティのバインド先によって提供されたカーソルで、列の名前を指定します。  
  
 `pDSCWnd`  
 プロパティをバインドするデータ ソースのホストを制御するウィンドウを指定します。 呼び出す`GetDlgItem`リソース id をドメイン コント ローラーのホスト ウィンドウのこのポインターを取得します。  
  
### <a name="remarks"></a>コメント  
 `CWnd`この関数を呼び出すオブジェクトは、データ バインド コントロールである必要があります。  
  
### <a name="example"></a>例  
 `BindDefaultProperty`次のコンテキストで使用できます。  
  
 [!code-cpp[NVC_MFC_AxDataBinding&#1;](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding&#2;](../../mfc/reference/codesnippet/cpp/cwnd-class_7.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding&#3;](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="a-namebindpropertya--cwndbindproperty"></a><a name="bindproperty"></a>Cwnd::bindproperty  
 データ ソース コントロールに (グリッド コントロール) などのデータ バインド コントロールで、カーソルにバインドされたプロパティをバインドし、そのリレーションシップを MFC バインディング マネージャーに登録します。  
  
```  
void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispId*  
 データ ソース コントロールに連結するのには、データ バインド コントロールのプロパティのように DISPID を指定します。  
  
 `pWndDSC`  
 プロパティをバインドするデータ ソースのホストを制御するウィンドウを指定します。 呼び出す`GetDlgItem`リソース id をドメイン コント ローラーのホスト ウィンドウのこのポインターを取得します。  
  
### <a name="remarks"></a>コメント  
 `CWnd`この関数を呼び出すオブジェクトは、データ バインド コントロールである必要があります。  
  
### <a name="example"></a>例  
 `BindProperty`次のコンテキストで使用できます。  
  
 [!code-cpp[NVC_MFC_AxDataBinding&#1;](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding&4;](../../mfc/reference/codesnippet/cpp/cwnd-class_9.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding&#3;](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="a-namebringwindowtotopa--cwndbringwindowtotop"></a><a name="bringwindowtotop"></a>CWnd::BringWindowToTop  
 `CWnd` を重なったウィンドウのスタックの最上位に移動します。  
  
```  
void BringWindowToTop();
```  
  
### <a name="remarks"></a>コメント  
 また、`BringWindowToTop` により、ポップアップ ウィンドウ、トップレベル ウィンドウ、および MDI 子ウィンドウがアクティブになります。 `BringWindowToTop` メンバー関数は、重なったウィンドウによって部分的または完全に隠されているウィンドウを表示する場合に使用します。  
  
 この関数は、Win32 を呼び出すだけ[BringWindowToTop](http://msdn.microsoft.com/library/windows/desktop/ms632673\(v=vs.85\).aspx)関数です。 呼び出す、 [SetWindowPos](#setwindowpos) Z オーダーでウィンドウの位置を変更する関数。 `BringWindowToTop` 関数では、ウィンドウ スタイルが変更され、そのウィンドウがトップレベル ウィンドウになることはありません。 詳細については、次を参照してください[HWND_TOP と HWND_TOPMOST の違いとは。](http://blogs.msdn.com/b/oldnewthing/archive/2005/11/21/495246.aspx)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&71;](../../mfc/reference/codesnippet/cpp/cwnd-class_10.cpp)]  
  
##  <a name="a-namecalcwindowrecta--cwndcalcwindowrect"></a><a name="calcwindowrect"></a>CWnd::CalcWindowRect  
 指定したクライアントの四角形を含めることができるウィンドウの四角形を計算します。  
  
```  
virtual void CalcWindowRect(
    LPRECT lpClientRect,  
    UINT nAdjustType = adjustBorder);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `lpClientRect`  
 四角形の構造体へのポインター。 入力には、この構造体には、クライアントの四角形が含まれています。 メソッドが終了した後、この構造体には、指定したクライアントの四角形を含めることができるウィンドウの四角形が含まれています。  
  
 [入力] `nAdjustType`  
 使用して`CWnd::adjustBorder`せずウィンドウ座標を計算する、`WS_EX_CLIENTEDGE`スタイル。 それ以外の場合、を使用して`CWnd::adjustOutside`します。  
  
### <a name="remarks"></a>コメント  
 計算されたウィンドウの四角形のサイズでは、メニュー バーの領域は含まれません。  
  
 使用量制限については、次を参照してください。 [AdjustWindowRectEx](http://msdn.microsoft.com/library/windows/desktop/ms632667)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&72;](../../mfc/reference/codesnippet/cpp/cwnd-class_11.cpp)]  
  
##  <a name="a-namecanceltooltipsa--cwndcanceltooltips"></a><a name="canceltooltips"></a>CWnd::CancelToolTips  
 ツール ヒントが現在表示されている場合に、画面から、ツール ヒントを削除するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL CancelToolTips(BOOL bKeys = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bKeys*  
 **TRUE**キーが押され、ステータス バーのテキストを既定に設定するときに、ツール ヒントをキャンセルするそれ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数を使用しても、コードによって管理されるツール ヒントに影響がありません。 影響を受けるのみによって管理されるツール ヒント コントロール[CWnd::EnableToolTips](#enabletooltips)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&73;](../../mfc/reference/codesnippet/cpp/cwnd-class_12.cpp)]  
  
##  <a name="a-namecenterwindowa--cwndcenterwindow"></a><a name="centerwindow"></a>CWnd::CenterWindow  
 ウィンドウをその親ウィンドウの中央に揃えます。  
  
```  
void CenterWindow(CWnd* pAlternateOwner = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pAlternateOwner`  
 基準となることが別のウィンドウへのポインターには、(親ウィンドウ以外の) が中央に配置します。  
  
### <a name="remarks"></a>コメント  
 通常から呼び出されます[CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)アプリケーションのメイン ウィンドウの相対センター ダイアログ ボックスにします。 既定では、関数の中央を基準にして、親ウィンドウをポップアップ ウィンドウをそのオーナー子ウィンドウ。 ポップアップ ウィンドウが所有していない場合は、画面を基準と中央揃えされます。 所有者または、親ではない特定のウィンドウの相対ウィンドウを中央に配置する、`pAlternateOwner`パラメーターは、有効なウィンドウに設定することがあります。 によって返される値を渡すには、画面の中央[に揃える](#getdesktopwindow)として`pAlternateOwner`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&74;](../../mfc/reference/codesnippet/cpp/cwnd-class_13.cpp)]  
  
##  <a name="a-namechangeclipboardchaina--cwndchangeclipboardchain"></a><a name="changeclipboardchain"></a>CWnd::ChangeClipboardChain  
 削除`CWnd`で指定されたウィンドウのクリップボード ビューアー化され、チェーンから`hWndNext`の子孫、`CWnd`チェーン内の先祖です。  
  
```  
BOOL ChangeClipboardChain(HWND hWndNext);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndNext`  
 次のウィンドウを識別`CWnd`クリップボード ビューアー チェインします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namecheckdlgbuttona--cwndcheckdlgbutton"></a><a name="checkdlgbutton"></a>CWnd::CheckDlgButton  
 (か所、横にチェック マーク) をオンまたはオフ (削除からチェック マーク) にボタンまたはその&3; つの状態のボタンの状態を変更します。  
  
```  
void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDButton`  
 変更するボタンを指定します。  
  
 `nCheck`  
 実行するアクションを指定します。 場合`nCheck`、0 以外の場合、`CheckDlgButton`メンバー関数は、ボタンの横にチェック マークを配置; 0 の場合、チェック マークを削除します。 3 つの状態のボタンの場合は`nCheck`が 2 の場合、ボタンの状態が不定になります。  
  
### <a name="remarks"></a>コメント  
 `CheckDlgButton`送信の機能、 [BM_SETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775989)メッセージは、指定したボタンをクリックします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&75;](../../mfc/reference/codesnippet/cpp/cwnd-class_14.cpp)]  
  
##  <a name="a-namecheckradiobuttona--cwndcheckradiobutton"></a><a name="checkradiobutton"></a>CWnd::CheckRadioButton  
 選択 (チェック マークを追加し)、グループ内の特定のオプション ボタンおよびクリア (チェック マーク) 他のすべてのオプション、グループ内のボタンです。  
  
```  
void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDFirstButton`  
 グループ内の最初のオプション ボタンの整数識別子を指定します。  
  
 `nIDLastButton`  
 グループ内の最後のオプション ボタンの整数識別子を指定します。  
  
 `nIDCheckButton`  
 チェックするオプション ボタンの整数識別子を指定します。  
  
### <a name="remarks"></a>コメント  
 `CheckRadioButton`関数の送信、 [BM_SETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775989)メッセージは、指定されたオプション ボタンをクリックします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&76;](../../mfc/reference/codesnippet/cpp/cwnd-class_15.cpp)]  
  
##  <a name="a-namechildwindowfrompointa--cwndchildwindowfrompoint"></a><a name="childwindowfrompoint"></a>CWnd::ChildWindowFromPoint  
 決定するには、いずれかに属する子ウィンドウの場合`CWnd`指定した点が含まれています。  
  
```  
CWnd* ChildWindowFromPoint(POINT point) const;  
  
CWnd* ChildWindowFromPoint(
    POINT point,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 テスト ポイントのクライアント座標を指定します。  
  
 *nflags*  
 スキップするには、どの子ウィンドウを指定します。 このパラメーターは、次の値の組み合わせを指定できます。  
  
|値|説明|  
|-----------|-------------|  
|**CWP_ALL**|すべての子ウィンドウは省略しないでください。|  
|**CWP_SKIPINVISIBLE**|非表示の子ウィンドウをスキップします|  
|**CWP_SKIPDISABLED**|無効な子ウィンドウをスキップします|  
|**CWP_SKIPTRANSPARENT**|透過的な子ウィンドウをスキップします|  
  
### <a name="return-value"></a>戻り値  
 ポイントを含む子ウィンドウを識別します。 **NULL**指定したポイントがクライアント領域外にある場合。 ポイントがクライアント領域内にも、任意の子ウィンドウに含まれていない場合は`CWnd`が返されます。  
  
 このメンバー関数では、指定したポイントを含む非表示または無効になっている子ウィンドウを返します。  
  
 複数のウィンドウには、指定したポイントを含めることができます。 ただし、この関数だけを返す、 `CWnd`* 最初に発生したポイントを含むウィンドウのです。  
  
 `CWnd`* 返される、一時的なとを後で使用しない格納されている必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&77;](../../mfc/reference/codesnippet/cpp/cwnd-class_16.cpp)]  
  
##  <a name="a-nameclienttoscreena--cwndclienttoscreen"></a><a name="clienttoscreen"></a>CWnd::ClientToScreen  
 ディスプレイ上の指定された点または四角形のクライアント座標を画面座標に変換します。  
  
```  
void ClientToScreen(LPPOINT lpPoint) const;  void ClientToScreen(LPRECT lpRect) const;  ```  
  
### Parameters  
 `lpPoint`  
 Points to a [POINT structure](../../mfc/reference/point-structure1.md) or `CPoint` object that contains the client coordinates to be converted.  
  
 `lpRect`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) or `CRect` object that contains the client coordinates to be converted.  
  
### Remarks  
 The `ClientToScreen` member function uses the client coordinates in the **POINT** or `RECT` structure or the `CPoint` or `CRect` object pointed to by `lpPoint` or `lpRect` to compute new screen coordinates; it then replaces the coordinates in the structure with the new coordinates. The new screen coordinates are relative to the upper-left corner of the system display.  
  
 The `ClientToScreen` member function assumes that the given point or rectangle is in client coordinates.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#78](../../mfc/reference/codesnippet/cpp/cwnd-class_17.cpp)]  
  
##  <a name="closewindow"></a>  CWnd::CloseWindow  
 Minimizes the window.  
  
```  
CloseWindow(); を無効にします。
```  
  
### Remarks  
 This member function emulates the functionality of the function [CloseWindow](http://msdn.microsoft.com/library/windows/desktop/ms632678), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="continuemodal"></a>  CWnd::ContinueModal  
 This member function is called by [RunModalLoop](#runmodalloop) to determine when the modal state should be exited.  
  
```  
仮想 BOOL ContinueModal() です。
```  
  
### Return Value  
 Nonzero if modal loop is to be continued; 0 when [EndModalLoop](#endmodalloop) is called.  
  
### Remarks  
 By default, it returns non-zero until `EndModalLoop` is called.  
  
##  <a name="create"></a>  CWnd::Create  
 Creates the specified child window and attaches it to the [CWnd](../../mfc/reference/cwnd-class.md) object.  
  
```  
仮想 BOOL 作成 (LPCTSTR lpszClassName、  
    LPCTSTR したとき  
    DWORD dwStyle  
    Const RECT >/documents/report1.rdl」の長方形,  
    CWnd* pParentWnd、UINT では、CCreateContext* pContext = NULL);
```  
  
### Parameters  
 [in] `lpszClassName`  
 Pointer to a null-terminated string that contains the name of a registered system window class; or the name of a predefined system window class.  
  
 [in] `lpszWindowName`  
 Pointer to a null-terminated string that contains the window display name; otherwise `NULL` for no window display name.  
  
 [in] `dwStyle`  
 Bitwise combination (OR) of [window styles](../../mfc/reference/window-styles.md). The `WS_POPUP` option is not a valid style.  
  
 [in] `rect`  
 The size and location of the window relative to the top-left corner of the parent window.  
  
 [in] `pParentWnd`  
 Pointer to the parent window.  
  
 [in] `nID`  
 ID of the window.  
  
 [in] `pContext`  
 Pointer to a [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) structure that is used to customize the document-view architecture for the application.  
  
### Return Value  
 `TRUE` if the method was successful; otherwise `FALSE`.  
  
### Remarks  
  
> [!WARNING]
> `CWnd::PreCreateWindow` now assigns the hMenu member of its `CREATESTRUCT` parameter to the `this` pointer if the menu is `NULL` and the style contains `WS_CHILD`. For proper functionality, ensure that your dialog control has an ID that is not `NULL`.  
>   
>  This change fixes a crash in managed/native interop scenarios. A `TRACE` statement in `CWnd::Create` alerts the developer of the problem.  
  
 Use the [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) function to register window classes. User defined window classes are available in the module where they are registered.  
  
 The [CWnd::OnCreate](#oncreate) method is called before the `Create` method returns, and before the window becomes visible.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#79](../../mfc/reference/codesnippet/cpp/cwnd-class_18.cpp)]  
  
##  <a name="createaccessibleproxy"></a>  CWnd::CreateAccessibleProxy  
 Creates an Active Accessibility proxy for the specified object.  
  
```  
仮想 HRESULT CreateAccessibleProxy (WPARAM の wParam は、  
    LPARAM lParam  
    LRESULT* pResult) です。
```  
  
### Parameters  
 `wParam`  
 Identifies the object accessed by the Active Accessibility proxy. Can be one of the following values  
  
|Value|Meaning|  
|-----------|-------------|  
|**OBJID_CLIENT**|Refers to the window's client area.|  
  
 `lParam`  
 Provides additional message-dependent information.  
  
 `pResult`  
 A pointer to an **LRESULT** that stores the result code.  
  
### Remarks  
 Creates an Active Accessibility proxy for the specified object.  
  
##  <a name="createcaret"></a>  CWnd::CreateCaret  
 Creates a new shape for the system caret and claims ownership of the caret.  
  
```  
void CreateCaret (CBitmap * pBitmap) です。
```  
  
### Parameters  
 `pBitmap`  
 Identifies the bitmap that defines the caret shape.  
  
### Remarks  
 The bitmap must have previously been created by the [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap) member function, the [CreateDIBitmap](http://msdn.microsoft.com/library/windows/desktop/dd183491) Windows function, or the [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap) member function.  
  
 `CreateCaret` automatically destroys the previous caret shape, if any, regardless of which window owns the caret. Once created, the caret is initially hidden. To show the caret, the [ShowCaret](#showcaret) member function must be called.  
  
 The system caret is a shared resource. `CWnd` should create a caret only when it has the input focus or is active. It should destroy the caret before it loses the input focus or becomes inactive.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#80](../../mfc/reference/codesnippet/cpp/cwnd-class_19.cpp)]  
  
##  <a name="createcontrol"></a>  CWnd::CreateControl  
 Use this member function to create an ActiveX control that will be represented in the MFC program by a `CWnd` object.  
  
```  
BOOL CreateControl (LPCTSTR pszClass、  
    LPCTSTR pszWindowName  
    DWORD dwStyle  
    const RECT >/documents/report1.rdl」の長方形,  
    CWnd* pParentWnd、UINT では、CFile* pPersist = NULL の場合、  
    BOOL bStorage = FALSE、  
    BSTR bstrLicKey = NULL);

 
BOOL CreateControl (REFCLSID clsid、  
    LPCTSTR pszWindowName  
    DWORD dwStyle  
    const RECT >/documents/report1.rdl」の長方形,  
    CWnd* pParentWnd、UINT では、CFile* pPersist = NULL の場合、  
    BOOL bStorage = FALSE、  
    BSTR bstrLicKey = NULL);

 
BOOL CreateControl (REFCLSID clsid、  
    LPCTSTR pszWindowName  
    DWORD dwStyle  
    const ポイント*ppt、const サイズ*psize、  
    CWnd* pParentWnd、UINT では、CFile* pPersist = NULL の場合、  
    BOOL bStorage = FALSE、  
    BSTR bstrLicKey = NULL);
```  
  
### Parameters  
 *pszClass*  
 This string may contain the OLE "short name" (ProgID) for the class, e.g., "CIRC3.Circ3Ctrl.1". The name needs to match the same name registered by the control. Alternatively, the string may contain the string form of a **CLSID**, contained in braces, e.g., "{9DBAFCCF-592F-101B-85CE-00608CEC297B}". In either case, `CreateControl` converts the string to the corresponding class ID.  
  
 *pszWindowName*  
 A pointer to the text to be displayed in the control. Sets the value of the control's Caption or Text property (if any). If **NULL**, the control's Caption or Text property is not changed.  
  
 `dwStyle`  
 Windows styles. The available styles are listed under Remarks.  
  
 `rect`  
 Specifies the control's size and position. It can be either a [CRect](../../atl-mfc-shared/reference/crect-class.md) object or a [RECT structure](../../mfc/reference/rect-structure1.md).  
  
 `ppt`  
 Points to a [POINT structure](../../mfc/reference/point-structure1.md) or `CPoint` object that contains the upper left corner of the control.  
  
 `pSize`  
 Points to a [SIZE](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure or `CSize` object that contains the control's size  
  
 `pParentWnd`  
 Specifies the control's parent window. It must not be **NULL**.  
  
 `nID`  
 Specifies the control's ID.  
  
 `pPersist`  
 A pointer to a [CFile](../../mfc/reference/cfile-class.md) containing the persistent state for the control. The default value is **NULL**, indicating that the control initializes itself without restoring its state from any persistent storage. If not **NULL**, it should be a pointer to a `CFile`-derived object which contains the control's persistent data, in the form of either a stream or a storage. This data could have been saved in a previous activation of the client. The `CFile` can contain other data, but must have its read-write pointer set to the first byte of persistent data at the time of the call to `CreateControl`.  
  
 `bStorage`  
 Indicates whether the data in `pPersist` should be interpreted as IStorage or IStream data. If the data in `pPersist` is a storage, `bStorage` should be **TRUE**. If the data in `pPersist` is a stream, `bStorage` should be **FALSE**. The default value is **FALSE**.  
  
 *bstrLicKe*y  
 Optional license key data. This data is needed only for creating controls that require a run-time license key. If the control supports licensing, you must provide a license key for the creation of the control to succeed. The default value is **NULL**.  
  
 `clsid`  
 The unique class ID of the control.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 `CreateControl` is a direct analog of the [CWnd::Create](#create) function, which creates the window for a `CWnd`. `CreateControl` creates an ActiveX control instead of an ordinary window.  
  
 Only a subset of the Windows `dwStyle` flags are supported for `CreateControl`:  
  
- **WS_VISIBLE** Creates a window that is initially visible. Required if you want the control to be visible immediately, like ordinary windows.  
  
- **WS_DISABLED** Creates a window that is initially disabled. A disabled window cannot receive input from the user. Can be set if the control has an Enabled property.  
  
- `WS_BORDER` Creates a window with a thin-line border. Can be set if control has a BorderStyle property.  
  
- **WS_GROUP** Specifies the first control of a group of controls. The user can change the keyboard focus from one control in the group to the next by using the direction keys. All controls defined with the **WS_GROUP** style after the first control belong to the same group. The next control with the **WS_GROUP** style ends the group and starts the next group.  
  
- **WS_TABSTOP** Specifies a control that can receive the keyboard focus when the user presses the TAB key. Pressing the TAB key changes the keyboard focus to the next control of the **WS_TABSTOP** style.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#81](../../mfc/reference/codesnippet/cpp/cwnd-class_20.h)]  
  
##  <a name="createex"></a>  CWnd::CreateEx  
 Creates the specified window and attaches it to the `CWnd` object.  
  
```  
仮想 BOOL CreateEx (DWORD dwExStyle、  
    LPCTSTR lpszClassName  
    LPCTSTR したとき  
    DWORD dwStyle  
    int x  
    int y  
    int nWidth  
    int パラメーター nHeight  
    HWND hWndParent  
    HMENU nIDorHMenu  
    LPVOID lpParam = NULL);

 
仮想 BOOL CreateEx (DWORD dwExStyle、  
    LPCTSTR lpszClassName  
    LPCTSTR したとき  
    DWORD dwStyle  
    const RECT >/documents/report1.rdl」の長方形,  
    CWnd * pParentWnd、  
    UINT では、  
    LPVOID lpParam = NULL);
```  
  
### Parameters  
 `dwExStyle`  
 Bitwise combination (OR) of [extended window styles](../../mfc/reference/extended-window-styles.md); otherwise `NULL` for the default extended window style.  
  
 `lpszClassName`  
 Pointer to a null-terminated string that contains the name of a registered system window class; or the name of a predefined system window class.  
  
 `lpszWindowName`  
 Pointer to a null-terminated string that contains the window display name; otherwise `NULL` for no window display name.  
  
 `dwStyle`  
 Bitwise combination (OR) of [window styles](../../mfc/reference/window-styles.md); otherwise `NULL` for the default window style.  
  
 `x`  
 The initial horizontal distance of the window from the left side of the screen or the parent window.  
  
 `y`  
 The initial vertical distance of the window from the top of the screen or the parent window.  
  
 `nWidth`  
 The width, in pixels, of the window.  
  
 `nHeight`  
 The height, in pixels, of the window.  
  
 `hwndParent`  
 For a child window, the handle to the parent window; otherwise, the handle of the owner window if the window has an owner.  
  
 `nIDorHMenu`  
 For a child window, the window ID; otherwise, the ID of a menu for the window.  
  
 `lpParam`  
 Pointer to user data that is passed to the [CWnd::OnCreate](#oncreate) method in the `lpCreateParams` field.  
  
 `rect`  
 The size and location of the window relative to the screen or the parent window.  
  
 `pParentWnd`  
 For a child window, pointer to the parent window; otherwise, pointer to the owner window if the window has an owner.  
  
 `nID`  
 For a child window, the window ID; otherwise, the ID of a menu for the window.  
  
### Return Value  
 `TRUE` if the method was successful; otherwise `FALSE`.  
  
### Remarks  
  
> [!WARNING]
> `CWnd::PreCreateWindow` now assigns the hMenu member of its `CREATESTRUCT` parameter to the `this` pointer if the menu is `NULL` and the style contains `WS_CHILD`. For proper functionality, ensure that your dialog control has an ID that is not `NULL`.  
>   
>  This change fixes a crash in managed/native interop scenarios. A `TRACE` statement in `CWnd::Create` alerts the developer of the problem.  
  
 The default extended window style is `WS_EX_LEFT`. The default window style is `WS_OVERLAPPED`.  
  
 Use the [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) function to register window classes. User defined window classes are available in the module where they are registered.  
  
 Dimensions for child windows are relative to the top-left corner of the client area of the parent window. Dimensions for top-level windows are relative to the top-left corner of the screen.  
  
 The [CWnd::OnCreate](#oncreate) method is called before the `CreateEx` method returns, and before the window becomes visible.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#82](../../mfc/reference/codesnippet/cpp/cwnd-class_21.cpp)]  
  
##  <a name="creategraycaret"></a>  CWnd::CreateGrayCaret  
 Creates a gray rectangle for the system caret and claims ownership of the caret.  
  
```  
void CreateGrayCaret (int nWidth、  
    int パラメーター nHeight) です。
```  
  
### Parameters  
 `nWidth`  
 Specifies the width of the caret (in logical units). If this parameter is 0, the width is set to the system-defined window-border width.  
  
 `nHeight`  
 Specifies the height of the caret (in logical units). If this parameter is 0, the height is set to the system-defined window-border height.  
  
### Remarks  
 The caret shape can be a line or a block.  
  
 The parameters `nWidth` and `nHeight` specify the caret's width and height (in logical units); the exact width and height (in pixels) depend on the mapping mode.  
  
 The system's window-border width or height can be retrieved by the [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) Windows function with the **SM_CXBORDER** and **SM_CYBORDER** indexes. Using the window-border width or height ensures that the caret will be visible on a high-resolution display.  
  
 The `CreateGrayCaret` member function automatically destroys the previous caret shape, if any, regardless of which window owns the caret. Once created, the caret is initially hidden. To show the caret, the [ShowCaret](#showcaret) member function must be called.  
  
 The system caret is a shared resource. `CWnd` should create a caret only when it has the input focus or is active. It should destroy the caret before it loses the input focus or becomes inactive.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#83](../../mfc/reference/codesnippet/cpp/cwnd-class_22.cpp)]  
  
##  <a name="createsolidcaret"></a>  CWnd::CreateSolidCaret  
 Creates a solid rectangle for the system caret and claims ownership of the caret.  
  
```  
void CreateSolidCaret (int nWidth、  
    int パラメーター nHeight) です。
```  
  
### Parameters  
 `nWidth`  
 Specifies the width of the caret (in logical units). If this parameter is 0, the width is set to the system-defined window-border width.  
  
 `nHeight`  
 Specifies the height of the caret (in logical units). If this parameter is 0, the height is set to the system-defined window-border height.  
  
### Remarks  
 The caret shape can be a line or block.  
  
 The parameters `nWidth` and `nHeight` specify the caret's width and height (in logical units); the exact width and height (in pixels) depend on the mapping mode.  
  
 The system's window-border width or height can be retrieved by the [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) Windows function with the **SM_CXBORDER** and **SM_CYBORDER** indexes. Using the window-border width or height ensures that the caret will be visible on a high-resolution display.  
  
 The `CreateSolidCaret` member function automatically destroys the previous caret shape, if any, regardless of which window owns the caret. Once created, the caret is initially hidden. To show the caret, the [ShowCaret](#showcaret) member function must be called.  
  
 The system caret is a shared resource. `CWnd` should create a caret only when it has the input focus or is active. It should destroy the caret before it loses the input focus or becomes inactive.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#84](../../mfc/reference/codesnippet/cpp/cwnd-class_23.cpp)]  
  
##  <a name="cwnd"></a>  CWnd::CWnd  
 Constructs a `CWnd` object.  
  
```  
CWnd() です。
```  
  
### Remarks  
 The Windows window is not created and attached until the [CreateEx](#createex) or [Create](#create) member function is called.  
  
##  <a name="default"></a>  CWnd::Default  
 Calls the default window procedure.  
  
```  
LRESULT は Default()。
```  
  
### Return Value  
 Depends on the message sent.  
  
### Remarks  
 The default window procedure provides default processing for any window message that an application does not process. This member function ensures that every message is processed.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#85](../../mfc/reference/codesnippet/cpp/cwnd-class_24.cpp)]  
  
##  <a name="defwindowproc"></a>  CWnd::DefWindowProc  
 Calls the default window procedure, which provides default processing for any window message that an application does not process.  
  
```  
仮想 LRESULT DefWindowProc (UINT メッセージ、  
    WPARAM wParam  
    LPARAM lParam) です。
```  
  
### Parameters  
 `message`  
 Specifies the Windows message to be processed.  
  
 `wParam`  
 Specifies additional message-dependent information.  
  
 `lParam`  
 Specifies additional message-dependent information.  
  
### Return Value  
 Depends on the message sent.  
  
### Remarks  
 This member function ensures that every message is processed. It should be called with the same parameters as those received by the window procedure.  
  
##  <a name="deletetempmap"></a>  CWnd::DeleteTempMap  
 Called automatically by the idle time handler of the `CWinApp` object.  
  
```  
static void PASCAL DeleteTempMap() です。
```  
  
### Remarks  
 Deletes any temporary `CWnd` objects created by the `FromHandle` member function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#86](../../mfc/reference/codesnippet/cpp/cwnd-class_25.cpp)]  
  
##  <a name="destroywindow"></a>  CWnd::DestroyWindow  
 Destroys the Windows window attached to the `CWnd` object.  
  
```  
仮想 BOOL DestroyWindow() です。
```  
  
### Return Value  
 Nonzero if the window is destroyed; otherwise 0.  
  
### Remarks  
 The `DestroyWindow` member function sends appropriate messages to the window to deactivate it and remove the input focus. It also destroys the window's menu, flushes the application queue, destroys outstanding timers, removes Clipboard ownership, and breaks the Clipboard-viewer chain if `CWnd` is at the top of the viewer chain. It sends [WM_DESTROY](#ondestroy) and [WM_NCDESTROY](#onncdestroy) messages to the window. It does not destroy the `CWnd` object.  
  
 `DestroyWindow` is a place holder for performing cleanup. Because `DestroyWindow` is a virtual function, it is shown in any `CWnd`-derived class in Class View. But even if you override this function in your `CWnd`-derived class, `DestroyWindow` is not necessarily called. If `DestroyWindow` is not called in the MFC code, then you have to explicitly call it in your own code if you want it to be called.  
  
 Assume, for example, you have overridden `DestroyWindow` in a `CView`-derived class. Since MFC source code does not call `DestroyWindow` in any of its `CFrameWnd`-derived classes, your overridden `DestroyWindow` will not be called unless you call it explicitly.  
  
 If the window is the parent of any windows, these child windows are automatically destroyed when the parent window is destroyed. The `DestroyWindow` member function destroys child windows first and then the window itself.  
  
 The `DestroyWindow` member function also destroys modeless dialog boxes created by [CDialog::Create](../../mfc/reference/cdialog-class.md#create).  
  
 If the `CWnd` being destroyed is a child window and does not have the [WS_EX_NOPARENTNOTIFY](../../mfc/reference/extended-window-styles.md) style set, then the [WM_PARENTNOTIFY ](https://msdn.microsoft.com/library/ms632638.aspx)       message is sent to the parent.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#87](../../mfc/reference/codesnippet/cpp/cwnd-class_26.cpp)]  
  
##  <a name="detach"></a>  CWnd::Detach  
 Detaches a Windows handle from a `CWnd` object and returns the handle.  
  
```  
HWND Detach() です。
```  
  
### Return Value  
 A `HWND` to the Windows object.  
  
### Example  
  See the example for [CWnd::Attach](#attach).  
  
##  <a name="dlgdirlist"></a>  CWnd::DlgDirList  
 Fills a list box with a file or directory listing.  
  
```  
int DlgDirList (LPTSTR lpPathSpec、  
    int nIDListBox  
    int nIDStaticPath  
    UINT nFileType) です。
```  
  
### Parameters  
 `lpPathSpec`  
 Points to a null-terminated string that contains the path or filename. `DlgDirList` modifies this string, which should be long enough to contain the modifications. For more information, see the following "Remarks" section.  
  
 `nIDListBox`  
 Specifies the identifier of a list box. If `nIDListBox` is 0, `DlgDirList` assumes that no list box exists and does not attempt to fill one.  
  
 `nIDStaticPath`  
 Specifies the identifier of the static-text control used to display the current drive and directory. If `nIDStaticPath` is 0, `DlgDirList` assumes that no such text control is present.  
  
 `nFileType`  
 Specifies the attributes of the files to be displayed. It can be any combination of the following values:  
  
- **DDL_READWRITE** Read-write data files with no additional attributes.  
  
- **DDL_READONLY** Read-only files.  
  
- **DDL_HIDDEN** Hidden files.  
  
- **DDL_SYSTEM** System files.  
  
- **DDL_DIRECTORY** Directories.  
  
- **DDL_ARCHIVE** Archives.  
  
- **DDL_POSTMSGS LB_DIR** flag. If the **LB_DIR** flag is set, Windows places the messages generated by `DlgDirList` in the application's queue; otherwise, they are sent directly to the dialog-box procedure.  
  
- **DDL_DRIVES** Drives. If the **DDL_DRIVES** flag is set, the **DDL_EXCLUSIVE** flag is set automatically. Therefore, to create a directory listing that includes drives and files, you must call `DlgDirList` twice: once with the **DDL_DRIVES** flag set and once with the flags for the rest of the list.  
  
- **DDL_EXCLUSIVE** Exclusive bit. If the exclusive bit is set, only files of the specified type are listed; otherwise normal files and files of the specified type are listed.  
  
### Return Value  
 Nonzero if the function is successful; otherwise 0.  
  
### Remarks  
 `DlgDirList` sends [LB_RESETCONTENT](http://msdn.microsoft.com/library/windows/desktop/bb761325) and [LB_DIR](http://msdn.microsoft.com/library/windows/desktop/bb775185) messages to the list box. It fills the list box specified by `nIDListBox` with the names of all files that match the path given by `lpPathSpec`.  
  
 The `lpPathSpec` parameter has the following form:  
  
 `[drive:] [ [\u]directory[\idirectory]...\u] [filename]`  
  
 In this example, `drive` is a drive letter, `directory` is a valid directory name, and *filename* is a valid filename that must contain at least one wildcard. The wildcards are a question mark ( ****), which means match any character, and an asterisk ( **\***), meaning match any number of characters.  
  
 If you specify a 0-length string for `lpPathSpec`, or if you specify only a directory name but do not include any file specification, the string will be changed to "*.\*".  
  
 If `lpPathSpec` includes a drive and/or directory name, the current drive and directory are changed to the designated drive and directory before the list box is filled. The text control identified by `nIDStaticPath` is also updated with the new drive and/or directory name.  
  
 After the list box is filled, `lpPathSpec` is updated by removing the drive and/or directory portion of the path.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#88](../../mfc/reference/codesnippet/cpp/cwnd-class_27.cpp)]  
  
##  <a name="dlgdirlistcombobox"></a>  CWnd::DlgDirListComboBox  
 Fills the list box of a combo box with a file or directory listing.  
  
```  
int DlgDirListComboBox (LPTSTR lpPathSpec、  
    int nIDComboBox  
    int nIDStaticPath  
    UINT nFileType) です。
```  
  
### Parameters  
 `lpPathSpec`  
 Points to a null-terminated string that contains the path or filename. `DlgDirListComboBox` modifies this string, so this data should not be in the form of a string literal. See the following "Remarks" section.  
  
 `nIDComboBox`  
 Specifies the identifier of a combo box in a dialog box. If `nIDComboBox` is 0, `DlgDirListComboBox` assumes that no combo box exists and does not attempt to fill one.  
  
 `nIDStaticPath`  
 Specifies the identifier of the static-text control used to display the current drive and directory. If `nIDStaticPath` is 0, `DlgDirListComboBox` assumes that no such text control is present.  
  
 `nFileType`  
 Specifies DOS file attributes of the files to be displayed. It can be any combination of the following values:  
  
- **DDL_READWRITE** Read-write data files with no additional attributes.  
  
- **DDL_READONLY** Read-only files.  
  
- **DDL_HIDDEN** Hidden files.  
  
- **DDL_SYSTEM** System files.  
  
- **DDL_DIRECTORY** Directories.  
  
- **DDL_ARCHIVE** Archives.  
  
- **DDL_POSTMSGS CB_DIR** flag. If the **CB_DIR** flag is set, Windows places the messages generated by `DlgDirListComboBox` in the application's queue; otherwise, they are sent directly to the dialog-box procedure.  
  
- **DDL_DRIVES** Drives. If the **DDL_DRIVES** flag is set, the **DDL_EXCLUSIVE** flag is set automatically. Therefore, to create a directory listing that includes drives and files, you must call `DlgDirListComboBox` twice: once with the **DDL_DRIVES** flag set and once with the flags for the rest of the list.  
  
- **DDL_EXCLUSIVE** Exclusive bit. If the exclusive bit is set, only files of the specified type are listed; otherwise normal files and files of the specified type are listed.  
  
### Return Value  
 Specifies the outcome of the function. It is nonzero if a listing was made, even an empty listing. A 0 return value implies that the input string did not contain a valid search path.  
  
### Remarks  
 `DlgDirListComboBox` sends [CB_RESETCONTENT](http://msdn.microsoft.com/library/windows/desktop/bb775878) and [CB_DIR](http://msdn.microsoft.com/library/windows/desktop/bb775832) messages to the combo box. It fills the list box of the combo box specified by `nIDComboBox` with the names of all files that match the path given by `lpPathSpec`.  
  
 The `lpPathSpec` parameter has the following form:  
  
 `[drive:] [ [\u]directory[\idirectory]...\u] [filename]`  
  
 In this example, `drive` is a drive letter, `directory` is a valid directory name, and *filename* is a valid filename that must contain at least one wildcard. The wildcards are a question mark ( ****), which means match any character, and an asterisk ( **\***), which means match any number of characters.  
  
 If you specify a zero-length string for `lpPathSpec`, the current directory will be used and `lpPathSpec` will not be modified. If you specify only a directory name but do not include any file specification, the string will be changed to "*".  
  
 If `lpPathSpec` includes a drive and/or directory name, the current drive and directory are changed to the designated drive and directory before the list box is filled. The text control identified by `nIDStaticPath` is also updated with the new drive and/or directory name.  
  
 After the combo-box list box is filled, `lpPathSpec` is updated by removing the drive and/or directory portion of the path.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#89](../../mfc/reference/codesnippet/cpp/cwnd-class_28.cpp)]  
  
##  <a name="dlgdirselect"></a>  CWnd::DlgDirSelect  
 Retrieves the current selection from a list box.  
  
```  
BOOL DlgDirSelect (LPTSTR されているもの、  
    int nIDListBox) です。
```  
  
### Parameters  
 `lpString`  
 Points to a buffer that is to receive the current selection in the list box.  
  
 `nIDListBox`  
 Specifies the integer ID of a list box in the dialog box.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 It assumes that the list box has been filled by the [DlgDirList](#dlgdirlist) member function and that the selection is a drive letter, a file, or a directory name.  
  
 The `DlgDirSelect` member function copies the selection to the buffer given by `lpString`. If there is no selection, `lpString` does not change.  
  
 `DlgDirSelect` sends [LB_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb775197) and [LB_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761313) messages to the list box.  
  
 It does not allow more than one filename to be returned from a list box. The list box must not be a multiple-selection list box.  
  
##  <a name="dlgdirselectcombobox"></a>  CWnd::DlgDirSelectComboBox  
 Retrieves the current selection from the list box of a combo box.  
  
```  
BOOL DlgDirSelectComboBox (LPTSTR されているもの、  
    int nIDComboBox) です。
```  
  
### Parameters  
 `lpString`  
 Points to a buffer that is to receive the selected path.  
  
 `nIDComboBox`  
 Specifies the integer ID of the combo box in the dialog box.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 It assumes that the list box has been filled by the [DlgDirListComboBox](#dlgdirlistcombobox) member function and that the selection is a drive letter, a file, or a directory name.  
  
 The `DlgDirSelectComboBox` member function copies the selection to the specified buffer. If there is no selection, the contents of the buffer are not changed.  
  
 `DlgDirSelectComboBox` sends [CB_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb775845) and [CB_GETLBTEXT](http://msdn.microsoft.com/library/windows/desktop/bb775862) messages to the combo box.  
  
 It does not allow more than one filename to be returned from a combo box.  
  
##  <a name="dodataexchange"></a>  CWnd::DoDataExchange  
 Called by the framework to exchange and validate dialog data.  
  
```  
仮想 void DoDataExchange (CDataExchange * pDX) です。
```  
  
### Parameters  
 `pDX`  
 A pointer to a `CDataExchange` object.  
  
### Remarks  
 Never call this function directly. It is called by the [UpdateData](#updatedata) member function. Call `UpdateData` to initialize a dialog box's controls or retrieve data from a dialog box.  
  
 When you derive an application-specific dialog class from [CDialog](../../mfc/reference/cdialog-class.md), you need to override this member function if you wish to utilize the framework's automatic data exchange and validation. The Add Variable wizard will write an overridden version of this member function for you containing the desired "data map" of dialog data exchange (DDX) and validation (DDV) global function calls.  
  
 To automatically generate an overridden version of this member function, first create a dialog resource with the dialog editor, then derive an application-specific dialog class. Then use the Add Variable wizard to associate variables, data, and validation ranges with various controls in the new dialog box. The wizard then writes the overridden `DoDataExchange`, which contains a data map. The following is an example DDX/DDV code block generated by the Add Variable wizard:  
  
 [!code-cpp[NVC_MFCWindowing#90](../../mfc/reference/codesnippet/cpp/cwnd-class_29.cpp)]  
  
 The `DoDataExchange` overridden member function must precede the macro statements in your source file.  
  
 For more information on dialog data exchange and validation, see [Displaying and Manipulating Data in a Form](../../data/odbc/displaying-and-manipulating-data-in-a-form.md) and [Dialog Data Exchange and Validation](../../mfc/dialog-data-exchange-and-validation.md). For a description of the DDX_ and DDV_ macros generated by the Add Variable wizard, see [Technical Note 26](../../mfc/tn026-ddx-and-ddv-routines.md).  
  
##  <a name="dragacceptfiles"></a>  CWnd::DragAcceptFiles  
 Call this member function from within a window, using a `CWnd` pointer, in your application's [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) function to indicate that the window accepts dropped files from the Windows File Manager or File Explorer.  
  
```  
DragAcceptFiles を無効にする (BOOL bAccept = TRUE)。
```  
  
### Parameters  
 *BAccept*  
 Flag that indicates whether dragged files are accepted.  
  
### Remarks  
 Only the window that calls `DragAcceptFiles` with the `bAccept` parameter set to **TRUE** has identified itself as able to process the Windows message `WM_DROPFILES`. For example, in an MDI application, if the `CMDIFrameWnd` window pointer is used in the `DragAcceptFiles` function call, only the `CMDIFrameWnd` window gets the `WM_DROPFILES` message. This message is not sent to all open `CMDIChildWnd` windows. For a `CMDIChildWnd` window to receive this message, you must call `DragAcceptFiles` with the `CMDIChildWnd` window pointer.  
  
 To discontinue receiving dragged files, call the member function with `bAccept` set to **FALSE**.  
  
##  <a name="dragdetect"></a>  CWnd::DragDetect  
 Captures the mouse and tracks its movement until the user releases the left button, presses the ESC key, or moves the mouse outside the drag rectangle around the specified point.  
  
```  
BOOL DragDetect(POINT pt) const です。  
```  
  
### Parameters  
 `pt`  
 Initial position of the mouse, in screen coordinates. The function determines the coordinates of the drag rectangle by using this point.  
  
### Return Value  
 If the user moved the mouse outside of the drag rectangle while holding down the left button , the return value is nonzero.  
  
 If the user did not move the mouse outside of the drag rectangle while holding down the left button , the return value is zero.  
  
### Remarks  
 This member function emulates the functionality of the function [DragDetect](http://msdn.microsoft.com/library/windows/desktop/ms646256), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="drawanimatedrects"></a>  CWnd::DrawAnimatedRects  
 Draws a wire-frame rectangle and animates it to indicate the opening of an icon or the minimizing or maximizing of a window.  
  
```  
BOOL DrawAnimatedRects (int idAni、  
    CONST RECT* lprcFrom、CONST RECT* lprcTo) です。
```  
  
### Parameters  
 *idAni*  
 Specifies the type of animation. If you specify **IDANI_CAPTION**, the window caption will animate from the position specified by `lprcFrom` to the position specified by `lprcTo`. The effect is similar to minimizing or maximizing a window.  
  
 `lprcFrom`  
 Pointer to a [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure specifying the location and size of the icon or minimized window.  
  
 `lprcTo`  
 Pointer to a [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure specifying the location and size of the restored window  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [DrawAnimatedRects](http://msdn.microsoft.com/library/windows/desktop/dd162475), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="drawcaption"></a>  CWnd::DrawCaption  
 Draws a window caption.  
  
```  
BOOL DrawCaption (CDC * pDC、  
    LPCRECT lprc  
    UINT uFlags) です。
```  
  
### Parameters  
 `pDC`  
 A pointer to a device context. The function draws the window caption into this device context.  
  
 `lprc`  
 A pointer to a RECT structure that specifies the bounding rectangle for the window caption.  
  
 `uFlags`  
 Specifies drawing options. For a complete list of values, see [DrawCaption](http://msdn.microsoft.com/library/windows/desktop/dd162476).  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [DrawCaption](http://msdn.microsoft.com/library/windows/desktop/dd162476), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="drawmenubar"></a>  CWnd::DrawMenuBar  
 Redraws the menu bar.  
  
```  
DrawMenuBar(); を無効にします。
```  
  
### Remarks  
 If a menu bar is changed after Windows has created the window, call this function to draw the changed menu bar.  
  
### Example  
  See the example for [CWnd::GetMenu](#getmenu).  
  
##  <a name="enableactiveaccessibility"></a>  CWnd::EnableActiveAccessibility  
 Enables user-defined Active Accessibility functions.  
  
```  
EnableActiveAccessibility(); を無効にします。
```  
  
### Remarks  
 MFC's default Active Accessibility support is sufficient for standard windows and controls, including ActiveX controls; however, if your `CWnd`-derived class contains nonwindowed user interface elements, MFC has no way of knowing about them. In that case, you must override the appropriate [Active Accessibility member functions](http://msdn.microsoft.com/en-us/68af04ac-4eb9-4b7d-b33f-c45512097a74) in your class, and you must call **EnableActiveAccessibility** in the class's constructor.  
  
##  <a name="enabledynamiclayout"></a>  CWnd::EnableDynamicLayout  
 Enables or disables the dynamic layout manager. When dynamic layout is enabled, the position and size of child windows can adjust dynamically when the user resizes the window.  
  
```  
EnableDynamicLayout を無効にする (BOOL bEnable = TRUE)。
```  
  
### Parameters  
 `bEnable`  
 TRUE to enable dynamic layout; FALSE to disable dynamic layout.  
  
### Remarks  
 If you want to enable dynamic layout, you have to do more than just call this method. You also have to provide dynamic layout information which species how the controls in the window respond to size changes. You can specify this information in the resource editor, or programmatically, for each control. See [Dynamic Layout](../../mfc/dynamic-layout.md).  
  
##  <a name="enabled2dsupport"></a>  CWnd::EnableD2DSupport  
 Enables or disables window D2D support. Call this method before the main window is initialized.  
  
```  
EnableD2DSupport を無効にする (BOOL bEnable = true の場合、  
    BOOL bUseDCRenderTarget = FALSE);
```  
  
### Parameters  
 `bEnable`  
 Specifies whether to turn on, or off D2D support.  
  
 `bUseDCRenderTarget`  
 Species whether to use the Device Context (DC) render target, CDCRenderTarget. If FALSE, CHwndRenderTarget is used.  
  
##  <a name="enablescrollbar"></a>  CWnd::EnableScrollBar  
 Enables or disables one or both arrows of a scroll bar.  
  
```  
BOOL EnableScrollBar (int nSBFlags、  
    UINT nArrowFlags = ESB_ENABLE_BOTH) です。
```  
  
### Parameters  
 *nSBFlags*  
 Specifies the scroll-bar type. Can have one of the following values:  
  
- **SB_BOTH** Enables or disables the arrows of the horizontal and vertical scroll bars associated with the window.  
  
- **SB_HORZ** Enables or disables the arrows of the horizontal scroll bar associated with the window.  
  
- **SB_VERT** Enables or disables the arrows of the vertical scroll bar associated with the window.  
  
 `nArrowFlags`  
 Specifies whether the scroll-bar arrows are enabled or disabled and which arrows are enabled or disabled. Can have one of the following values:  
  
- **ESB_ENABLE_BOTH** Enables both arrows of a scroll bar (default).  
  
- **ESB_DISABLE_LTUP** Disables the left arrow of a horizontal scroll bar or the up arrow of a vertical scroll bar.  
  
- **ESB_DISABLE_RTDN** Disables the right arrow of a horizontal scroll bar or the down arrow of a vertical scroll bar.  
  
- **ESB_DISABLE_BOTH** Disables both arrows of a scroll bar.  
  
### Return Value  
 Nonzero if the arrows are enabled or disabled as specified. Otherwise it is 0, which indicates that the arrows are already in the requested state or that an error occurred.  
  
##  <a name="enablescrollbarctrl"></a>  CWnd::EnableScrollBarCtrl  
 Enables or disables the scroll bar for this window.  
  
```  
void EnableScrollBarCtrl (int れる、  
    BOOL bEnable = TRUE)。
```  
  
### Parameters  
 `nBar`  
 The scroll-bar identifier.  
  
 `bEnable`  
 Specifies whether the scroll bar is to be enabled or disabled.  
  
### Remarks  
 If the window has a sibling scroll-bar control, that scroll bar is used; otherwise the window's own scroll bar is used.  
  
##  <a name="enabletooltips"></a>  CWnd::EnableToolTips  
 Enables tool tips for the given window.  
  
```  
BOOL EnableToolTips(BOOL bEnable = TRUE) です。
```  
  
### Parameters  
 `bEnable`  
 Specifies whether the tool tip control is enabled or disabled. **TRUE** enables the control; **FALSE** disables the control.  
  
### Return Value  
 **TRUE** if tool tips are enabled; otherwise **FALSE**.  
  
### Remarks  
 Override [OnToolHitTest](#ontoolhittest) to provide the [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) struct or structs for the window.  
  
> [!NOTE]
>  Some windows, such as [CToolBar](../../mfc/reference/ctoolbar-class.md), provide a built-in implementation of [OnToolHitTest](#ontoolhittest).  
  
 See [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for more information on this structure.  
  
 Simply calling `EnableToolTips` is not enough to display tool tips for your child controls unless the parent window is derived from `CFrameWnd`. This is because `CFrameWnd` provides a default handler for the **TTN_NEEDTEXT** notification. If your parent window is not derived from `CFrameWnd`, that is, if it is a dialog box or a form view, tool tips for your child controls will not display correctly unless you provide a handler for the **TTN_NEEDTEXT** tool tip notification. See [Tool Tips](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 The default tool tips provided for your windows by `EnableToolTips` do not have text associated with them. To retrieve text for the tool tip to display, the **TTN_NEEDTEXT** notification is sent to the tool tip control's parent window just before the tool tip window is displayed. If there is no handler for this message to assign some value to the `pszText` member of the **TOOLTIPTEXT** structure, there will be no text displayed for the tool tip.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#91](../../mfc/reference/codesnippet/cpp/cwnd-class_30.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#92](../../mfc/reference/codesnippet/cpp/cwnd-class_31.cpp)]  
  
##  <a name="enabletrackingtooltips"></a>  CWnd::EnableTrackingToolTips  
 Enables or disables tracking tooltips.  
  
```  
BOOL EnableTrackingToolTips(BOOL bEnable = TRUE) です。
```  
  
### Parameters  
 `bEnable`  
 Specifies whether tracking tool tips are enabled or disabled. If this parameter is **TRUE**, the tracking tool tips will be enabled. If this parameter is **FALSE**, the tracking tool tips will be disabled.  
  
### Return Value  
 Indicates the state before the `EnableWindow` member function was called. The return value is nonzero if the window was previously disabled. The return value is 0 if the window was previously enabled or an error occurred.  
  
### Remarks  
 Tracking tool tips are tool tip windows that you can dynamically position on the screen. By rapidly updating the position, the tool tip window appears to move smoothly, or "track." This functionality can be useful if you need tool tip text to follow the position of the pointer as it moves.  
  
##  <a name="enablewindow"></a>  CWnd::EnableWindow  
 Enables or disables mouse and keyboard input.  
  
```  
BOOL EnableWindow(BOOL bEnable = TRUE) です。
```  
  
### Parameters  
 `bEnable`  
 Specifies whether the given window is to be enabled or disabled. If this parameter is **TRUE**, the window will be enabled. If this parameter is **FALSE**, the window will be disabled.  
  
### Return Value  
 Indicates the state before the `EnableWindow` member function was called. The return value is nonzero if the window was previously disabled. The return value is 0 if the window was previously enabled or an error occurred.  
  
### Remarks  
 When input is disabled, input such as mouse clicks and keystrokes is ignored. When input is enabled, the window processes all input.  
  
 If the enabled state is changing, the [WM_ENABLE](#onenable) message is sent before this function returns.  
  
 If disabled, all child windows are implicitly disabled, although they are not sent `WM_ENABLE` messages.  
  
 A window must be enabled before it can be activated. For example, if an application is displaying a modeless dialog box and has disabled its main window, the main window must be enabled before the dialog box is destroyed. Otherwise, another window will get the input focus and be activated. If a child window is disabled, it is ignored when Windows tries to determine which window should get mouse messages.  
  
 By default, a window is enabled when it is created. An application can specify the **WS_DISABLED** style in the [Create](#create) or [CreateEx](#createex) member function to create a window that is initially disabled. After a window has been created, an application can also use the `EnableWindow` member function to enable or disable the window.  
  
 An application can use this function to enable or disable a control in a dialog box. A disabled control cannot receive the input focus, nor can a user access it.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#93](../../mfc/reference/codesnippet/cpp/cwnd-class_32.cpp)]  
  
##  <a name="endmodalloop"></a>  CWnd::EndModalLoop  
 Terminates a call to `RunModalLoop`.  
  
```  
仮想 void は (int れた)。
```  
  
### Parameters  
 `nResult`  
 Contains the value to be returned to the caller of [RunModalLoop](#runmodalloop).  
  
### Remarks  
 The `nResult` parameter is propagated to the return value from `RunModalLoop`.  
  
##  <a name="endmodalstate"></a>  CWnd::EndModalState  
 Call this member function to change a frame window from modal to modeless.  
  
```  
仮想 void EndModalState() です。
```  
  
##  <a name="endpaint"></a>  CWnd::EndPaint  
 Marks the end of painting in the given window.  
  
```  
void EndPaint (LPPAINTSTRUCT lpPaint) です。
```  
  
### Parameters  
 `lpPaint`  
 Points to a [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) structure that contains the painting information retrieved by the [BeginPaint](#beginpaint) member function.  
  
### Remarks  
 The `EndPaint` member function is required for each call to the `BeginPaint` member function, but only after painting is complete.  
  
 If the caret was hidden by the `BeginPaint` member function, `EndPaint` restores the caret to the screen.  
  
### Example  
  See the example for [CWnd::BeginPaint](#beginpaint).  
  
##  <a name="executedlginit"></a>  CWnd::ExecuteDlgInit  
 Initiates a dialog resource.  
  
```  
BOOL ExecuteDlgInit(LPCTSTR lpszResourceName) です。  
BOOL ExecuteDlgInit(LPVOID lpResource) です。
```  
  
### Parameters  
 `lpszResourceName`  
 A pointer to a null-terminated string specifying the name of the resource.  
  
 `lpResource`  
 A pointer to a resource.  
  
### Return Value  
 **TRUE** if a dialog resource is executed; otherwise **FALSE**.  
  
### Remarks  
 `ExecuteDlgInit` will use resources bound to the executing module, or resources from other sources. To accomplish this, `ExecuteDlgInit` finds a resource handle by calling `AfxFindResourceHandle`. If your MFC application does not use the shared DLL (MFCx0[U][D].DLL), **AfxFindResourceHandle** calls [AfxGetResourceHandle](http://msdn.microsoft.com/library/d0eff6c4-f566-471a-96b7-a5a70a751a92), which returns the current resource handle for the executable. If your MFC application that uses MFCx0[U][D].DLL, `AfxFindResourceHandle` traverses the **CDynLinkLibrary** object list of shared and extension DLLs looking for the correct resource handle.  
  
##  <a name="filtertooltipmessage"></a>  CWnd::FilterToolTipMessage  
 Called by the framework to display tool tip messages.  
  
```  
void FilterToolTipMessage (MSG * pMsg) です。
```  
  
### Parameters  
 `pMsg`  
 A pointer to the tool tip message.  
  
### Remarks  
 In most MFC applications this method is called by the framework from [PreTranslateMessage](#pretranslatemessage) and [EnableToolTips](#enabletooltips), and you do not need to call it yourself.  
  
 However, in certain applications, for example some ActiveX controls, these methods might not be invoked by the framework, and you will need to call FilterToolTipMessage yourself. For more information, see [Methods of Creating Tool Tips](../../mfc/methods-of-creating-tool-tips.md).  
  
##  <a name="findwindow"></a>  CWnd::FindWindow  
 Returns the top-level `CWnd` whose window class is given by `lpszClassName` and whose window name, or title, is given by `lpszWindowName`.  
  
```  
静的 CWnd * PASCAL FindWindow (LPCTSTR lpszClassName、  
    LPCTSTR したとき)。
```  
  
### Parameters  
 `lpszClassName`  
 Points to a null-terminated string that specifies the window's class name (a **WNDCLASS** structure). If `lpClassName` is **NULL**, all class names match.  
  
 `lpszWindowName`  
 Points to a null-terminated string that specifies the window name (the window's title). If `lpWindowName` is **NULL**, all window names match.  
  
### Return Value  
 Identifies the window that has the specified class name and window name. It is **NULL** if no such window is found.  
  
 The `CWnd`* may be temporary and should not be stored for later use.  
  
### Remarks  
 This function does not search child windows.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#94](../../mfc/reference/codesnippet/cpp/cwnd-class_33.cpp)]  
  
##  <a name="findwindowex"></a>  CWnd::FindWindowEx  
 Retrieves the window object whose class name and window name match the specified strings.  
  
```  
静的 CWnd * FindWindowEx (HWND hwndParent、  
    HWND hwndChildAfter  
    LPCTSTR lpszClass  
    LPCTSTR lpszWindow) です。
```  
  
### Parameters  
 *hwndParent*  
 Handle to the parent window whose child windows are to be searched.  
  
 *hwndChildAfter*  
 Handle to a child window. The search begins with the next child window in the Z order. The child window must be a direct child window of *hwndParent*, not just a descendant window.  
  
 `lpszClass`  
 Pointer to a null-terminated string that specifies the class name or a class atom created by a previous call to the [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586) or [RegisterClassEx](http://msdn.microsoft.com/library/windows/desktop/ms633587).  
  
 *lpszWindow*  
 Pointer to a null-terminated string that specifies the window name (the window's title). If this parameter is **NULL**, all window names match.  
  
### Return Value  
 If the function succeeds, the return value is a pointer to the window object having the specified class and window names. If the function fails, the return value is **NULL**.  
  
### Remarks  
 This member function emulates the functionality of the function [FindWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms633500), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="flashwindow"></a>  CWnd::FlashWindow  
 Flashes the given window once.  
  
```  
BOOL FlashWindow(BOOL bInvert) です。
```  
  
### Parameters  
 `bInvert`  
 Specifies whether the `CWnd` is to be flashed or returned to its original state. The `CWnd` is flashed from one state to the other if `bInvert` is **TRUE**. If `bInvert` is **FALSE**, the window is returned to its original state (either active or inactive).  
  
### Return Value  
 Nonzero if the window was active before the call to the `FlashWindow` member function; otherwise 0.  
  
### Remarks  
 For successive flashing, create a system timer and repeatedly call `FlashWindow`. Flashing the `CWnd` means changing the appearance of its title bar as if the `CWnd` were changing from inactive to active status, or vice versa. (An inactive title bar changes to an active title bar; an active title bar changes to an inactive title bar.)  
  
 Typically, a window is flashed to inform the user that it requires attention but that it does not currently have the input focus.  
  
 The `bInvert` parameter should be **FALSE** only when the window is getting the input focus and will no longer be flashing; it should be **TRUE** on successive calls while waiting to get the input focus.  
  
 This function always returns nonzero for minimized windows. If the window is minimized, `FlashWindow` will simply flash the window's icon; `bInvert` is ignored for minimized windows.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#95](../../mfc/reference/codesnippet/cpp/cwnd-class_34.cpp)]  
  
##  <a name="flashwindowex"></a>  CWnd::FlashWindowEx  
 Flashes the given window.  
  
```  
BOOL FlashWindowEx (DWORD dwFlags、  
    UINT uCount  
    DWORD dwTimeout) です。
```  
  
### Parameters  
 `dwFlags`  
 Specifies the flash status. For a complete list of values, see the [FLASHWINFO](http://msdn.microsoft.com/library/windows/desktop/ms679348) structure.  
  
 `uCount`  
 Specifies the number of times to flash the window.  
  
 `dwTimeout`  
 Specifies the rate, in milliseconds, at which the window will be flashed. If `dwTimeout` is zero, the function uses the default cursor blink rate.  
  
### Return Value  
 The return value specifies the window's state before the call to the `FlashWindowEx` function. If the window caption was drawn as active before the call, the return value is nonzero. Otherwise, the return value is zero.  
  
### Remarks  
 This method emulates the functionality of the function [FlashWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms679347), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="fromhandle"></a>  CWnd::FromHandle  
 Returns a pointer to a `CWnd` object when given a handle to a window. If a `CWnd` object is not attached to the handle, a temporary `CWnd` object is created and attached.  
  
```  
静的 CWnd * PASCAL FromHandle(HWND hWnd) です。
```  
  
### Parameters  
 `hWnd`  
 An `HWND` of a Windows window.  
  
### Return Value  
 Returns a pointer to a `CWnd` object when given a handle to a window. If a `CWnd` object is not attached to the handle, a temporary `CWnd` object is created and attached.  
  
 The pointer may be temporary and should not be stored for later use.  
  
##  <a name="fromhandlepermanent"></a>  CWnd::FromHandlePermanent  
 Returns a pointer to a `CWnd` object when given a handle to a window.  
  
```  
静的 CWnd * PASCAL FromHandlePermanent(HWND hWnd) です。
```  
  
### Parameters  
 `hWnd`  
 An `HWND` of a Windows window.  
  
### Return Value  
 A pointer to a `CWnd` object.  
  
### Remarks  
 If a `CWnd` object is not attached to the handle, **NULL** is returned.  
  
 This function, unlike [FromHandle](#fromhandle), does not create temporary objects.  
  
##  <a name="get_accchild"></a>  CWnd::get_accChild  
 Called by the framework to retrieve the address of an `IDispatch` interface for the specified child.  
  
```  
仮想 HRESULT get_accChild (バリアント varChild、  
    IDispatch** ppdispChild) です。
```  
  
### Parameters  
 `varChild`  
 Identifies the child whose `IDispatch` interface is to be retrieved.  
  
 *ppdispChild*  
 Receives the address of the child object's `IDispatch` interface.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accChild](http://msdn.microsoft.com/library/windows/desktop/dd318475) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accChild](http://msdn.microsoft.com/library/windows/desktop/dd318475) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accchildcount"></a>  CWnd::get_accChildCount  
 Called by the framework to retrieve the number of children belonging to this object.  
  
```  
仮想 HRESULT get_accChildCount (時間の長い * pcountChildren) です。
```  
  
### Parameters  
 *pcountChildren*  
 Receives the number of children.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accChildCount](http://msdn.microsoft.com/library/windows/desktop/dd318476) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles). Call the base class version and then add the nonwindowed child elements.  
  
 For more information, see [IAccessible::get_accChildCount](http://msdn.microsoft.com/library/windows/desktop/dd318476) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accdefaultaction"></a>  CWnd::get_accDefaultAction  
 Called by the framework to retrieve a string that describes the object's default action.  
  
```  
仮想 HRESULT get_accDefaultAction (バリアント varChild、  
    BSTR* pszDefaultAction) です。
```  
  
### Parameters  
 `varChild`  
 Specifies whether the default action to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 *pszDefaultAction*  
 Address of a `BSTR` that receives a localized string describing the default action for the specified object, or NULL if this object has no default action.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318477) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to describe your object's default action.  
  
 For more information, see [IAccessible::get_accDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318477) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accdescription"></a>  CWnd::get_accDescription  
 Called by framework to retrieve a string that describes the visual appearance of the specified object.  
  
```  
仮想 HRESULT get_accDescription (バリアント varChild、  
    BSTR* pszDescription) です。
```  
  
### Parameters  
 `varChild`  
 Specifies whether the description to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pszDescription`  
 Address of a `BSTR` that receives a localized string describing the specified object, or NULL if no description is available for this object.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accDescription](http://msdn.microsoft.com/library/windows/desktop/dd318478) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to describe your object. Call the base class version and add your description.  
  
 For more information, see [IAccessible::get_accDescription](http://msdn.microsoft.com/library/windows/desktop/dd318478) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accfocus"></a>  CWnd::get_accFocus  
 Called by the framework to retrieve the object that has the keyboard focus.  
  
```  
仮想 HRESULT get_accFocus (VARIANT * pvarChild) です。
```  
  
### Parameters  
 `pvarChild`  
 Receives information about the object that has the focus. See *pvarID* in [IAccessible::get_accFocus](http://msdn.microsoft.com/library/windows/desktop/dd318479) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accFocus** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accFocus](http://msdn.microsoft.com/library/windows/desktop/dd318479) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_acchelp"></a>  CWnd::get_accHelp  
 Called by the framework to retrieve an object's **Help** property string.  
  
```  
仮想 HRESULT get_accHelp (バリアント varChild、  
    BSTR* pszHelp) です。
```  
  
### Parameters  
 `varChild`  
 Specifies whether the help information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 *pszHelp*  
 Address of a `BSTR` that receives the localized string containing the help information for the specified object, or NULL if no help information is available.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accHelp](http://msdn.microsoft.com/library/windows/desktop/dd318480) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to provide help text for your object.  
  
 For more information, see [IAccessible::get_accHelp](http://msdn.microsoft.com/library/windows/desktop/dd318480) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_acchelptopic"></a>  CWnd::get_accHelpTopic  
 Called by the framework to retrieve the full path of the **WinHelp** file associated with the specified object and the identifier of the appropriate topic within that file.  
  
```  
仮想 HRESULT get_accHelpTopic (BSTR* pszHelpFile バリアント varChild 長い*pidTopic) です。
```  
  
### Parameters  
 `pszHelpFile`  
 Address of a `BSTR` that receives the full path of the `WinHelp` file associated with the specified object, if any.  
  
 `varChild`  
 Specifies whether the Help topic to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain a Help topic for the object) or a child ID (to obtain a Help topic for one of the object's child elements).  
  
 `pidTopic`  
 Identifies the Help file topic associated with the specified object. See `pidTopic` in [IAccessible::get_accHelpTopic](http://msdn.microsoft.com/library/windows/desktop/dd318481) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accHelpTopic** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to provide help information about your object.  
  
 For more information, see [IAccessible::get_accHelpTopic](http://msdn.microsoft.com/library/windows/desktop/dd318481) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_acckeyboardshortcut"></a>  CWnd::get_accKeyboardShortcut  
 Called by the framework to retrieve the specified object's shortcut key or access key.  
  
```  
仮想 HRESULT get_accKeyboardShortcut (バリアント varChild、  
    BSTR* pszKeyboardShortcut) です。
```  
  
### Parameters  
 `varChild`  
 Specifies whether the keyboard shortcut to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 *pszKeyboardShortcut*  
 Address of a `BSTR` that receives a localized string identifying the keyboard shortcut, or NULL if no keyboard shortcut is associated with the specified object.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accKeyboardShortcut](http://msdn.microsoft.com/library/windows/desktop/dd318482) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to identify the keyboard shortcut for your object.  
  
 For more information, see [IAccessible::get_accKeyboardShortcut](http://msdn.microsoft.com/library/windows/desktop/dd318482) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accname"></a>  CWnd::get_accName  
 Called by the framework to retrieve the name of the specified object.  
  
```  
仮想 HRESULT get_accName (バリアント varChild、  
    BSTR* pszName) です。
```  
  
### Parameters  
 `varChild`  
 Specifies whether the name to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pszName`  
 Address of a `BSTR` that receives a string containing the specified object's name.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accName](http://msdn.microsoft.com/library/windows/desktop/dd318483) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to return the name of your object.  
  
 For more information, see [IAccessible::get_accName](http://msdn.microsoft.com/library/windows/desktop/dd318483) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accparent"></a>  CWnd::get_accParent  
 Called by the framework to retrieve the `IDispatch` interface of the object's parent.  
  
```  
仮想 HRESULT get_accParent (IDispatch * * ppdispParent) です。
```  
  
### Parameters  
 *ppdispParent*  
 Receives the address of the parent object's `IDispatch` interface. The variable is set to NULL if no parent exists, or if the child cannot access its parent.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accParent](http://msdn.microsoft.com/library/windows/desktop/dd318484) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 In most cases you don't have to override this function.  
  
 For more information, see [IAccessible::get_accParent](http://msdn.microsoft.com/library/windows/desktop/dd318484) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accrole"></a>  CWnd::get_accRole  
 Called by the framework to retrieve information that describes the role of the specified object.  
  
```  
仮想 HRESULT get_accRole (バリアント varChild、  
    VARIANT* pvarRole) です。
```  
  
### Parameters  
 `varChild`  
 Specifies whether the role information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pvarRole`  
 Receives the role information. See `pvarRole` in [IAccessible::get_accRole](http://msdn.microsoft.com/library/windows/desktop/dd318485) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accRole** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accRole](http://msdn.microsoft.com/library/windows/desktop/dd318485) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accselection"></a>  CWnd::get_accSelection  
 Called by the framework to retrieve the selected children of this object.  
  
```  
仮想 HRESULT get_accSelection (VARIANT * pvarChildren) です。
```  
  
### Parameters  
 `pvarChildren`  
 Receives information about which children are selected. See `pvarChildren` in [IAccessible::get_accSelection](http://msdn.microsoft.com/library/windows/desktop/dd318486) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accSelection** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accSelection](http://msdn.microsoft.com/library/windows/desktop/dd318486) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accstate"></a>  CWnd::get_accState  
 Called by the framework to retrieve the current state of the specified object.  
  
```  
仮想 HRESULT get_accState (バリアント varChild、  
    VARIANT* pvarState) です。
```  
  
### Parameters  
 `varChild`  
 Specifies whether the state information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pvarState`  
 Receives information about the object's state. See `pvarState` in [IAccessible::get_accState](http://msdn.microsoft.com/library/windows/desktop/dd318487) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accState** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accState](http://msdn.microsoft.com/library/windows/desktop/dd318487) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accvalue"></a>  CWnd::get_accValue  
 Called by the framework to retrieve the value of the specified object.  
  
```  
仮想 HRESULT get_accValue (バリアント varChild、  
    BSTR* 終端) です。
```  
  
### Parameters  
 `varChild`  
 Specifies whether the value information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pszValue`  
 Address of the `BSTR` that receives a localized string containing the object's current value.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accValue](http://msdn.microsoft.com/library/windows/desktop/dd318488) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accValue](http://msdn.microsoft.com/library/windows/desktop/dd318488) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getactivewindow"></a>  CWnd::GetActiveWindow  
 Retrieves a pointer to the active window.  
  
```  
静的 CWnd * PASCAL 場合に、Getactivewindow です。
```  
  
### Return Value  
 The active window or **NULL** if no window was active at the time of the call. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The active window is either the window that has the current input focus or the window explicitly made active by the [SetActiveWindow](#setactivewindow) member function.  
  
##  <a name="getancestor"></a>  CWnd::GetAncestor  
 Retrieves the ancestor window object of the specified window.  
  
```  
CWnd * GetAncestor(UINT gaFlags) const です。  
```  
  
### Parameters  
 *gaFlags*  
 Specifies the ancestor to be retrieved. For a complete list of possible values, see [GetAncestor](http://msdn.microsoft.com/library/windows/desktop/ms633502).  
  
### Return Value  
 If the function succeeds, the return value is a pointer to the ancestor window object. If the function fails, the return value is **NULL**.  
  
### Remarks  
 This member function emulates the functionality of the function [GetAncestor](http://msdn.microsoft.com/library/windows/desktop/ms633502), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcapture"></a>  CWnd::GetCapture  
 Retrieves the window that has the mouse capture.  
  
```  
静的 CWnd * PASCAL GetCapture() です。
```  
  
### Return Value  
 Identifies the window that has the mouse capture. It is **NULL** if no window has the mouse capture.  
  
 The return value may be temporary and should not be stored for later use.  
  
### Remarks  
 Only one window has the mouse capture at any given time. A window receives the mouse capture when the [SetCapture](#setcapture) member function is called. This window receives mouse input whether or not the cursor is within its borders.  
  
##  <a name="getcaretpos"></a>  CWnd::GetCaretPos  
 Retrieves the client coordinates of the caret's current position and returns them as a `CPoint`.  
  
```  
静的 CPoint PASCAL GetCaretPos() です。
```  
  
### Return Value  
 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object containing the coordinates of the caret's position.  
  
### Remarks  
 The caret position is given in the client coordinates of the `CWnd` window.  
  
##  <a name="getcheckedradiobutton"></a>  CWnd::GetCheckedRadioButton  
 Retrieves the ID of the currently checked radio button in the specified group.  
  
```  
int GetCheckedRadioButton (int nIDFirstButton、  
    int nIDLastButton) です。
```  
  
### Parameters  
 `nIDFirstButton`  
 Specifies the integer identifier of the first radio button in the group.  
  
 `nIDLastButton`  
 Specifies the integer identifier of the last radio button in the group.  
  
### Return Value  
 ID of the checked radio button, or 0 if none is selected.  
  
##  <a name="getclientrect"></a>  CWnd::GetClientRect  
 Copies the client coordinates of the `CWnd` client area into the structure pointed to by `lpRect`.  
  
```  
void GetClientRect (LPRECT lpRect) const です。  
```  
  
### Parameters  
 `lpRect`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) or a `CRect` object to receive the client coordinates. The **left** and **top** members will be 0. The **right** and **bottom** members will contain the width and height of the window.  
  
### Remarks  
 The client coordinates specify the upper-left and lower-right corners of the client area. Since client coordinates are relative to the upper-left corners of the `CWnd` client area, the coordinates of the upper-left corner are (0,0).  
  
### Example  
  See the example for [CWnd::IsIconic](#isiconic).  
  
##  <a name="getclipboardowner"></a>  CWnd::GetClipboardOwner  
 Retrieves the current owner of the Clipboard.  
  
```  
静的 CWnd * PASCAL GetClipboardOwner() です。
```  
  
### Return Value  
 Identifies the window that owns the Clipboard if the function is successful. Otherwise, it is **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The Clipboard can still contain data even if it is not currently owned.  
  
##  <a name="getclipboardviewer"></a>  CWnd::GetClipboardViewer  
 Retrieves the first window in the Clipboard-viewer chain.  
  
```  
静的 CWnd * PASCAL GetClipboardViewer() です。
```  
  
### Return Value  
 Identifies the window currently responsible for displaying the Clipboard if successful; otherwise **NULL** (for example, if there is no viewer).  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
##  <a name="getcontrolunknown"></a>  CWnd::GetControlUnknown  
 Call this member function to retrieve a pointer to an unknown OLE control.  
  
```  
LPUNKNOWN GetControlUnknown() です。
```  
  
### Return Value  
 A pointer to the [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) interface of the OLE control represented by this `CWnd` object. If this object does not represent an OLE control, the return value is **NULL**.  
  
### Remarks  
 You should not release this **IUnknown** pointer. Typically, you would use to obtain a specific interface of the control.  
  
 The interface pointer returned by **GetControlUnknown** is not reference-counted. Do not call [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) on the pointer unless you have previously called [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) on it.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#96](../../mfc/reference/codesnippet/cpp/cwnd-class_35.cpp)]  
  
##  <a name="getcurrentmessage"></a>  CWnd::GetCurrentMessage  
 Returns a pointer to the message this window is currently processing. Should only be called when in an **On***Message* message-handler member function.  
  
```  
静的 const MSG * PASCAL GetCurrentMessage() です。
```  
  
### Return Value  
 Returns a pointer to the [MSG](../../mfc/reference/msg-structure1.md) structure that contains the message the window is currently processing. Should only be called when in an **On***Message* handler.  
  
### Example  
  See the example for [CMDIFrameWnd::MDICascade](../../mfc/reference/cmdiframewnd-class.md#mdicascade).  
  
##  <a name="getdc"></a>  CWnd::GetDC  
 Retrieves a pointer to a common, class, or private device context for the client area depending on the class style specified for the `CWnd`.  
  
```  
CDC * GetDC() です。
```  
  
### Return Value  
 Identifies the device context for the `CWnd` client area if successful; otherwise, the return value is **NULL**. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 For common device contexts, `GetDC` assigns default attributes to the context each time it is retrieved. For class and private contexts, `GetDC` leaves the previously assigned attributes unchanged. The device context can be used in subsequent graphics device interface (GDI) functions to draw in the client area.  
  
 Unless the device context belongs to a window class, the [ReleaseDC](#releasedc) member function must be called to release the context after painting.  
  
 A device context belonging to the `CWnd` class is returned by the `GetDC` member function if **CS_CLASSDC**, **CS_OWNDC**, or **CS_PARENTDC** was specified as a style in the **WNDCLASS** structure when the class was registered.  
  
##  <a name="getdcex"></a>  CWnd::GetDCEx  
 Retrieves the handle of a device context for the `CWnd` window.  
  
```  
CDC* GetDCEx (CRgn* prgnClip、  
    DWORD フラグ)
```  
  
### Parameters  
 `prgnClip`  
 Identifies a clipping region that may be combined with the visible region of the client window.  
  
 `flags`  
 Can have one of the following preset values:  
  
- **DCX_CACHE** Returns a device context from the cache rather than the **OWNDC** or **CLASSDC** window. Overrides **CS_OWNDC** and **CS_CLASSDC**.  
  
- **DCX_CLIPCHILDREN** Excludes the visible regions of all child windows below the `CWnd` window.  
  
- **DCX_CLIPSIBLINGS** Excludes the visible regions of all sibling windows above the `CWnd` window.  
  
- **DCX_EXCLUDERGN** Excludes the clipping region identified by `prgnClip` from the visible region of the returned device context.  
  
- **DCX_INTERSECTRGN** Intersects the clipping region identified by `prgnClip` within the visible region of the returned device context.  
  
- **DCX_LOCKWINDOWUPDATE** Allows drawing even if there is a `LockWindowUpdate` call in effect that would otherwise exclude this window. This value is used for drawing during tracking.  
  
- **DCX_PARENTCLIP** Uses the visible region of the parent window and ignores the parent window's **WS_CLIPCHILDREN** and **WS_PARENTDC** style bits. This value sets the device context's origin to the upper-left corner of the `CWnd` window.  
  
- **DCX_WINDOW** Returns a device context that corresponds to the window rectangle rather than the client rectangle.  
  
### Return Value  
 The device context for the specified window if the function is successful; otherwise **NULL**.  
  
### Remarks  
 The device context can be used in subsequent GDI functions to draw in the client area.  
  
 This function, which is an extension to the [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) function, gives an application more control over how and whether a device context for a window is clipped.  
  
 Unless the device context belongs to a window class, the [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) function must be called to release the context after drawing. Since only five common device contexts are available at any given time, failure to release a device context can prevent other applications from gaining access to a device context.  
  
 To obtain a cached device context, an application must specify [DCX_CACHE](http://msdn.microsoft.com/library/windows/desktop/dd144873). If **DCX_CACHE** is not specified and the window is neither **CS_OWNDC** nor [CS_CLASSDC](http://msdn.microsoft.com/library/windows/desktop/ms633576), this function returns **NULL**.  
  
 A device context with special characteristics is returned by the [GetDCEx](http://msdn.microsoft.com/library/windows/desktop/dd144873) function if the **CS_CLASSDC**, [CS_OWNDC](http://msdn.microsoft.com/library/windows/desktop/ms633576), or [CS_PARENTDC](http://msdn.microsoft.com/library/windows/desktop/ms633576) style was specified in the [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure when the class was registered.  
  
 For more information about these characteristics, see the description of the **WNDCLASS** structure in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdcrendertarget"></a>  CWnd::GetDCRenderTarget  
 Retrieves the device context (DC) render target for the `CWnd` window.  
  
```  
CDCRenderTarget * GetDCRenderTarget() です。
```  
  
### Return Value  
 The device context render target for the specified window if the function is successful; otherwise **NULL**.  
  
### Remarks  
  
##  <a name="getdescendantwindow"></a>  CWnd::GetDescendantWindow  
 Call this member function to find the descendant window specified by the given ID.  
  
```  
CWnd * GetDescendantWindow (int では、  
    BOOL bOnlyPerm = FALSE) const です。  
```  
  
### Parameters  
 `nID`  
 Specifies the identifier of the control or child window to be retrieved.  
  
 `bOnlyPerm`  
 Specifies whether the window to be returned can be temporary. If **TRUE**, only a permanent window can be returned; if **FALSE,** the function can return a temporary window. For more information on temporary windows see [Technical Note 3](../../mfc/tn003-mapping-of-windows-handles-to-objects.md).  
  
### Return Value  
 A pointer to a `CWnd` object, or **NULL** if no child window is found.  
  
### Remarks  
 This member function searches the entire tree of child windows, not only the windows that are immediate children.  
  
##  <a name="getdesktopwindow"></a>  CWnd::GetDesktopWindow  
 Returns the Windows desktop window.  
  
```  
静的 CWnd * PASCAL GetDesktopWindow() です。
```  
  
### Return Value  
 Identifies the Windows desktop window. This pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The desktop window covers the entire screen and is the area on top of which all icons and other windows are painted.  
  
##  <a name="getdlgctrlid"></a>  CWnd::GetDlgCtrlID  
 Returns the window or control ID value for any child window, not only that of a control in a dialog box.  
  
```  
int GetDlgCtrlID() const です。  
```  
  
### Return Value  
 The numeric identifier of the `CWnd` child window if the function is successful; otherwise 0.  
  
### Remarks  
 Since top-level windows do not have an ID value, the return value of this function is invalid if the `CWnd` is a top-level window.  
  
### Example  
  See the example for [CWnd::OnCtlColor](#onctlcolor).  
  
##  <a name="getdlgitem"></a>  CWnd::GetDlgItem  
 Retrieves a pointer to the specified control or child window in a dialog box or other window.  
  
```  
CWnd * GetDlgItem(int nID) const です。  
  
(int では、コードを無効にします。  
    HWND* phWnd) const です。  
```  
  
### Parameters  
 `nID`  
 Specifies the identifier of the control or child window to be retrieved.  
  
 `phWnd`  
 A pointer to a child window.  
  
### Return Value  
 A pointer to the given control or child window. If no control with the integer ID given by the `nID` parameter exists, the value is **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The pointer returned is usually cast to the type of control identified by `nID`.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#97](../../mfc/reference/codesnippet/cpp/cwnd-class_36.cpp)]  
  
##  <a name="getdlgitemint"></a>  CWnd::GetDlgItemInt  
 Retrieves the text of the control identified by `nID`.  
  
```  
UINT GetDlgItemInt (int では、  
    BOOL * lpTrans = NULL の場合、  
    BOOL bSigned = TRUE) const です。  
```  
  
### Parameters  
 `nID`  
 Specifies the integer identifier of the dialog-box control to be translated.  
  
 `lpTrans`  
 Points to the Boolean variable that is to receive the translated flag.  
  
 `bSigned`  
 Specifies whether the value to be retrieved is signed.  
  
### Return Value  
 Specifies the translated value of the dialog-box item text. Since 0 is a valid return value, `lpTrans` must be used to detect errors. If a signed return value is desired, cast it as an `int` type.  
  
 The function returns 0 if the translated number is greater than INT_MAX (for signed numbers) or UINT_MAX (for unsigned).  
  
 When errors occur, such as encountering nonnumeric characters and exceeding the above maximum, `GetDlgItemInt` copies 0 to the location pointed to by `lpTrans`. If there are no errors, `lpTrans` receives a nonzero value. If `lpTrans` is **NULL**, `GetDlgItemInt` does not warn about errors.  
  
### Remarks  
 It translates the text of the specified control in the given dialog box into an integer value by stripping any extra spaces at the beginning of the text and converting decimal digits. It stops the translation when it reaches the end of the text or encounters any nonnumeric character.  
  
 If `bSigned` is **TRUE**, `GetDlgItemInt` checks for a minus sign (–) at the beginning of the text and translates the text into a signed number. Otherwise, it creates an unsigned value.  
  
 It sends a [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627) message to the control.  
  
##  <a name="getdlgitemtext"></a>  CWnd::GetDlgItemText  
 Call this member function to retrieve the title or text associated with a control in a dialog box.  
  
```  
int GetDlgItemText (int では、  
    LPTSTR lpStr  
    int nMaxCount) const です。  
  
int GetDlgItemText (int では、  
    CString >/reportbuilder/reportbuilder_3_0_0_0.application rString) const です。  
```  
  
### Parameters  
 `nID`  
 Specifies the integer identifier of the control whose title is to be retrieved.  
  
 `lpStr`  
 Points to the buffer to receive the control's title or text.  
  
 `nMaxCount`  
 Specifies the maximum length (in characters) of the string to be copied to `lpStr`. If the string is longer than `nMaxCount`, it is truncated.  
  
 `rString`  
 A reference to a [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### Return Value  
 Specifies the actual number of characters copied to the buffer, not including the terminating null character. The value is 0 if no text is copied.  
  
### Remarks  
 The `GetDlgItemText` member function copies the text to the location pointed to by `lpStr` and returns a count of the number of bytes it copies.  
  
##  <a name="getdsccursor"></a>  CWnd::GetDSCCursor  
 Call this member function to retrieve a pointer to the underlying cursor that is defined by the DataSource, UserName, Password, and SQL properties of the data-source control.  
  
```  
IUnknown * GetDSCCursor() です。
```  
  
### Return Value  
 A pointer to a cursor that is defined by a data-source control. MFC takes care of calling `AddRef` for the pointer.  
  
### Remarks  
 Use the returned pointer to set the ICursor property of a complex data-bound control, such as the data-bound grid control. A data-source control will not become active until the first bound control requests its cursor. This can happen either explicitly by a call to `GetDSCCursor` or implicitly by the MFC binding manager. In either case, you can force a data-source control to become active by calling `GetDSCCursor` and then calling **Release** on the returned pointer to **IUnknown**. Activation will cause the data-source control to attempt to connect to the underlying data source. The returned pointer might be used in the following context:  
  
### Example  
 [!code-cpp[NVC_MFC_AxDataBinding#1](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#5](../../mfc/reference/codesnippet/cpp/cwnd-class_37.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#3](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="getdynamiclayout"></a>  CWnd::GetDynamicLayout  
 Retrieves a pointer to the dynamic layout manager object.  
  
```  
CMFCDynamicLayout * GetDynamicLayout() です。
```  
  
### Return Value  
 A pointer to the dynamic layout manager object, or NULL if dynamic layout is not enabled.  
  
### Remarks  
 The window object owns and manages the lifetime of the returned pointer, so it should only be used to access the object; do not delete the pointer or store the pointer permanently.  
  
##  <a name="getexstyle"></a>  CWnd::GetExStyle  
 Returns the window's extended style.  
  
```  
DWORD GetExStyle() const です。  
```  
  
### Return Value  
 The window's extended style. For more information about the extended window styles used in MFC, see [Extended Window Styles](../../mfc/reference/extended-window-styles.md).  
  
##  <a name="getfocus"></a>  CWnd::GetFocus  
 Retrieves a pointer to the `CWnd` that currently has the input focus.  
  
```  
静的 CWnd * PASCAL GetFocus() です。
```  
  
### Return Value  
 A pointer to the window that has the current focus, or **NULL** if there is no focus window.  
  
 The pointer may be temporary and should not be stored for later use.  
  
##  <a name="getfont"></a>  CWnd::GetFont  
 Sends the `WM_GETFONT` message to the window to retrieve the current font.  
  
```  
CFont * GetFont() const です。  
```  
  
### Return Value  
 Pointer to a [CFont](../../mfc/reference/cfont-class.md) object that is attached to the current font for the window.  
  
### Remarks  
 This method has no effect unless the window processes the `WM_GETFONT` message. Many MFC classes that derive from `CWnd` process this message because they are attached to a predefined window class that includes a message handler for the `WM_GETFONT` message. To use this method, classes that you derive from `CWnd` must define a method handler for the `WM_GETFONT` message.  
  
##  <a name="getforegroundwindow"></a>  CWnd::GetForegroundWindow  
 Returns a pointer to the foreground window (the window with which the user is currently working).  
  
```  
静的 CWnd * PASCAL GetForegroundWindow() です。
```  
  
### Return Value  
 A pointer to the foreground window. This may be a temporary `CWnd` object.  
  
### Remarks  
 The foreground window applies only to top-level windows (frame windows or dialog boxes).  
  
##  <a name="geticon"></a>  CWnd::GetIcon  
 Call this member function to get the handle to either a big (32x32) or the handle to a small (16x16) icon, as indicated by `bBigIcon`.  
  
```  
HICON GetIcon(BOOL bBigIcon) const です。  
```  
  
### Parameters  
 `bBigIcon`  
 Specifies a 32 pixel by 32 pixel icon if **TRUE**; specifies a 16 pixel by 16 pixel icon if **FALSE**.  
  
### Return Value  
 A handle to an icon. If unsuccessful, returns **NULL**.  
  
##  <a name="getlastactivepopup"></a>  CWnd::GetLastActivePopup  
 Determines which pop-up window owned by `CWnd` was most recently active.  
  
```  
CWnd * GetLastActivePopup() const です。  
```  
  
### Return Value  
 Identifies the most recently active pop-up window. The return value will be the window itself if any of the following conditions are met:  
  
-   The window itself was most recently active.  
  
-   The window does not own any pop-up windows.  
  
-   The window is not a top-level window or is owned by another window.  
  
 The pointer may be temporary and should not be stored for later use.  
  
### Example  
  See the example for [CWnd::FindWindow](#findwindow).  
  
##  <a name="getlayeredwindowattributes"></a>  CWnd::GetLayeredWindowAttributes  
 Retrieves the opacity and transparency color key of a layered window.  
  
```  
BOOL GetLayeredWindowAttributes (COLORREF* pcrKey バイト*pbAlpha、  
    DWORD* pdwFlags) const です。  
```  
  
### Parameters  
 *pcrKey*  
 Pointer to a **COLORREF** value that receives the transparency color key to be used when composing the layered window. All pixels painted by the window in this color will be transparent. This can be **NULL** if the argument is not needed.  
  
 `pbAlpha`  
 Pointer to a **BYTE** that receives the Alpha value used to describe the opacity of the layered window. When the variable referred to by `pbAlpha` is 0, the window is completely transparent. When the variable referred to by `pbAlpha` is 255, the window is opaque. This can be **NULL** if the argument is not needed.  
  
 *pdwFlags*  
 Pointer to a `DWORD` that receives a layering flag. This can be **NULL** if the argument is not needed. For a complete list of possible values, see [GetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633508).  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [GetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633508), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getmenu"></a>  CWnd::GetMenu  
 Retrieves a pointer to the menu for this window.  
  
```  
CMenu * GetMenu() const です。  
```  
  
### Return Value  
 Identifies the menu. The value is **NULL** if `CWnd` has no menu. The return value is undefined if `CWnd` is a child window.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 This function should not be used for child windows because they do not have a menu.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#98](../../mfc/reference/codesnippet/cpp/cwnd-class_38.cpp)]  
  
##  <a name="getmenubarinfo"></a>  CWnd::GetMenuBarInfo  
 Retrieves information about the specified menu bar.  
  
```  
BOOL GetMenuBarInfo (長い idObject、  
    長い idItem  
    PMENUBARINFO pmbi) const です。  
```  
  
### Parameters  
 `idObject`  
 Specifies the menu object. For a list of possible values, see [GetMenuBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms647833).  
  
 `idItem`  
 Specifies the item for which to retrieve information. If this parameter is zero, the function retrieves information about the menu itself. If this parameter is 1, the function retrieves information about the first item on the menu, and so on.  
  
 *pmbi*  
 Pointer to a [MENUBARINFO](http://msdn.microsoft.com/library/windows/desktop/ms647564) structure that receives the information.  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [GetMenuBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms647833), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getnextdlggroupitem"></a>  CWnd::GetNextDlgGroupItem  
 Searches for the previous or next control within a group of controls in a dialog box.  
  
```  
CWnd* GetNextDlgGroupItem (CWnd* pWndCtl、  
    BOOL bPrevious = FALSE) const です。  
  
COleControlSiteOrWnd* GetNextDlgGroupItem (COleControlSiteOrWnd* pCurSiteOrWnd = NULL) const です。  
```  
  
### Parameters  
 `pWndCtl`  
 Identifies the control to be used as the starting point for the search.  
  
 `bPrevious`  
 Specifies how the function is to search the group of controls in the dialog box. If **TRUE**, the function searches for the previous control in the group; if **FALSE**, it searches for the next control in the group.  
  
 `pCurSiteOrWnd`  
 Identifies the **COleControlSiteOrWnd** control. For more information about `COleControlSiteOrWnd`, see **Remarks**.  
  
### Return Value  
 Pointer to the previous or next control in the group if the member function is successful.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 A group of controls begins with a control that was created with the [WS_GROUP](../../mfc/reference/window-styles.md) style and ends with the last control that was not created with the **WS_GROUP** style.  
  
 By default, the `GetNextDlgGroupItem` member function returns a pointer to the next control in the group. If `pWndCtl` identifies the first control in the group and `bPrevious` is **TRUE**, `GetNextDlgGroupItem` returns a pointer to the last control in the group.  
  
> [!NOTE]
>  Because MFC supports windowless ActiveX controls, standard ActiveX controls, and windows, referring to a control by only an HWND no longer suffices. The `COleControlSiteOrWnd` object includes information that identifies the object as a windowed ActiveX control, a windowless ActiveX control, or a window, as follows:  
  
|Control or window type|Identifying information|  
|----------------------------|-----------------------------|  
|Windowed ActiveX control|Contains an HWND and associates a [COleControlSite](../../mfc/reference/colecontrolsite-class.md) object with it. The `m_hWnd` member of `COleControlSiteOrWnd` is set to the HWND of the control, and the **m_pSite** member points to the control's `COleControlSite`.|  
|Windowless ActiveX control|Contains no `HWND`. The **m_pSite** member of `COleControlSiteOrWnd` points to the control's `COleControlSite`, and the **m_hWnd** member is **NULL**.|  
|Standard window|Contains just an `HWND`. The `m_hWnd` member of `COleControlSiteOrWnd` is set to the `HWND` of the window, and the **m_pSite** member is **NULL**.|  
  
##  <a name="getnextdlgtabitem"></a>  CWnd::GetNextDlgTabItem  
 Retrieves a pointer to the first control that was created with the [WS_TABSTOP](window-styles.md) style and that precedes or follows the specified control.  
  
```  
CWnd* GetNextDlgTabItem (CWnd* pWndCtl、  
    BOOL bPrevious = FALSE) const です。  
  
COleControlSiteOrWnd* GetNextDlgTabItem (COleControlSiteOrWnd* pCurSiteOrWnd、  
    BOOL bPrevious) const です。  
```  
  
### Parameters  
 `pWndCtl`  
 Identifies the control to be used as the starting point for the search.  
  
 `pCurSiteOrWnd`  
 Identifies the **COleControlSiteOrWnd** control. For more information about `COleControlSiteOrWnd`, see [CWnd::GetNextDlgGroupItem](#getnextdlggroupitem).  
  
 `bPrevious`  
 Specifies how the function is to search the dialog box. If **TRUE**, the function searches for the previous control in the dialog box; if **FALSE**, it searches for the next control.  
  
### Return Value  
 Pointer to the previous or next control that has the **WS_TABSTOP** style, if the member function is successful.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
 For more information about `COleControlSiteOrWnd`, see [CWnd::GetNextDlgGroupItem](#getnextdlggroupitem).  
  
##  <a name="getnextwindow"></a>  CWnd::GetNextWindow  
 Searches for the next (or previous) window in the window manager's list.  
  
```  
CWnd * GetNextWindow(UINT nFlag = GW_HWNDNEXT) const です。  
```  
  
### Parameters  
 `nFlag`  
 Specifies whether the function returns a pointer to the next window or the previous window. It can be either **GW_HWNDNEXT**, which returns the window that follows the `CWnd` object on the window manager's list, or **GW_HWNDPREV**, which returns the previous window on the window manager's list.  
  
### Return Value  
 Identifies the next (or the previous) window in the window manager's list if the member function is successful.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The window manager's list contains entries for all top-level windows, their associated child windows, and the child windows of any child windows.  
  
 If `CWnd` is a top-level window, the function searches for the next (or previous) top-level window; if `CWnd` is a child window, the function searches for the next (or previous) child window.  
  
##  <a name="getolecontrolsite"></a>  CWnd::GetOleControlSite  
 Retrieves the custom site for the specified ActiveX control.  
  
```  
メンバー * GetOleControlSite(UINT idControl) const です。  
```  
  
### Parameters  
 `idControl`  
 The ID of the ActiveX control.  
  
##  <a name="getopenclipboardwindow"></a>  CWnd::GetOpenClipboardWindow  
 Retrieves the handle of the window that currently has the Clipboard open.  
  
```  
静的 CWnd * PASCAL GetOpenClipboardWindow() です。
```  
  
### Return Value  
 The handle of the window that currently has the Clipboard open if the function is successful; otherwise **NULL**.  
  
##  <a name="getowner"></a>  CWnd::GetOwner  
 Retrieves a pointer to the owner of the window.  
  
```  
CWnd * GetOwner() const です。  
```  
  
### Return Value  
 A pointer to a `CWnd` object.  
  
### Remarks  
 If the window has no owner, then a pointer to the parent window object is returned by default. Note that the relationship between the owner and the owned differs from the parent-child aspect in several important aspects. For example, a window with a parent is confined to its parent window's client area. Owned windows can be drawn at any location on the desktop.  
  
 The ownership concept of this function is different from the ownership concept of [GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms633515).  
  
##  <a name="getparent"></a>  CWnd::GetParent  
 Call this function to get a pointer to a child window's parent window (if any).  
  
```  
CWnd * GetParent() const です。  
```  
  
### Return Value  
 See the Return Values section in [GetParent](http://msdn.microsoft.com/library/windows/desktop/ms633510) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 The `GetParent` function returns a pointer to the immediate parent (if it exists). In contrast, the [GetParentOwner](#getparentowner) function returns a pointer to the most immediate parent or owner window that is not a child window (does not have the **WS_CHILD** style). If you have a child window within a child window `GetParent` and `GetParentOwner` return different results.  
  
##  <a name="getparentframe"></a>  CWnd::GetParentFrame  
 Call this member function to retrieve the parent frame window.  
  
```  
CFrameWnd * GetParentFrame() const です。  
```  
  
### Return Value  
 A pointer to a frame window if successful; otherwise **NULL**.  
  
### Remarks  
 The member function searches up the parent chain until a [CFrameWnd](../../mfc/reference/cframewnd-class.md) (or derived class) object is found.  
  
##  <a name="getparentowner"></a>  CWnd::GetParentOwner  
 Call this member function to get a pointer to a child window's parent window or owner window.  
  
```  
CWnd * GetParentOwner() const です。  
```  
  
### Return Value  
 A pointer to a `CWnd` object. If a `CWnd` object is not attached to the handle, a temporary `CWnd` object is created and attached. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 `GetParentOwner` returns a pointer to the most immediate parent or owner window that is not a child window (does not have the **WS_CHILD** style). The current owner window can be set with [SetOwner](#setowner). By default, the parent of a window is its owner.  
  
 In contrast, the [GetParent](#getparent) function returns a pointer to the immediate parent, whether it is a child window or not. If you have a child window within a child window `GetParent` and `GetParentOwner` return different results.  
  
##  <a name="getproperty"></a>  CWnd::GetProperty  
 Call this member function to get the ActiveX control property specified by `dwDispID`.  
  
```  
void GetProperty (DISPID dwDispID、  
    VARTYPE vtProp  
    void * pvProp) const です。  
```  
  
### Parameters  
 `dwDispID`  
 Identifies the property to be retrieved.  
  
 `vtProp`  
 Specifies the type of the property to be retrieved. For possible values, see the Remarks section for [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvProp`  
 Address of the variable that will that will receive the property value. It must match the type specified by `vtProp`.  
  
### Remarks  
 **GetProperty** returns the value through `pvProp`.  
  
> [!NOTE]
>  This function should be called only on a `CWnd` object that represents an ActiveX control.  
  
 For more information about using this member function with ActiveX Control Containers, see the article [ActiveX Control Containers: Programming ActiveX Controls in an ActiveX Control Container](../../mfc/programming-activex-controls-in-a-activex-control-container.md).  
  
##  <a name="getrendertarget"></a>  CWnd::GetRenderTarget  
 Gets a render target that is associated with this window.  
  
```  
CHwndRenderTarget * GetRenderTarget() です。
```  
  
### Return Value  
 Pointer to the render target or NULL.  
  
##  <a name="getsafehwnd"></a>  CWnd::GetSafeHwnd  
 Returns `m_hWnd`, or **NULL** if the **this** pointer is **NULL**.  
  
```  
HWND GetSafeHwnd() const です。  
```  
  
### Return Value  
 Returns the window handle for a window. Returns **NULL** if the `CWnd` is not attached to a window or if it is used with a **NULL CWnd** pointer.  
  
### Example  
  See the example for [CWnd::SubclassWindow](#subclasswindow).  
  
##  <a name="getsafeowner"></a>  CWnd::GetSafeOwner  
 Call this member function to retrieve the owner window that should be used for dialog boxes or other modal windows.  
  
```  
静的 CWnd* GetSafeOwner (CWnd* pParent = NULL の場合、  
    HWND* pWndTop = NULL);
```  
  
### Parameters  
 `pParent`  
 A pointer to a parent `CWnd` window. May be **NULL**.  
  
 *pWndTop*  
 A pointer to the window that is currently on top. May be **NULL**.  
  
### Return Value  
 A pointer to the safe owner for the given window.  
  
### Remarks  
 The safe owner is the first non-child parent window of `pParent`. If `pParent` is **NULL**, the thread's main window (retrieved via [AfxGetMainWnd](../../mfc/reference/application-information-and-management.md#afxgetmainwnd)) is used to find an owner.  
  
> [!NOTE]
>  The framework itself uses this function to determine the correct owner window for dialog boxes and property sheets where the owner is not specified.  
  
##  <a name="getscrollbarctrl"></a>  CWnd::GetScrollBarCtrl  
 Call this member function to obtain a pointer to the specified sibling scroll bar or splitter window.  
  
```  
仮想関数 * GetScrollBarCtrl(int nBar) const です。  
```  
  
### Parameters  
 `nBar`  
 Specifies the type of scroll bar. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the position of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the position of the vertical scroll bar.  
  
### Return Value  
 A sibling scroll-bar control, or **NULL** if none.  
  
### Remarks  
 This member function does not operate on scroll bars created when the **WS_HSCROLL** or **WS_VSCROLL** bits are set during the creation of a window. The `CWnd` implementation of this function simply returns **NULL**. Derived classes, such as `CView`, implement the described functionality.  
  
##  <a name="getscrollbarinfo"></a>  CWnd::GetScrollBarInfo  
 Retrieves information about the specified scroll bar.  
  
```  
BOOL GetScrollBarInfo (長い idObject、  
    PSCROLLBARINFO psbi) const です。  
```  
  
### Parameters  
 `idObject`  
 Specifies the menu object. For a list of possible values, see [GetScrollBarInfo](http://msdn.microsoft.com/library/windows/desktop/bb787581).  
  
 *psbi*  
 Pointer to a [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535) structure that receives the information.  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [GetScrollBarInfo](http://msdn.microsoft.com/library/windows/desktop/bb787581), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getscrollinfo"></a>  CWnd::GetScrollInfo  
 Call this member function to retrieve the information that the `SCROLLINFO` structure maintains about a scroll bar.  
  
```  
BOOL GetScrollInfo (int れる、  
    LPSCROLLINFO lpScrollInfo  
    UINT いる = SIF_ALL) です。
```  
  
### Parameters  
 `nBar`  
 Specifies whether the scroll bar is a control or part of a window's nonclient area. If it is part of the nonclient area, `nBar` also indicates whether the scroll bar is positioned horizontally, vertically, or both. It must be one of the following:  
  
- **SB_CTL** Retrieves the parameters for a scroll bar control. The `m_hWnd` data member must be the handle of the scroll bar control.  
  
- **SB_HORZ** Retrieves the parameters for the window's standard horizontal scroll bar.  
  
- **SB_VERT** Retrieves the parameters for the window's standard vertical scroll bar.  
  
 `lpScrollInfo`  
 A pointer to a [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) structure. See the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for more information about this structure.  
  
 `nMask`  
 Specifies the scroll bar parameters to retrieve. The default specifies a combination of **SIF_PAGE**, **SIF_POS**, **SIF_TRACKPOS**, and **SIF_RANGE**. See `SCROLLINFO` for more information on the *nMask* values.  
  
### Return Value  
 If the message retrieved any values, the return is **TRUE**. Otherwise, it is **FALSE**.  
  
### Remarks  
 `GetScrollInfo` enables applications to use 32-bit scroll positions.  
  
 The [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) structure contains information about a scroll bar, including the minimum and maximum scrolling positions, the page size, and the position of the scroll box (the thumb). See the `SCROLLINFO` structure topic in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for more information about changing the structure defaults.  
  
 The MFC Windows message handlers that indicate scroll-bar position, [CWnd::OnHScroll](#onhscroll) and [CWnd::OnVScroll](#onvscroll), provide only 16 bits of position data. `GetScrollInfo` and `SetScrollInfo` provide 32 bits of scroll-bar position data. Thus, an application can call `GetScrollInfo` while processing either `CWnd::OnHScroll` or `CWnd::OnVScroll` to obtain 32-bit scroll-bar position data.  
  
##  <a name="getscrolllimit"></a>  CWnd::GetScrollLimit  
 Call this member function to retrieve the maximum scrolling position of the scroll bar.  
  
```  
int GetScrollLimit (int れる) です。
```  
  
### Parameters  
 `nBar`  
 Specifies the type of scroll bar. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the scroll limit of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the scroll limit of the vertical scroll bar.  
  
### Return Value  
 Specifies the maximum position of a scroll bar if successful; otherwise 0.  
  
##  <a name="getscrollpos"></a>  CWnd::GetScrollPos  
 Retrieves the current position of the scroll box of a scroll bar.  
  
```  
int GetScrollPos (int れる) const です。  
```  
  
### Parameters  
 `nBar`  
 Specifies the scroll bar to examine. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the position of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the position of the vertical scroll bar.  
  
### Return Value  
 Specifies the current position of the scroll box in the scroll bar if successful; otherwise 0.  
  
### Remarks  
 The current position is a relative value that depends on the current scrolling range. For example, if the scrolling range is 50 to 100 and the scroll box is in the middle of the bar, the current position is 75.  
  
##  <a name="getscrollrange"></a>  CWnd::GetScrollRange  
 Copies the current minimum and maximum scroll-bar positions for the given scroll bar to the locations specified by `lpMinPos` and `lpMaxPos`.  
  
```  
void GetScrollRange (int れる、  
    LPINT lpMinPos  
    LPINT 最大位置) const です。  
```  
  
### Parameters  
 `nBar`  
 Specifies the scroll bar to examine. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the position of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the position of the vertical scroll bar.  
  
 `lpMinPos`  
 Points to the integer variable that is to receive the minimum position.  
  
 `lpMaxPos`  
 Points to the integer variable that is to receive the maximum position.  
  
### Remarks  
 If `CWnd` does not have a scroll bar, then the `GetScrollRange` member function copies 0 to `lpMinPos` and `lpMaxPos`.  
  
 The default range for a standard scroll bar is 0 to 100. The default range for a scroll-bar control is empty (both values are 0).  
  
##  <a name="getstyle"></a>  CWnd::GetStyle  
 Returns the current window style.  
  
```  
DWORD GetStyle() const です。  
```  
  
### Return Value  
 The window's style. For more information about the window styles used in MFC, see [Window Styles](../../mfc/reference/window-styles.md).  
  
##  <a name="getsystemmenu"></a>  CWnd::GetSystemMenu  
 Allows the application to access the Control menu for copying and modification.  
  
```  
CMenu * GetSystemMenu(BOOL bRevert) const です。  
```  
  
### Parameters  
 `bRevert`  
 Specifies the action to be taken. If `bRevert` is **FALSE**, `GetSystemMenu` returns a handle to a copy of the Control menu currently in use. This copy is initially identical to the Control menu but can be modified. If `bRevert` is **TRUE**, `GetSystemMenu` resets the Control menu back to the default state. The previous, possibly modified, Control menu, if any, is destroyed. The return value is undefined in this case.  
  
### Return Value  
 Identifies a copy of the Control menu if `bRevert` is **FALSE**. If `bRevert` is **TRUE**, the return value is undefined.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 Any window that does not use `GetSystemMenu` to make its own copy of the Control menu receives the standard Control menu.  
  
 The pointer returned by the `GetSystemMenu` member function can be used with the [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu), or [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu) functions to change the Control menu.  
  
 The Control menu initially contains items identified with various ID values such as **SC_CLOSE**, **SC_MOVE**, and **SC_SIZE**. Items on the Control menu generate [WM_SYSCOMMAND](#onsyscommand) messages. All predefined Control-menu items have ID numbers greater than 0xF000. If an application adds items to the Control menu, it should use ID numbers less than F000.  
  
 Windows may automatically make items unavailable on the standard Control menu. `CWnd` can carry out its own selection or unavailability by responding to the [WM_INITMENU](#oninitmenu) messages, which are sent before any menu is displayed.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#99](../../mfc/reference/codesnippet/cpp/cwnd-class_39.cpp)]  
  
##  <a name="gettitlebarinfo"></a>  CWnd::GetTitleBarInfo  
 Retrieves information about the specified title bar.  
  
```  
BOOL GetTitleBarInfo(PTITLEBARINFO pti) const です。  
```  
  
### Parameters  
 *pti*  
 Pointer to a [TITLEBARINFO](http://msdn.microsoft.com/library/windows/desktop/ms632608) structure that receives the information.  
  
### Remarks  
 This member function emulates the functionality of the function [GetTitleBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms633513), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettoplevelframe"></a>  CWnd::GetTopLevelFrame  
 Call this member function to retrieve the window's top level frame window, if any.  
  
```  
CFrameWnd * GetTopLevelFrame() const です。  
```  
  
### Return Value  
 Identifies the top-level frame window of the window.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 If `CWnd` has no attached window, or its top-level parent is not a [CFrameWnd](../../mfc/reference/cframewnd-class.md)-derived object, this function returns **NULL**.  
  
##  <a name="gettoplevelowner"></a>  CWnd::GetTopLevelOwner  
 Call this member function to retrieve the top-level window.  
  
```  
CWnd * GetTopLevelOwner() const です。  
```  
  
### Return Value  
 Identifies the top-level window. The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The top-level window is the window that is a child of the desktop. If `CWnd` has no attached window, this function returns **NULL**.  
  
##  <a name="gettoplevelparent"></a>  CWnd::GetTopLevelParent  
 Call this member function to retrieve the window's top-level parent.  
  
```  
CWnd * GetTopLevelParent() const です。  
```  
  
### Return Value  
 Identifies the top-level parent window of the window.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 `GetTopLevelParent` is similar to [GetTopLevelFrame](#gettoplevelframe) and [GetTopLevelOwner](#gettoplevelowner); however, it ignores the value set as the current owner window.  
  
##  <a name="gettopwindow"></a>  CWnd::GetTopWindow  
 Searches for the top-level child window that belongs to `CWnd`.  
  
```  
CWnd * GetTopWindow() const です。  
```  
  
### Return Value  
 Identifies the top-level child window in a `CWnd` linked list of child windows. If no child windows exist, the value is **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 If `CWnd` has no children, this function returns **NULL**.  
  
##  <a name="getupdaterect"></a>  CWnd::GetUpdateRect  
 Retrieves the coordinates of the smallest rectangle that completely encloses the update region.  
  
```  
BOOL GetUpdateRect (LPRECT lpRect、  
    BOOL あらゆる = FALSE);
```  
  
### Parameters  
 `lpRect`  
 Points to a `CRect` object or [RECT structure](../../mfc/reference/rect-structure1.md) that is to receive the client coordinates of the update that encloses the update region.  
  
 Set this parameter to **NULL** to determine whether an update region exists within the `CWnd`. If `lpRect` is **NULL**, the `GetUpdateRect` member function returns nonzero if an update region exists and 0 if one does not. This provides a way to determine whether a `WM_PAINT` message resulted from an invalid area. Do not set this parameter to **NULL** in Windows version 3.0 and earlier.  
  
 `bErase`  
 Specifies whether the background in the update region is to be erased.  
  
### Return Value  
 Specifies the status of the update region. The value is nonzero if the update region is not empty; otherwise 0.  
  
 If the `lpRect` parameter is set to **NULL**, the return value is nonzero if an update region exists; otherwise 0.  
  
### Remarks  
 If `CWnd` was created with the **CS_OWNDC** style and the mapping mode is not `MM_TEXT`, the `GetUpdateRect` member function gives the rectangle in logical coordinates. Otherwise, `GetUpdateRect` gives the rectangle in client coordinates. If there is no update region, `GetUpdateRect` sets the rectangle to be empty (sets all coordinates to 0).  
  
 The `bErase` parameter specifies whether `GetUpdateRect` should erase the background of the update region. If `bErase` is **TRUE** and the update region is not empty, the background is erased. To erase the background, `GetUpdateRect` sends the [WM_ERASEBKGND](#onerasebkgnd) message.  
  
 The update rectangle retrieved by the [BeginPaint](#beginpaint) member function is identical to that retrieved by the `GetUpdateRect` member function.  
  
 The `BeginPaint` member function automatically validates the update region, so any call to `GetUpdateRect` made immediately after a call to `BeginPaint` retrieves an empty update region.  
  
##  <a name="getupdatergn"></a>  CWnd::GetUpdateRgn  
 Retrieves the update region into a region identified by `pRgn`.  
  
```  
int GetUpdateRgn (CRgn * pRgn、  
    BOOL あらゆる = FALSE);
```  
  
### Parameters  
 `pRgn`  
 Identifies the update region.  
  
 `bErase`  
 Specifies whether the background will be erased and nonclient areas of child windows will be drawn. If the value is **FALSE**, no drawing is done.  
  
### Return Value  
 Specifies a short-integer flag that indicates the type of resulting region. The value can take any one of the following:  
  
- **SIMPLEREGION** The region has no overlapping borders.  
  
- **COMPLEXREGION** The region has overlapping borders.  
  
- **NULLREGION** The region is empty.  
  
- **ERROR** No region was created.  
  
### Remarks  
 The coordinates of this region are relative to the upper-left corner (client coordinates).  
  
 The [BeginPaint](#beginpaint) member function automatically validates the update region, so any call to `GetUpdateRgn` made immediately after a call to `BeginPaint` retrieves an empty update region.  
  
##  <a name="getwindow"></a>  CWnd::GetWindow  
 Returns a pointer to the window requested, or **NULL** if none.  
  
```  
CWnd * GetWindow(UINT nCmd) const です。  
```  
  
### Parameters  
 `nCmd`  
 Specifies the relationship between `CWnd` and the returned window. It can take one of the following values:  
  
- **GW_CHILD** Identifies the `CWnd` first child window.  
  
- **GW_HWNDFIRST** If `CWnd` is a child window, returns the first sibling window. Otherwise, it returns the first top-level window in the list.  
  
- **GW_HWNDLAST** If `CWnd` is a child window, returns the last sibling window. Otherwise, it returns the last top-level window in the list.  
  
- **GW_HWNDNEXT** Returns the next window on the window manager's list.  
  
- **GW_HWNDPREV** Returns the previous window on the window manager's list.  
  
- **GW_OWNER** Identifies the `CWnd` owner.  
  
### Return Value  
 The returned pointer may be temporary and should not be stored for later use.  
  
##  <a name="getwindowcontexthelpid"></a>  CWnd::GetWindowContextHelpId  
 Call this member function to retrieve the help context identifier, if any, associated with the window.  
  
```  
DWORD GetWindowContextHelpId() const です。  
```  
  
### Return Value  
 The help context identifier. Returns 0 if the window has none.  
  
##  <a name="getwindowedchildcount"></a>  CWnd::GetWindowedChildCount  
 Call this member function to retrieve the number of associated child windows.  
  
```  
長い GetWindowedChildCount() です。
```  
  
### Return Value  
 The number of child windows associated with the `CWnd` object.  
  
##  <a name="getwindowdc"></a>  CWnd::GetWindowDC  
 Retrieves the display context for the entire window, including caption bar, menus, and scroll bars.  
  
```  
CDC * GetWindowDC() です。
```  
  
### Return Value  
 Identifies the display context for the given window if the function is successful; otherwise **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use. [ReleaseDC](#releasedc) should be called once for each successful call to `GetWindowDC`.  
  
### Remarks  
 A window display context permits painting anywhere in `CWnd`, since the origin of the context is the upper-left corner of `CWnd` instead of the client area.  
  
 Default attributes are assigned to the display context each time it retrieves the context. Previous attributes are lost.  
  
 `GetWindowDC` is intended to be used for special painting effects within the `CWnd` nonclient area. Painting in nonclient areas of any window is not recommended.  
  
 The [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) Windows function can be used to retrieve the dimensions of various parts of the nonclient area, such as the caption bar, menu, and scroll bars.  
  
 After painting is complete, the [ReleaseDC](#releasedc) member function must be called to release the display context. Failure to release the display context will seriously affect painting requested by applications due to limitations on the number of device contexts that can be open at the same time.  
  
##  <a name="getwindowinfo"></a>  CWnd::GetWindowInfo  
 Retrieves information about the window.  
  
```  
BOOL GetWindowInfo(PWINDOWINFO pwi) const です。  
```  
  
### Parameters  
 *pwi*  
 A pointer to a [WINDOWINFO](http://msdn.microsoft.com/library/windows/desktop/ms632610) structure.  
  
### Remarks  
 This member function emulates the functionality of the function [GetWindowInfo](http://msdn.microsoft.com/library/windows/desktop/ms633516), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getwindowlesschildcount"></a>  CWnd::GetWindowlessChildCount  
 Retrieves the number of associated windowless child windows.  
  
```  
長い GetWindowlessChildCount() です。
```  
  
### Return Value  
 The number of windowless child windows associated with the `CWnd` object.  
  
##  <a name="getwindowplacement"></a>  CWnd::GetWindowPlacement  
 Retrieves the show state and the normal (restored), minimized, and maximized positions of a window.  
  
```  
BOOL GetWindowPlacement(WINDOWPLACEMENT* lpwndpl) const です。  
```  
  
### Parameters  
 `lpwndpl`  
 Points to the `WINDOWPLACEMENT` structure that receives the show state and position information.  
  
### Return Value  
 Nonzero if the function is successful; otherwise 0.  
  
### Remarks  
 The **flags** member of the [WINDOWPLACEMENT](../../mfc/reference/windowplacement-structure.md) structure retrieved by this function is always 0. If `CWnd` is maximized, the **showCmd** member of `WINDOWPLACEMENT` is **SW_SHOWMAXIMIZED**. If the window is minimized, it is **SW_SHOWMINIMIZED.** It is **SW_SHOWNORMAL** otherwise.  
  
##  <a name="getwindowrect"></a>  CWnd::GetWindowRect  
 Copies the dimensions of the bounding rectangle of the `CWnd` object to the structure pointed to by `lpRect`.  
  
```  
void GetWindowRect (LPRECT lpRect) const です。  
```  
  
### Parameters  
 `lpRect`  
 Points to a `CRect` object or a [RECT structure](../../mfc/reference/rect-structure1.md) that will receive the screen coordinates of the upper-left and lower-right corners.  
  
### Remarks  
 The dimensions are given in screen coordinates relative to the upper-left corner of the display screen. The dimensions of the caption, border, and scroll bars, if present, are included.  
  
##  <a name="getwindowrgn"></a>  CWnd::GetWindowRgn  
 Call this member function to get the window region of a window.  
  
```  
int GetWindowRgn (HRGN hRgn) const です。  
```  
  
### Parameters  
 `hRgn`  
 A handle to a window region.  
  
### Return Value  
 The return value specifies the type of the region that the function obtains. It can be one of the following values:  
  
- **NULLREGION** The region is empty.  
  
- **SIMPLEREGION** The region is a single rectangle.  
  
- **COMPLEXREGION** The region is more than one rectangle.  
  
- **ERROR** An error occurred; the region is unaffected.  
  
### Remarks  
 The window region determines the area within the window where the operating system permits drawing. The operating system does not display any portion of a window that lies outside of the window region.  
  
 The coordinates of a window's window region are relative to the upper-left corner of the window, not the client area of the window.  
  
 To set the window region of a window, call [CWnd::SetWindowRgn](#setwindowrgn).  
  
##  <a name="getwindowtext"></a>  CWnd::GetWindowText  
 Copies the `CWnd` caption title (if it has one) into the buffer pointed to by `lpszStringBuf` or into the destination string `rString`.  
  
```  
int GetWindowText (LPTSTR lpszStringBuf、  
    int nMaxCount) const です。  
  
GetWindowText (CString >/reportbuilder/reportbuilder_3_0_0_0.application rString) const; を無効にします。  
```  
  
### Parameters  
 `lpszStringBuf`  
 Points to the buffer that is to receive the copied string of the window's title.  
  
 `nMaxCount`  
 Specifies the maximum number of characters to be copied to the buffer, including the terminating null character. If the string is longer than the number of characters specified in `nMaxCount`, it is truncated.  
  
 `rString`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) object that is to receive the copied string of the window's title.  
  
### Return Value  
 Specifies the length, in characters, of the copied string, not including the terminating null character. It is 0 if `CWnd` has no caption or if the caption is empty.  
  
### Remarks  
 If the `CWnd` object is a control, the `GetWindowText` member function copies the text within the control instead of copying the caption.  
  
 This member function causes the [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627) message to be sent to the `CWnd` object.  
  
### Example  
  See the example for [CWnd::SetWindowText](#setwindowtext).  
  
##  <a name="getwindowtextlength"></a>  CWnd::GetWindowTextLength  
 Returns the length of the `CWnd` object caption title.  
  
```  
int GetWindowTextLength() const です。  
```  
  
### Return Value  
 Specifies the text length in characters, not including any null-termination character. The value is 0 if no such text exists.  
  
### Remarks  
 If `CWnd` is a control, the `GetWindowTextLength` member function returns the length of the text within the control instead of the caption.  
  
 This member function causes the [WM_GETTEXTLENGTH](http://msdn.microsoft.com/library/windows/desktop/ms632628) message to be sent to the `CWnd` object.  
  
### Example  
  See the example for [CWnd::SetWindowText](#setwindowtext).  
  
##  <a name="hidecaret"></a>  CWnd::HideCaret  
 Hides the caret by removing it from the display screen.  
  
```  
HideCaret(); を無効にします。
```  
  
### Remarks  
 Although the caret is no longer visible, it can be displayed again by using the [ShowCaret](#showcaret) member function. Hiding the caret does not destroy its current shape.  
  
 Hiding is cumulative. If `HideCaret` has been called five times in a row, the `ShowCaret` member function must be called five times before the caret will be shown.  
  
##  <a name="hilitemenuitem"></a>  CWnd::HiliteMenuItem  
 Highlights or removes the highlight from a top-level (menu-bar) menu item.  
  
```  
BOOL HiliteMenuItem (CMenu * pMenu、  
    UINT nIDHiliteItem  
    UINT される必要)。
```  
  
### Parameters  
 `pMenu`  
 Identifies the top-level menu that contains the item to be highlighted.  
  
 `nIDHiliteItem`  
 Specifies the menu item to be highlighted, depending on the value of the `nHilite` parameter.  
  
 `nHilite`  
 Specifies whether the menu item is highlighted or the highlight is removed. It can be a combination of **MF_HILITE** or **MF_UNHILITE** with **MF_BYCOMMAND** or **MF_BYPOSITION**. The values can be combined using the bitwise OR operator. These values have the following meanings:  
  
- **MF_BYCOMMAND** Interprets `nIDHiliteItem` as the menu-item ID (the default interpretation).  
  
- **MF_BYPOSITION** Interprets `nIDHiliteItem` as the zero-based offset of the menu item.  
  
- **MF_HILITE** Highlights the item. If this value is not given, the highlight is removed from the item.  
  
- **MF_UNHILITE** Removes the highlight from the item.  
  
### Return Value  
 Specifies whether the menu item was highlighted. Nonzero if the item was highlighted; otherwise 0.  
  
### Remarks  
 The **MF_HILITE** and **MF_UNHILITE** flags can be used only with this member function; they cannot be used with the [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu) member function.  
  
##  <a name="htmlhelp"></a>  CWnd::HtmlHelp  
 Call this member function to invoke the HTMLHelp application.  
  
```  
仮想 void html ヘルプ (DWORD_PTR 指定、  
    UINT nCmd = 0x000F) です。
```  
  
### Parameters  
 `dwData`  
 Specifies additional data. The value used depends on the value of the `nCmd` parameter.  
  
 `nCmd`  
 Specifies the type of help requested. For a list of possible values and how they affect the `dwData` parameter, see the `uCommand` parameter described in the HTML Help API Reference in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 See [CWinApp::HtmlHelp](../../mfc/reference/cwinapp-class.md#htmlhelp) for more information.  
  
##  <a name="initdynamiclayout"></a>  CWnd::InitDynamicLayout  
 Called by the framework to initialize dynamic layout for a window.  
  
```  
InitDynamicLayout(); を無効にします。
```  
  
### Remarks  
 Do not call this method directly.  
  
##  <a name="invalidate"></a>  CWnd::Invalidate  
 Invalidates the entire client area of `CWnd`.  
  
```  
Invalidate を無効にする (BOOL あらゆる = TRUE)。
```  
  
### Parameters  
 `bErase`  
 Specifies whether the background within the update region is to be erased.  
  
### Remarks  
 The client area is marked for painting when the next [WM_PAINT](#onpaint) message occurs. The region can also be validated before a `WM_PAINT` message occurs by the [ValidateRect](#validaterect) or [ValidateRgn](#validatergn) member function.  
  
 The `bErase` parameter specifies whether the background within the update area is to be erased when the update region is processed. If `bErase` is **TRUE**, the background is erased when the [BeginPaint](#beginpaint) member function is called; if `bErase` is **FALSE**, the background remains unchanged. If `bErase` is **TRUE** for any part of the update region, the background in the entire region, not just in the given part, is erased.  
  
 Windows sends a [WM_PAINT](#onpaint) message whenever the `CWnd` update region is not empty and there are no other messages in the application queue for that window.  
  
### Example  
  See the example for [CWnd::UpdateWindow](#updatewindow).  
  
##  <a name="invalidaterect"></a>  CWnd::InvalidateRect  
 Invalidates the client area within the given rectangle by adding that rectangle to the `CWnd` update region.  
  
```  
void InvalidateRect (LPCRECT lpRect、  
    BOOL あらゆる = TRUE)。
```  
  
### Parameters  
 `lpRect`  
 Points to a `CRect` object or a [RECT structure](../../mfc/reference/rect-structure1.md) that contains the rectangle (in client coordinates) to be added to the update region. If `lpRect` is **NULL**, the entire client area is added to the region.  
  
 `bErase`  
 Specifies whether the background within the update region is to be erased.  
  
### Remarks  
 The invalidated rectangle, along with all other areas in the update region, is marked for painting when the next [WM_PAINT](#onpaint) message is sent. The invalidated areas accumulate in the update region until the region is processed when the next `WM_PAINT` call occurs, or until the region is validated by the [ValidateRect](#validaterect) or [ValidateRgn](#validatergn) member function.  
  
 The `bErase` parameter specifies whether the background within the update area is to be erased when the update region is processed. If `bErase` is **TRUE**, the background is erased when the [BeginPaint](#beginpaint) member function is called; if `bErase` is **FALSE**, the background remains unchanged. If `bErase` is **TRUE** for any part of the update region, the background in the entire region is erased, not just in the given part.  
  
 Windows sends a [WM_PAINT](#onpaint) message whenever the `CWnd` update region is not empty and there are no other messages in the application queue for that window.  
  
##  <a name="invalidatergn"></a>  CWnd::InvalidateRgn  
 Invalidates the client area within the given region by adding it to the current update region of `CWnd`.  
  
```  
void 戻り (CRgn * pRgn、  
    BOOL あらゆる = TRUE)。
```  
  
### Parameters  
 `pRgn`  
 A pointer to a [CRgn](../../mfc/reference/crgn-class.md) object that identifies the region to be added to the update region. The region is assumed to have client coordinates. If this parameter is **NULL**, the entire client area is added to the update region.  
  
 `bErase`  
 Specifies whether the background within the update region is to be erased.  
  
### Remarks  
 The invalidated region, along with all other areas in the update region, is marked for painting when the [WM_PAINT](#onpaint) message is next sent. The invalidated areas accumulate in the update region until the region is processed when a `WM_PAINT` message is next sent, or until the region is validated by the [ValidateRect](#validaterect) or [ValidateRgn](#validatergn) member function.  
  
 The `bErase` parameter specifies whether the background within the update area is to be erased when the update region is processed. If `bErase` is **TRUE**, the background is erased when the [BeginPaint](#beginpaint) member function is called; if `bErase` is **FALSE**, the background remains unchanged. If `bErase` is **TRUE** for any part of the update region, the background in the entire region, not just in the given part, is erased.  
  
 Windows sends a [WM_PAINT](#onpaint) message whenever the `CWnd` update region is not empty and there are no other messages in the application queue for that window.  
  
 The given region must have been previously created by one of the region functions.  
  
##  <a name="invokehelper"></a>  CWnd::InvokeHelper  
 Call this member function to invoke the ActiveX Control method or property specified by `dwDispID`, in the context specified by `wFlags`.  
  
```  
void AFX_CDECL InvokeHelper (DISPID dwDispID、  
    WORD wFlags  
    VARTYPE 変数  
    void* pvRet、const バイト*pbParamInfo、  
 ...);
```  
  
### Parameters  
 `dwDispID`  
 Identifies the method or property to be invoked.  
  
 `wFlags`  
 Flags describing the context of the call to **IDispatch::Invoke**.  
  
 `vtRet`  
 Specifies the type of the return value. For possible values, see the Remarks section for [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvRet`  
 Address of the variable that will that will receive the property value or return value. It must match the type specified by `vtRet`.  
  
 `pbParamInfo`  
 Pointer to a null-terminated string of bytes specifying the types of the parameters following `pbParamInfo`. For possible values, see the Remarks section for `COleDispatchDriver::InvokeHelper`.  
  
 *...*  
 Variable List of parameters, of types specified in `pbParamInfo`.  
  
### Remarks  
 The `pbParamInfo` parameter specifies the types of the parameters passed to the method or property. The variable list of arguments is represented by *...* in the syntax declaration.  
  
 This function converts the parameters to **VARIANTARG** values, then invokes the **IDispatch::Invoke** method on the ActiveX control. If the call to **IDispatch::Invoke** fails, this function will throw an exception. If the `SCODE` (status code) returned by **IDispatch::Invoke** is `DISP_E_EXCEPTION`, this function throws a [COleException](../../mfc/reference/coleexception-class.md) object, otherwise it throws a [COleDispatchException](../../mfc/reference/coledispatchexception-class.md).  
  
> [!NOTE]
>  This function should be called only on a `CWnd` object that represents an ActiveX control.  
  
 For more information about using this member function with ActiveX Control Containers, see the article [ActiveX Control Containers: Programming ActiveX Controls in an ActiveX Control Container](../../mfc/programming-activex-controls-in-a-activex-control-container.md).  
  
##  <a name="ischild"></a>  CWnd::IsChild  
 Indicates whether the window specified by `pWnd` is a child window or other direct descendant of `CWnd`.  
  
```  
BOOL IsChild(const CWnd* pWnd) const です。  
```  
  
### Parameters  
 `pWnd`  
 Identifies the window to be tested.  
  
### Return Value  
 Specifies the outcome of the function. The value is nonzero if the window identified by `pWnd` is a child window of `CWnd`; otherwise 0.  
  
### Remarks  
 A child window is the direct descendant of `CWnd` if the `CWnd` object is in the chain of parent windows that leads from the original pop-up window to the child window.  
  
##  <a name="isd2dsupportenabled"></a>  CWnd::IsD2DSupportEnabled  
 Determines whether D2D support is enabled.  
  
```  
BOOL IsD2DSupportEnabled() です。
```  
  
### Return Value  
 TRUE if the feature is enabled; otherwise FALSE.  
  
##  <a name="isdialogmessage"></a>  CWnd::IsDialogMessage  
 Call this member function to determine whether the given message is intended for a modeless dialog box; if it is, this function processes the message.  
  
```  
BOOL IsDialogMessage(LPMSG lpMsg) です。
```  
  
### Parameters  
 `lpMsg`  
 Points to an [MSG](../../mfc/reference/msg-structure1.md) structure that contains the message to be checked.  
  
### Return Value  
 Specifies whether the member function has processed the given message. It is nonzero if the message has been processed; otherwise 0. If the return is 0, call the [CWnd::PreTranslateMessage](#pretranslatemessage) member function of the base class to process the message. In an override of the `CWnd::PreTranslateMessage` member function the code looks like this :  
  
 [!code-cpp[NVC_MFCWindowing#100](../../mfc/reference/codesnippet/cpp/cwnd-class_40.cpp)]  
  
### Remarks  
 When the `IsDialogMessage` function processes a message, it checks for keyboard messages and converts them to selection commands for the corresponding dialog box. For example, the TAB key selects the next control or group of controls, and the DOWN ARROW key selects the next control in a group.  
  
 You must not pass a message processed by `IsDialogMessage` to the [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) or [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows functions, because it has already been processed.  
  
##  <a name="isdlgbuttonchecked"></a>  CWnd::IsDlgButtonChecked  
 Determines whether a button control has a check mark next to it.  
  
```  
UINT IsDlgButtonChecked(int nIDButton) const です。  
```  
  
### Parameters  
 `nIDButton`  
 Specifies the integer identifier of the button control.  
  
### Return Value  
 Nonzero if the given control is checked, and 0 if it is not checked. Only radio buttons and check boxes can be checked. For three-state buttons, the return value can be 2 if the button is indeterminate. This member function returns 0 for a pushbutton.  
  
### Remarks  
 If the button is a three-state control, the member function determines whether it is dimmed, checked, or neither.  
  
##  <a name="isdynamiclayoutenabled"></a>  CWnd::IsDynamicLayoutEnabled  
 Determines whether dynamic layout is enabled on this window. If dynamic layout is enabled, the position and size of child windows can change when the user resizes the parent window.  
  
```  
BOOL IsDynamicLayoutEnabled() const です。  
```  
  
### Return Value  
 TRUE if dynamic layout is enabled; otherwise FALSE.  
  
### Remarks  
  
##  <a name="isiconic"></a>  CWnd::IsIconic  
 Specifies whether `CWnd` is minimized (iconic).  
  
```  
BOOL IsIconic() const です。  
```  
  
### Return Value  
 Nonzero if `CWnd` is minimized; otherwise 0.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#101](../../mfc/reference/codesnippet/cpp/cwnd-class_41.cpp)]  
  
##  <a name="istouchwindow"></a>  CWnd::IsTouchWindow  
 Specifies whether `CWnd` has touch support.  
  
```  
BOOL IsTouchWindow() const です。  
```  
  
### Return Value  
 `TRUE` if `CWnd` has touch support; otherwise `FALSE`.  
  
### Remarks  
  
##  <a name="iswindowenabled"></a>  CWnd::IsWindowEnabled  
 Specifies whether `CWnd` is enabled for mouse and keyboard input.  
  
```  
BOOL IsWindowEnabled() const です。  
```  
  
### Return Value  
 Nonzero if `CWnd` is enabled; otherwise 0.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#102](../../mfc/reference/codesnippet/cpp/cwnd-class_42.cpp)]  
  
##  <a name="iswindowvisible"></a>  CWnd::IsWindowVisible  
 Determines the visibility state of the given window.  
  
```  
BOOL IsWindowVisible() const です。  
```  
  
### Return Value  
 Nonzero if `CWnd` is visible (has the [WS_VISIBLE](../../mfc/reference/window-styles.md) style bit set, and parent window is visible). Because the return value reflects the state of the **WS_VISIBLE** style bit, the return value may be nonzero even though `CWnd` is totally obscured by other windows.  
  
### Remarks  
 A window possesses a visibility state indicated by the **WS_VISIBLE** style bit. When this style bit is set with a call to the [ShowWindow](#showwindow) member function, the window is displayed and subsequent drawing to the window is displayed as long as the window has the style bit set.  
  
 Any drawing to a window that has the **WS_VISIBLE** style will not be displayed if the window is covered by other windows or is clipped by its parent window.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#103](../../mfc/reference/codesnippet/cpp/cwnd-class_43.cpp)]  
  
##  <a name="iszoomed"></a>  CWnd::IsZoomed  
 Determines whether `CWnd` has been maximized.  
  
```  
BOOL IsZoomed() const です。  
```  
  
### Return Value  
 Nonzero if `CWnd` is maximized; otherwise 0.  
  
##  <a name="killtimer"></a>  CWnd::KillTimer  
 Kills the timer event identified by `nIDEvent` from the earlier call to `SetTimer`.  
  
```  
BOOL KillTimer(UINT_PTR nIDEvent) です。
```  
  
### Parameters  
 `nIDEvent`  
 The value of the timer event passed to [SetTimer](#settimer).  
  
### Return Value  
 Specifies the outcome of the function. The value is nonzero if the event was killed. It is 0 if the `KillTimer` member function could not find the specified timer event.  
  
### Remarks  
 Pending [WM_TIMER](#ontimer) messages associated with the timer are not removed from the message queue.  
  
### Example  
  See the example for [CWnd::SetTimer](#settimer).  
  
##  <a name="loaddynamiclayoutresource"></a>  CWnd::LoadDynamicLayoutResource  
 Called by the framework to load dynamic layout information from the resource file.  
  
```  
BOOL LoadDynamicLayoutResource(LPCTSTR lpszResourceName) です。
```  
  
### Parameters  
 `lpszResourceName`  
 The name of the resource that contains the desired dynamic layout information for this window.  
  
### Return Value  
 Nonzero if the function is successful. It is 0 if a failure occurs.  
  
### Remarks  
 Do not call this method directly.  
  
##  <a name="lockwindowupdate"></a>  CWnd::LockWindowUpdate  
 Disables drawing in the given window.  
  
```  
BOOL LockWindowUpdate() です。
```  
  
### Return Value  
 Nonzero if the function is successful. It is 0 if a failure occurs or if the `LockWindowUpdate` function has been used to lock another window.  
  
### Remarks  
 A locked window cannot be moved. Only one window can be locked at a time. To unlock a window locked with `LockWindowUpdate`, call [UnlockWindowUpdate](#unlockwindowupdate).  
  
 If an application with a locked window (or any locked child windows) calls the [GetDC,](http://msdn.microsoft.com/library/windows/desktop/dd144871) [GetDCEx,](http://msdn.microsoft.com/library/windows/desktop/dd144873) or [BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362) Windows function, the called function returns a device context whose visible region is empty. This will occur until the application unlocks the window by calling the `UnlockWindowUpdate` member function.  
  
 While window updates are locked, the system keeps track of the bounding rectangle of any drawing operations to device contexts associated with a locked window. When drawing is reenabled, this bounding rectangle is invalidated in the locked window and its child windows to force an eventual [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message to update the screen. If no drawing has occurred while the window updates were locked, no area is invalidated.  
  
 The `LockWindowUpdate` member function does not make the given window invisible and does not clear the [WS_VISIBLE](../../mfc/reference/window-styles.md) style bit.  
  
##  <a name="m_hwnd"></a>  CWnd::m_hWnd  
 The handle of the Windows window attached to this `CWnd`.  
  
```  
HWND m_hWnd です。  
```  
  
### Remarks  
 The `m_hWnd` data member is a public variable of type `HWND`.  
  
##  <a name="mapwindowpoints"></a>  CWnd::MapWindowPoints  
 Converts (maps) a set of points from the coordinate space of the `CWnd` to the coordinate space of another window.  
  
```  
void MapWindowPoints (CWnd * pwndTo、  
    LPRECT lpRect) const です。  
  
void MapWindowPoints (CWnd * pwndTo、  
    LPPOINT lpPoint  
    UINT nCount) const です。  
```  
  
### Parameters  
 *pwndTo*  
 Identifies the window to which points are converted. If this parameter is **NULL**, the points are converted to screen coordinates.  
  
 `lpRect`  
 Specifies the rectangle whose points are to be converted. The first version of this function is available only for Windows 3.1 and later.  
  
 `lpPoint`  
 A pointer to an array of [POINT structure](../../mfc/reference/point-structure1.md) that contain the set of points to be converted.  
  
 `nCount`  
 Specifies the number of **POINT** structures in the array pointed to by `lpPoint`.  
  
##  <a name="messagebox"></a>  CWnd::MessageBox  
 Creates and displays a window that contains an application-supplied message and caption, plus a combination of the predefined icons and pushbuttons described in the [Message-Box Styles](../../mfc/reference/message-box-styles.md) list.  
  
```  
int (LPCTSTR lpszText、メッセージ ボックス  
    LPCTSTR lpszCaption = NULL の場合、  
    UINT %n タイプ = MB_OK) です。
```  
  
### Parameters  
 `lpszText`  
 Points to a `CString` object or null-terminated string containing the message to be displayed.  
  
 `lpszCaption`  
 Points to a `CString` object or null-terminated string to be used for the message-box caption. If `lpszCaption` is **NULL**, the default caption "Error" is used.  
  
 `nType`  
 Specifies the contents and behavior of the message box.  
  
### Return Value  
 This method utilizes the [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) function as defined in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This method returns the result of calling this function.  
  
### Remarks  
 Use the global function [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) instead of this member function to implement a message box in your application.  
  
 The following shows the various system icons that can be used in a message box:  
  
|||  
|-|-|  
|![Stop &#40;x&#41; icon](../../mfc/reference/media/vc364f1.gif "vc364f1")|**MB_ICONHAND**, **MB_ICONSTOP**, and **MB_ICONERROR**|  
|![Help &#40;&#41; icon](../../mfc/reference/media/vc364f2.gif "vc364f2")|**MB_ICONQUESTION**|  
|![Important &#40;&#33;&#41; icon](../../mfc/reference/media/vc364f3.gif "vc364f3")|**MB_ICONEXCLAMATION** and **MB_ICONWARNING**|  
|![Information &#40;i&#41; icon](../../mfc/reference/media/vc364f4.gif "vc364f4")|**MB_ICONASTERISK** and **MB_ICONINFORMATION**|  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#104](../../mfc/reference/codesnippet/cpp/cwnd-class_44.cpp)]  
  
##  <a name="modifystyle"></a>  CWnd::ModifyStyle  
 Call this member function to modify a window's style.  
  
```  
BOOL は (DWORD dwRemove、  
    DWORD dwAdd  
    UINT nFlags = 0) です。
```  
  
### Parameters  
 `dwRemove`  
 Specifies window styles to be removed during style modification.  
  
 `dwAdd`  
 Specifies window styles to be added during style modification.  
  
 `nFlags`  
 Flags to be passed to [SetWindowPos](#setwindowpos), or zero if `SetWindowPos` should not be called. The default is zero. See the Remarks section for a list of preset flags.  
  
### Return Value  
 Nonzero if style was successfully modified; otherwise, 0.  
  
### Remarks  
 Styles to be added or removed can be combined by using the bitwise OR (&#124;) operator. See the topics [Window Styles](http://msdn.microsoft.com/library/windows/desktop/ms632600) and [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for information about the available window styles.  
  
 If `nFlags` is nonzero, `ModifyStyle` calls the Windows API function [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) and redraws the window by combining `nFlags` with the following four preset flags:  
  
- `SWP_NOSIZE` Retains the current size.  
  
- `SWP_NOMOVE` Retains the current position.  
  
- `SWP_NOZORDER` Retains the current Z order.  
  
- `SWP_NOACTIVATE` Does not activate the window.  
  
 To modify a window's extended styles, see [ModifyStyleEx](#modifystyleex).  
  
> [!NOTE]
>  For some styles in certain controls (the **ES_READONLY** style in the edit control, for example), **ModifyStyle** may not properly change the style because the control may need to perform special internal processing. In these cases, a corresponding message to change the style will be available ( **EM_SETREADONLY** in the example mentioned).  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#105](../../mfc/reference/codesnippet/cpp/cwnd-class_45.cpp)]  
  
##  <a name="modifystyleex"></a>  CWnd::ModifyStyleEx  
 Call this member function to modify a window's extended style.  
  
```  
BOOL は (DWORD dwRemove、  
    DWORD dwAdd  
    UINT nFlags = 0) です。
```  
  
### Parameters  
 `dwRemove`  
 Specifies extended styles to be removed during style modification.  
  
 `dwAdd`  
 Specifies extended styles to be added during style modification.  
  
 `nFlags`  
 Flags to be passed to [SetWindowPos](#setwindowpos), or zero if `SetWindowPos` should not be called. The default is zero. See the Remarks section for a list of preset flags.  
  
### Return Value  
 Nonzero if style was successfully modified; otherwise, 0.  
  
### Remarks  
 Styles to be added or removed can be combined by using the bitwise OR (&#124;) operator. See the topics [Extended Window Styles](../../mfc/reference/extended-window-styles.md) in this book and [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for information about the available extended styles  
  
 If `nFlags` is nonzero, `ModifyStyleEx` calls the Windows API function [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) and redraws the window by combining `nFlags` with the following four preset flags:  
  
- `SWP_NOSIZE` Retains the current size.  
  
- `SWP_NOMOVE` Retains the current position.  
  
- `SWP_NOZORDER` Retains the current Z order.  
  
- `SWP_NOACTIVATE` Does not activate the window.  
  
 To modify windows using regular window styles, see [ModifyStyle](#modifystyle).  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#106](../../mfc/reference/codesnippet/cpp/cwnd-class_46.cpp)]  
  
##  <a name="movewindow"></a>  CWnd::MoveWindow  
 Changes the position and dimensions.  
  
```  
MoveWindow を無効にする (int x  
    int y  
    int nWidth  
    int パラメーター nHeight  
    BOOL bRepaint = TRUE)。

 
MoveWindow を無効にする (LPCRECT lpRect、BOOL bRepaint = TRUE)。
```  
  
### Parameters  
 *x*  
 Specifies the new position of the left side of the `CWnd`.  
  
 *y*  
 Specifies the new position of the top of the `CWnd`.  
  
 `nWidth`  
 Specifies the new width of the `CWnd`.  
  
 `nHeight`  
 Specifies the new height of the `CWnd`.  
  
 `bRepaint`  
 Specifies whether `CWnd` is to be repainted. If **TRUE**, `CWnd` receives a [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message in its [OnPaint](#onpaint) message handler as usual. If this parameter is **FALSE**, no repainting of any kind occurs. This applies to the client area, to the nonclient area (including the title and scroll bars), and to any part of the parent window uncovered as a result of `CWnd`'s move. When this parameter is **FALSE**, the application must explicitly invalidate or redraw any parts of `CWnd` and parent window that must be redrawn.  
  
 `lpRect`  
 The [CRect](../../atl-mfc-shared/reference/crect-class.md) object or [RECT structure](../../mfc/reference/rect-structure1.md) that specifies the new size and position.  
  
### Remarks  
 For a top-level `CWnd` object, the *x* and *y* parameters are relative to the upper-left corner of the screen. For a child `CWnd` object, they are relative to the upper-left corner of the parent window's client area.  
  
 The `MoveWindow` function sends the [WM_GETMINMAXINFO](#ongetminmaxinfo) message. Handling this message gives `CWnd` the opportunity to modify the default values for the largest and smallest possible windows. If the parameters to the `MoveWindow` member function exceed these values, the values can be replaced by the minimum or maximum values in the `WM_GETMINMAXINFO` handler.  
  
### Example  
  See the example for [CWnd::ClientToScreen](#clienttoscreen).  
  
##  <a name="notifywinevent"></a>  CWnd::NotifyWinEvent  
 Signals the system that a predefined event occurred. If any client applications have registered a hook function for the event, the system calls the client's hook function.  
  
```  
NotifyWinEvent (DWORD イベントを無効にします。  
    長い idObjectType  
    長い idObject) です。
```  
  
### Parameters  
 `event`  
 Specifies the event that occurred. This value must be one of the [event constants](http://msdn.microsoft.com/library/windows/desktop/dd318066).  
  
 *idObjectType*  
 Identifies the kind of object that generated the event. This value is one of the predefined [object identifiers](http://msdn.microsoft.com/library/windows/desktop/dd373606) or a custom object ID value.  
  
 `idObject`  
 Identifies whether the event was generated by an object or a child element of the object. If this value is **CHILDID_SELF**, the event was generated by the object itself. If not, this value is the child ID of the element that generated the event.  
  
### Remarks  
 This member function emulates the functionality of the function [NotifyWinEvent](http://msdn.microsoft.com/library/windows/desktop/dd373603), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onactivate"></a>  CWnd::OnActivate  
 The framework calls this member function when a `CWnd` object is being activated or deactivated.  
  
```  
afx_msg OnActivate (UINT %n 状態を無効にします。  
    CWnd * pWndOther、  
    BOOL bMinimized) です。
```  
  
### Parameters  
 `nState`  
 Specifies whether the `CWnd` is being activated or deactivated. It can be one of the following values:  
  
- **WA_INACTIVE** The window is being deactivated.  
  
- **WA_ACTIVE** The window is being activated through some method other than a mouse click (for example, by use of the keyboard interface to select the window).  
  
- **WA_CLICKACTIVE** The window is being activated by a mouse click.  
  
 *pWndOther*  
 Pointer to the `CWnd` being activated or deactivated. The pointer can be **NULL**, and it may be temporary.  
  
 *bMinimized*  
 Specifies the minimized state of the `CWnd` being activated or deactivated. A value of **TRUE** indicates the window is minimized.  
  
 If **TRUE**, the `CWnd` is being activated; otherwise deactivated.  
  
### Remarks  
 If the `CWnd` object is activated with a mouse click, it will also receive an [OnMouseActivate](#onmouseactivate) member function call.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onactivateapp"></a>  CWnd::OnActivateApp  
 The framework calls this member function to all top-level windows of the task being activated and for all top-level windows of the task being deactivated.  
  
```  
afx_msg OnActivateApp (BOOL 描画を無効にします。  
    DWORD dwThreadID) です。
```  
  
### Parameters  
 `bActive`  
 Specifies whether the `CWnd` is being activated or deactivated. **TRUE** means the `CWnd` is being activated. **FALSE** means the `CWnd` is being deactivated.  
  
 *dwThreadID*  
 Specifies the value of the thread ID. If `bActive` is **TRUE**, *dwThreadID* identifies the thread that owns the `CWnd` being deactivated. If `bActive` is **FALSE**, *dwThreadID* identifies the thread that owns the `CWnd` being activated.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onambientproperty"></a>  CWnd::OnAmbientProperty  
 The framework calls this member function to obtain ambient property values from a window that contains OLE controls.  
  
```  
仮想 BOOL OnAmbientProperty (メンバー* pSite DISPID dispid バリアント*pvar) です。
```  
  
### Parameters  
 `pSite`  
 Pointer to the site of the control that requested the ambient property.  
  
 `dispid`  
 The dispatch ID of the requested ambient property.  
  
 `pvar`  
 Pointer to a caller-allocated `VARIANT` structure, through which the ambient property's value will be returned.  
  
### Return Value  
 **TRUE** if the ambient property is supported; **FALSE** if not.  
  
### Remarks  
 Override this function to alter the default ambient property values returned by an OLE control container to its controls. Any ambient property requests not handled by an overriding function should be forwarded to the base class implementation.  
  
##  <a name="onappcommand"></a>  CWnd::OnAppCommand  
 The framework calls this member function when the user generates an application command event. Such an event occurs when the user clicks an application command button or types an application command key.  
  
```  
afx_msg OnAppCommand (CWnd * 我が物を無効にします。  
    UINT nCmd  
    UINT nDevice  
    UINT nKey) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pWnd`|Pointer to a `CWnd` object that represents the window where the user clicked the comman button or pressed the command key. This window can be a child window of the window receiving the message.|  
|[in] `nCmd`|Indicates the application command. For a list of possible values, see the commands under the *cmd* section of the `lParam` parameter of [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275).|  
|[in] `nDevice`|The input device that generated the input event. For a list of possible values, see the devices under the *uDevice* section of the `lParam` parameter of [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275).|  
|[in] `nKey`|Indicates any virtual keys that are down, such as the CTRL key or the left mouse button. For a list of possible values, see the keys under the *dwKeys* section of the `lParam` parameter of [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275). For more information, see the "Message Parameters" subheading in [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).|  
  
### Remarks  
 This method receives the [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onaskcbformatname"></a>  CWnd::OnAskCbFormatName  
 The framework calls this member function when the Clipboard contains a data handle for the `CF_OWNERDISPLAY` format (that is, when the Clipboard owner will display the Clipboard contents).  
  
```  
afx_msg void OnAskCbFormatName (UINT nMaxCount は、  
    LPTSTR lpszString) です。
```  
  
### Parameters  
 `nMaxCount`  
 Specifies the maximum number of bytes to copy.  
  
 `lpszString`  
 Points to the buffer where the copy of the format name is to be stored.  
  
### Remarks  
 The Clipboard owner should provide a name for its format.  
  
 Override this member function and copy the name of the `CF_OWNERDISPLAY` format into the specified buffer, not exceeding the maximum number of bytes specified.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncancelmode"></a>  CWnd::OnCancelMode  
 The framework calls this member function to inform `CWnd` to cancel any internal mode.  
  
```  
afx_msg OnCancelMode(); を無効にします。
```  
  
### Remarks  
 If the `CWnd` object has the focus, its `OnCancelMode` member function is called when a dialog box or message box is displayed. This gives the `CWnd` the opportunity to cancel modes such as mouse capture.  
  
 The default implementation responds by calling the [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261) Windows function. Override this member function in your derived class to handle other modes.  
  
##  <a name="oncapturechanged"></a>  CWnd::OnCaptureChanged  
 The framework calls this member function to notify the window that is losing the mouse capture.  
  
```  
afx_msg OnCaptureChanged (CWnd * 我が物); を無効にします。
```  
  
### Parameters  
 `pWnd`  
 A pointer to the window to gain mouse capture  
  
### Remarks  
 A window receives this message even if it calls [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261) itself. An application should not attempt to set the mouse capture in response to this message. When it receives this message, a window should redraw itself, if necessary, to reflect the new mouse-capture state.  
  
 See the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for information on the `ReleaseCapture` Windows function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchangecbchain"></a>  CWnd::OnChangeCbChain  
 The framework calls this member function for each window in the Clipboard-viewer chain to notify it that a window is being removed from the chain.  
  
```  
afx_msg OnChangeCbChain (HWND hWndRemove を無効にします。  
    HWND hWndAfter) です。
```  
  
### Parameters  
 `hWndRemove`  
 Specifies the window handle that is being removed from the Clipboard-viewer chain.  
  
 `hWndAfter`  
 Specifies the window handle that follows the window being removed from the Clipboard-viewer chain.  
  
### Remarks  
 Each `CWnd` object that receives an `OnChangeCbChain` call should use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function to send the [WM_CHANGECBCHAIN](http://msdn.microsoft.com/library/windows/desktop/ms649019) message to the next window in the Clipboard-viewer chain (the handle returned by `SetClipboardViewer`). If `hWndRemove` is the next window in the chain, the window specified by `hWndAfter` becomes the next window, and Clipboard messages are passed on to it.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchangeuistate"></a>  CWnd::OnChangeUIState  
 Called when the user interface (UI) state should be changed.  
  
```  
afx_msg OnChangeUIState (UINT %5%6%7%8 を無効にします。  
    UINT nUIElement) です。
```  
  
### Parameters  
 `nAction`  
 Specifies the action to be taken. Can be one of the following values:  
  
- **UIS_CLEAR** The UI state element (specified by `nUIElement`) should be hidden.  
  
- **UIS_INITIALIZE** The UI state element (specified by `nUIElement`) should be changed based on the last input event. For more information, see the **Remarks** section of [WM_CHANGEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646342).  
  
- **UIS_SET** The UI state element (specified by `nUIElement`) should be visible.  
  
 `nUIElement`  
 Specifies which UI state elements are affected or the style of the control. Can be one of the following values:  
  
- **UISF_HIDEACCEL** Keyboard accelerators.  
  
- **UISF_HIDEFOCUS** Focus indicators.  
  
- **UISF_ACTIVE Windows XP:** A control should be drawn in the style used for active controls.  
  
### Remarks  
 This member function emulates the functionality of the [WM_CHANGEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646342) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onchar"></a>  CWnd::OnChar  
 The framework calls this member function when a keystroke translates to a nonsystem character.  
  
```  
afx_msg OnChar (UINT nChar を無効にします。  
    UINT nRepCnt  
    UINT nFlags) です。
```  
  
### Parameters  
 `nChar`  
 Contains the character code value of the key.  
  
 `nRepCnt`  
 Contains the repeat count, the number of times the keystroke is repeated when user holds down the key.  
  
 `nFlags`  
 Contains the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0-15|Specifies the repeat count. The value is the number of times the keystroke is repeated as a result of the user holding down the key.|  
|16-23|Specifies the scan code. The value depends on the original equipment manufacturer (OEM)|  
|24|Specifies whether the key is an extended key, such as the right-hand ALT and CTRL keys that appear on an enhanced 101- or 102-key keyboard. The value is 1 if it is an extended key; otherwise, it is 0.|  
|25-28|Used internally by Windows.|  
|29|Specifies the context code. The value is 1 if the ALT key is held down while the key is pressed; otherwise, the value is 0.|  
|30|Specifies the previous key state. The value is 1 if the key is down before the message is sent, or it is 0 if the key is up.|  
|31|Specifies the transition state. The value is 1 if the key is being released, or it is 0 if the key is being pressed.|  
  
### Remarks  
 This function is called before the [OnKeyUp](#onkeyup) member function and after the [OnKeyDown](#onkeydown) member function are called. `OnChar` contains the value of the keyboard key being pressed or released.  
  
 Because there is not necessarily a one-to-one correspondence between keys pressed and `OnChar` calls generated, the information in `nFlags` is generally not useful to applications. The information in `nFlags` applies only to the most recent call to the `OnKeyUp` member function or the `OnKeyDown` member function that precedes the call to `OnChar`.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchartoitem"></a>  CWnd::OnCharToItem  
 Called when a list box with the [LBS_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) style sends its owner a [WM_CHARTOITEM](http://msdn.microsoft.com/library/windows/desktop/bb761358) message in response to a [WM_CHAR](#onchar) message.  
  
```  
afx_msg int OnCharToItem (UINT nChar、  
    CListBox * pListBox、  
    UINT nIndex) です。
```  
  
### Parameters  
 `nChar`  
 Specifies the value of the key pressed by the user.  
  
 `pListBox`  
 Specifies a pointer to the list box. It may be temporary.  
  
 `nIndex`  
 Specifies the current caret position.  
  
### Return Value  
 The framework calls this member function to specify the action that the application performed in response to the call. A return value of –2 indicates that the application handled all aspects of selecting the item and wants no further action by the list box. A return value of –1 indicates that the list box should perform the default action in response to the keystroke. A return value of 0 or greater specifies the zero-based index of an item in the list box and indicates that the list box should perform the default action for the keystroke on the given item.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchildactivate"></a>  CWnd::OnChildActivate  
 If the `CWnd` object is a multiple document interface (MDI) child window, `OnChildActivate` is called by the framework when the user clicks the window's title bar or when the window is activated, moved, or sized.  
  
```  
afx_msg OnChildActivate(); を無効にします。
```  
  
##  <a name="onchildnotify"></a>  CWnd::OnChildNotify  
 This member function is called by this window's parent window when it receives a notification message that applies to this window.  
  
```  
仮想 BOOL OnChildNotify (UINT メッセージ、  
    WPARAM wParam  
    LPARAM lParam  
    LRESULT* pResult) です。
```  
  
### Parameters  
 `message`  
 A Windows message number sent to a parent window.  
  
 `wParam`  
 The **wparam** associated with the message.  
  
 `lParam`  
 The **lparam** associated with the message.  
  
 `pLResult`  
 A pointer to a value to be returned from the parent's window procedure. This pointer will be **NULL** if no return value is expected.  
  
### Return Value  
 Nonzero if this window is responsible for handling the message sent to its parent; otherwise 0.  
  
### Remarks  
 Never call this member function directly.  
  
 The default implementation of this member function returns 0, which means that the parent should handle the message.  
  
 Override this member function to extend the manner in which a control responds to notification messages.  
  
##  <a name="onclipboardupdate"></a>  CWnd::OnClipboardUpdate  
 The framework calls this member function when the contents of the clipboard have changed.  
  
```  
afx_msg OnClipboardUpdate(); を無効にします。
```  
  
##  <a name="onclose"></a>  CWnd::OnClose  
 The framework calls this member function as a signal that the `CWnd` or an application is to terminate.  
  
```  
afx_msg OnClose(); を無効にします。
```  
  
### Remarks  
 The default implementation calls `DestroyWindow`.  
  
##  <a name="oncolorizationcolorchanged"></a>  CWnd::OnColorizationColorChanged  
 The framework calls this member when the rendering policy for the nonclient area has changed.  
  
```  
afx_msg OnColorizationColorChanged (DWORD dwColorizationColor を無効にします。   
    BOOL bOpacity) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `dwColorizationColor`|Specifies the new colorization color.<br /><br /> The color format is a hexadecimal number of the form 0xAARRGGBB, where each of the four components ranges from 0x00 through 0xFF. The AA component is the alpha value, RR is the color red, GG is green, and BB is blue.|  
|[in] `bOpacity`|`true` if the new color is blended with opacity; `false` if it is not.|  
  
### Remarks  
 This method receives the [WM_DWMNCRENDERINGCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388198) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncommand"></a>  CWnd::OnCommand  
 The framework calls this member function when the user selects an item from a menu, when a child control sends a notification message, or when an accelerator keystroke is translated.  
  
```  
仮想 BOOL OnCommand (WPARAM の wParam は、  
    LPARAM lParam) です。
```  
  
### Parameters  
 `wParam`  
 The low-order word of `wParam` identifies the command ID of the menu item, control, or accelerator. The high-order word of `wParam` specifies the notification message if the message is from a control. If the message is from an accelerator, the high-order word is 1. If the message is from a menu, the high-order word is 0.  
  
 `lParam`  
 Identifies the control that sends the message if the message is from a control. Otherwise, `lParam` is 0.  
  
### Return Value  
 An application returns nonzero if it processes this message; otherwise 0.  
  
### Remarks  
 `OnCommand` processes the message map for control notification and `ON_COMMAND` entries, and calls the appropriate member function.  
  
 Override this member function in your derived class to handle the [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) message. An override will not process the message map unless the base class `OnCommand` is called.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncompacting"></a>  CWnd::OnCompacting  
 The framework calls this member function for all top-level windows when Windows detects that more than 12.5 percent of system time over a 30- to 60-second interval is being spent compacting memory.  
  
```  
afx_msg OnCompacting (UINT nCpuTime); を無効にします。
```  
  
### Parameters  
 *nCpuTime*  
 Specifies the ratio of CPU time currently spent by Windows compacting memory to CPU time spent performing other operations. For example, 8000h represents 50 percent of CPU time spent compacting memory.  
  
### Remarks  
 This indicates that system memory is low.  
  
 When a `CWnd` object receives this call, it should free as much memory as possible, taking into account the current level of activity of the application and the total number of applications running in Windows. The application can call the Windows function to determine how many applications are running.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncompareitem"></a>  CWnd::OnCompareItem  
 The framework calls this member function to specify the relative position of a new item in a child sorted owner-draw combo or list box.  
  
```  
afx_msg int OnCompareItem (int 送るとき、  
    LPCOMPAREITEMSTRUCT lpCompareItemStruct) です。
```  
  
### Parameters  
 `nIDCtl`  
 The identifier of the control that sent the `WM_COMPAREITEM` message.  
  
 `lpCompareItemStruct`  
 Contains a long pointer to a [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) data structure that contains the identifiers and application-supplied data for two items in the combo or list box.  
  
### Return Value  
 Indicates the relative position of the two items. It may be any of the following values:  
  
|Value|Meaning|  
|-----------|-------------|  
|–1|Item 1 sorts before item 2.|  
|0|Item 1 and item 2 sort the same.|  
|1|Item 1 sorts after item 2.|  
  
### Remarks  
 If a combo or list box is created with the [CBS_SORT](../../mfc/reference/combo-box-styles.md) or [LBS_SORT](../../mfc/reference/list-box-styles.md) style, Windows sends the combo-box or list-box owner a `WM_COMPAREITEM` message whenever the application adds a new item.  
  
 Two items in the combo or list box are reformed in a `COMPAREITEMSTRUCT` structure pointed to by `lpCompareItemStruct`. `OnCompareItem` should return a value that indicates which of the items should appear before the other. Typically, Windows makes this call several times until it determines the exact position for the new item.  
  
 If the **hwndItem** member of the `COMPAREITEMSTRUCT` structure belongs to a [CListBox](../../mfc/reference/clistbox-class.md) or [CComboBox](../../mfc/reference/ccombobox-class.md) object, then the `CompareItem` virtual function of the appropriate class is called. Override `CComboBox::CompareItem` or `CListBox::CompareItem` in your derived `CListBox` or `CComboBox` class to do the item comparison.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncompositionchanged"></a>  CWnd::OnCompositionChanged  
 The framework calls this member function for all top-level windows when the Desktop Window Manager (DWM) composition is enabled or disabled.  
  
```  
afx_msg OnCompositionChanged(); を無効にします。
```  
  
### Remarks  
 This method receives the [WM_DWMCOMPOSITIONCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388199) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncontextmenu"></a>  CWnd::OnContextMenu  
 Called by the framework when the user has clicked the right mouse button (right clicked) in the window.  
  
```  
afx_msg OnContextMenu (CWnd * 我が物を無効にします。  
    CPoint pos) です。
```  
  
### Parameters  
 `pWnd`  
 Handle to the window in which the user right clicked the mouse. This can be a child window of the window receiving the message. For more information about processing this message, see the Remarks section.  
  
 `pos`  
 Position of the cursor, in screen coordinates, at the time of the mouse click.  
  
### Remarks  
 You can process this message by displaying a context menu using the [TrackPopupMenu](../../mfc/reference/cmenu-class.md#trackpopupmenu).  
  
 If you do not display a context menu you should pass this message onto the [DefWindowProc](#defwindowproc) function. If your window is a child window, `DefWindowProc` sends the message to the parent. Otherwise, `DefWindowProc` displays a default context menu if the specified position is in the window's caption.  
  
##  <a name="oncopydata"></a>  CWnd::OnCopyData  
 This member function is called by the framework to copy data from one application to another.  
  
```  
afx_msg BOOL OnCopyData (CWnd*我が物、COPYDATASTRUCT* pCopyDataStruct) です。
```  
  
### Parameters  
 `pWnd`  
 A pointer to a `CWnd` object that is sending the data.  
  
 `pCopyDataStruct`  
 A pointer to a [COPYDATASTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms649010) structure that contains the data being sent.  
  
### Return Value  
 Returns **TRUE** if the receiving application successfully accepts the data. Otherwise, returns **FALSE**.  
  
### Remarks  
 The data being passed must not contain pointers or other references to objects not accessible to the application receiving the data.  
  
 While the data is being copied, it must not be changed by another thread of the sending process.  
  
 The receiving application should consider the data read-only. The structure pointed to by the parameter `pCopyDataStruct` is valid only during the transfer of data; however, the receiving application should not free the memory associated with the structure.  
  
 If the receiving application needs access to the data after this function returns, it must copy the data received to a local buffer.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncreate"></a>  CWnd::OnCreate  
 The framework calls this member function when an application requests that the Windows window be created by calling the [Create](#create) or [CreateEx](#createex) member function.  
  
```  
afx_msg int OnCreate (LPCREATESTRUCT lpCreateStruct) です。
```  
  
### Parameters  
 `lpCreateStruct`  
 Points to a [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) structure that contains information about the `CWnd` object being created.  
  
### Return Value  
 `OnCreate` must return 0 to continue the creation of the `CWnd` object. If the application returns –1, the window will be destroyed.  
  
### Remarks  
 The `CWnd` object receives this call after the window is created but before it becomes visible. `OnCreate` is called before the **Create** or `CreateEx` member function returns.  
  
 Override this member function to perform any needed initialization of a derived class.  
  
 The `CREATESTRUCT` structure contains copies of the parameters used to create the window.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onctlcolor"></a>  CWnd::OnCtlColor  
 The framework calls this member function when a child control is about to be drawn.  
  
```  
afx_msg HBRUSH OnCtlColor (CDC* pDC CWnd*我が物、  
    UINT のため)。
```  
  
### Parameters  
 `pDC`  
 Contains a pointer to the display context for the child window. May be temporary.  
  
 `pWnd`  
 Contains a pointer to the control asking for the color. May be temporary.  
  
 `nCtlColor`  
 Contains one of the following values, specifying the type of control:  
  
- **CTLCOLOR_BTN** Button control  
  
- **CTLCOLOR_DLG** Dialog box  
  
- **CTLCOLOR_EDIT** Edit control  
  
- **CTLCOLOR_LISTBOX** List-box control  
  
- **CTLCOLOR_MSGBOX** Message box  
  
- **CTLCOLOR_SCROLLBAR** Scroll-bar control  
  
- **CTLCOLOR_STATIC** Static control  
  
### Return Value  
 `OnCtlColor` must return a handle to the brush that is to be used for painting the control background.  
  
### Remarks  
 Most controls send this message to their parent (usually a dialog box) to prepare the `pDC` for drawing the control using the correct colors.  
  
 To change the text color, call the `SetTextColor` member function with the desired red, green, and blue (RGB) values.  
  
 To change the background color of a single-line edit control, set the brush handle in both the **CTLCOLOR_EDIT** and **CTLCOLOR_MSGBOX** message codes, and call the [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) function in response to the **CTLCOLOR_EDIT** code.  
  
 `OnCtlColor` will not be called for the list box of a drop-down combo box because the drop-down list box is actually a child of the combo box and not a child of the window. To change the color of the drop-down list box, create a `CComboBox` with an override of `OnCtlColor` that checks for **CTLCOLOR_LISTBOX** in the `nCtlColor` parameter. In this handler, the `SetBkColor` member function must be used to set the background color for the text.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function. To add the following method to your dialog class, use the Visual Studio properties pane to add a message handler for WM_CTLCOLOR. Alternatively, you can manually add an ON_WM_CTLCOLOR() entry to the message map.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#107](../../mfc/reference/codesnippet/cpp/cwnd-class_47.cpp)]  
  
##  <a name="ondeadchar"></a>  CWnd::OnDeadChar  
 The framework calls this member function when the [OnKeyUp](#onkeyup) member function and the [OnKeyDown](#onkeydown) member functions are called.  
  
```  
afx_msg OnDeadChar (UINT nChar を無効にします。  
    UINT nRepCnt  
    UINT nFlags) です。
```  
  
### Parameters  
 `nChar`  
 Specifies the dead-key character value.  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Description|  
|-----------|-----------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
### Remarks  
 This member function can be used to specify the character value of a dead key. A dead key is a key, such as the umlaut (double-dot) character, that is combined with other characters to form a composite character. For example, the umlaut-O character consists of the dead key, umlaut, and the O key.  
  
 An application typically uses `OnDeadChar` to give the user feedback about each key pressed. For example, an application can display the accent in the current character position without moving the caret.  
  
 Since there is not necessarily a one-to-one correspondence between keys pressed and `OnDeadChar` calls, the information in `nFlags` is generally not useful to applications. The information in `nFlags` applies only to the most recent call to the [OnKeyUp](#onkeyup) member function or the [OnKeyDown](#onkeydown) member function that precedes the `OnDeadChar` call.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondeleteitem"></a>  CWnd::OnDeleteItem  
 The framework calls this member function to inform the owner of an owner-draw list box or combo box that the list box or combo box is destroyed or that items have been removed by [CComboBox::DeleteString](../../mfc/reference/ccombobox-class.md#deletestring), [CListBox::DeleteString](../../mfc/reference/clistbox-class.md#deletestring), [CComboBox::ResetContent](../../mfc/reference/ccombobox-class.md#resetcontent), or [CListBox::ResetContent](../../mfc/reference/clistbox-class.md#resetcontent).  
  
```  
afx_msg void OnDeleteItem (int 送るとき、  
    LPDELETEITEMSTRUCT lpDeleteItemStruct) です。
```  
  
### Parameters  
 `nIDCtl`  
 The identifier of the control that sent the `WM_DELETEITEM` message.  
  
 `lpDeleteItemStruct`  
 Specifies a long pointer to a [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) data structure that contains information about the deleted list box item.  
  
### Remarks  
 If the **hwndItem** member of the `DELETEITEMSTRUCT` structure belongs to a combo box or list box, then the `DeleteItem` virtual function of the appropriate class is called. Override the `DeleteItem` member function of the appropriate control's class to delete item-specific data.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondestroy"></a>  CWnd::OnDestroy  
 The framework calls this member function to inform the `CWnd` object that it is being destroyed.  
  
```  
afx_msg OnDestroy(); を無効にします。
```  
  
### Remarks  
 `OnDestroy` is called after the `CWnd` object is removed from the screen.  
  
 `OnDestroy` is called first for the `CWnd` being destroyed, then for the child windows of `CWnd` as they are destroyed. It can be assumed that all child windows still exist while `OnDestroy` runs.  
  
 If the `CWnd` object being destroyed is part of the Clipboard-viewer chain (set by calling the [SetClipboardViewer](#setclipboardviewer) member function), the `CWnd` must remove itself from the Clipboard-viewer chain by calling the [ChangeClipboardChain](#changeclipboardchain) member function before returning from the `OnDestroy` function.  
  
##  <a name="ondestroyclipboard"></a>  CWnd::OnDestroyClipboard  
 The framework calls this member function for the Clipboard owner when the Clipboard is emptied through a call to the [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) Windows function.  
  
```  
afx_msg OnDestroyClipboard(); を無効にします。
```  
  
##  <a name="ondevicechange"></a>  CWnd::OnDeviceChange  
 The framework calls this member function to notify an application or device driver of a change to the hardware configuration of a device or the computer.  
  
```  
afx_msg BOOL OnDeviceChange (UINT nEventType、  
    DWORD_PTR 指定)。
```  
  
### Parameters  
 *nEventType*  
 An event type. See the Remarks section for a description of the available values  
  
 `dwData`  
 The address of a structure that contains event-specific data. Its meaning depends on the given event.  
  
### Remarks  
 For devices that offer software-controllable features, such as ejection and locking, the operating system typically sends a **DBT_DEVICEREMOVEPENDING** message to let applications and device drivers end their use of the device gracefully.  
  
 If the operating system forcefully removes of a device, it may not send a **DBT_DEVICEQUERYREMOVE** message before doing so.  
  
 The *nEvent* parameter can be one of these values:  
  
- [DBT_DEVICEARRIVAL](http://msdn.microsoft.com/library/windows/desktop/aa363205) A device has been inserted and is now available.  
  
- [DBT_DEVICEQUERYREMOVE](http://msdn.microsoft.com/library/windows/desktop/aa363206) Permission to remove a device is requested. Any application can deny this request and cancel the removal.  
  
- [DBT_DEVICEQUERYREMOVEFAILED](http://msdn.microsoft.com/library/windows/desktop/aa363207) Request to remove a device has been canceled.  
  
- [DBT_DEVICEREMOVEPENDING](http://msdn.microsoft.com/library/windows/desktop/aa363209) Device is about to be removed. Cannot be denied.  
  
- [DBT_DEVICEREMOVECOMPLETE](http://msdn.microsoft.com/library/windows/desktop/aa363208) Device has been removed.  
  
- [DBT_DEVICETYPESPECIFIC](http://msdn.microsoft.com/library/windows/desktop/aa363210) Device-specific event.  
  
- [DBT_CONFIGCHANGED](http://msdn.microsoft.com/library/windows/desktop/aa363203) Current configuration has changed.  
  
- **DBT_DEVNODES_CHANGED** Device node has changed.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondevmodechange"></a>  CWnd::OnDevModeChange  
 The framework calls this member function for all top-level `CWnd` objects when the user changes device-mode settings.  
  
```  
afx_msg OnDevModeChange (LPTSTR lpDeviceName); を無効にします。
```  
  
### Parameters  
 *lpDeviceName*  
 Points to the device name specified in the Windows initialization file, WIN.INI.  
  
### Remarks  
 Applications that handle the `WM_DEVMODECHANGE` message may reinitialize their device-mode settings. Applications that use the Windows **ExtDeviceMode** function to save and restore device settings typically do not process this function.  
  
 This function is not called when the user changes the default printer from Control Panel. In this case, the `OnWinIniChange` function is called.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondrawclipboard"></a>  CWnd::OnDrawClipboard  
 The framework calls this member function for each window in the Clipboard-viewer chain when the contents of the Clipboard change.  
  
```  
afx_msg OnDrawClipboard(); を無効にします。
```  
  
### Remarks  
 Only applications that have joined the Clipboard-viewer chain by calling the [SetClipboardViewer](#setclipboardviewer) member function need to respond to this call.  
  
 Each window that receives an `OnDrawClipboard` call should call the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function to pass a [WM_DRAWCLIPBOARD](http://msdn.microsoft.com/library/windows/desktop/ms649025) message on to the next window in the Clipboard-viewer chain. The handle of the next window is returned by the [SetClipboardViewer](#setclipboardviewer) member function; it may be modified in response to an [OnChangeCbChain](#onchangecbchain) member function call.  
  
##  <a name="ondrawiconicthumbnailorlivepreview"></a>  CWnd::OnDrawIconicThumbnailOrLivePreview  
 Called by the framework when it needs to obtain a bitmap to be displayed on Windows 7 tab thumbnail, or on the client for application peek.  
  
```  
仮想の void OnDrawIconicThumbnailOrLivePreview (CDC >/documents/report1.rdl」の dc では、  
    CRect rect  
    CSize szRequiredThumbnailSize  
    BOOL bIsThumbnail  
    BOOL >/reportbuilder/reportbuilder_3_0_0_0.application bAlphaChannelSet) です。
```  
  
### Parameters  
 `dc`  
 Specifies the device context.  
  
 `rect`  
 Specifies the bounding rectangle of the area to render.  
  
 `szRequiredThumbnailSize`  
 Specifies the size of the target thumbnail. Should be ignored if `bIsThumbnail` is `FALSE`.  
  
 `bIsThumbnail`  
 Specifies whether this method is called for iconic thumbnail or live preview (peek).  
  
 `bAlphaChannelSet`  
 [out] Set it to `TRUE` if your implementation initializes the alpha channel of a bitmap selected in `dc`.  
  
### Remarks  
 Override this method in a derived class and draw on the specified device context in order to customize thumbnail and peek. If `bThumbnail` is `TRUE`, `szRequiredThumbnailSize` can be ignored. In this case you should be aware that you draw full sized bitmap (that is, a bitmap that covers the whole client area). The device context ( `dc`) comes with selected 32 bits bitmap. The default implementation sends WM_PRINT to this window with PRF_CLIENT, PRF_CHILDREN, and PRF_NONCLIENT flags.  
  
##  <a name="ondrawitem"></a>  CWnd::OnDrawItem  
 The framework calls this member function for the owner of an owner-draw button control, combo-box control, list-box control, or menu when a visual aspect of the control or menu has changed.  
  
```  
afx_msg void OnDrawItem (int 送るとき、  
    LPDRAWITEMSTRUCT lpDrawItemStruct) です。
```  
  
### Parameters  
 `nIDCtl`  
 Contains the identifier of the control that sent the `WM_DRAWITEM` message. If a menu sent the message, `nIDCtl` contains 0.  
  
 `lpDrawItemStruct`  
 Specifies a long pointer to a `DRAWITEMSTRUCT` data structure that contains information about the item to be drawn and the type of drawing required.  
  
### Remarks  
 The **itemAction** member of the [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) structure defines the drawing operation that is to be performed. The data in this member allows the owner of the control to determine what drawing action is required.  
  
 Before returning from processing this message, an application should ensure that the device context identified by the `hDC` member of the `DRAWITEMSTRUCT` structure is restored to the default state.  
  
 If the **hwndItem** member belongs to a [CButton](../../mfc/reference/cbutton-class.md), [CMenu](../../mfc/reference/cmenu-class.md), [CListBox](../../mfc/reference/clistbox-class.md), or [CComboBox](../../mfc/reference/ccombobox-class.md) object, then the `DrawItem` virtual function of the appropriate class is called. Override the `DrawItem` member function of the appropriate control's class to draw the item.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondropfiles"></a>  CWnd::OnDropFiles  
 The framework calls this member function when the user releases the left mouse button over a window that has registered itself as the recipient of dropped files.  
  
```  
afx_msg OnDropFiles (HDROP hDropInfo); を無効にします。
```  
  
### Parameters  
 *hDropInfo*  
 A pointer to an internal data structure that describes the dropped files. This handle is used by the **DragFinish**, **DragQueryFile**, and **DragQueryPoint** Windows functions to retrieve information about the dropped files.  
  
### Remarks  
 Typically, a derived class will be designed to support dropped files and it will register itself during window construction.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onenable"></a>  CWnd::OnEnable  
 The framework calls this member function when an application changes the enabled state of the `CWnd` object.  
  
```  
afx_msg OnEnable (BOOL bEnable); を無効にします。
```  
  
### Parameters  
 `bEnable`  
 Specifies whether the `CWnd` object has been enabled or disabled. This parameter is **TRUE** if the `CWnd` has been enabled; it is **FALSE** if the `CWnd` has been disabled.  
  
### Remarks  
 `OnEnable` is called before the [EnableWindow](#enablewindow) member function returns, but after the window enabled state ( [WS_DISABLED](../../mfc/reference/window-styles.md) style bit) has changed.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onendsession"></a>  CWnd::OnEndSession  
 The framework calls this member function after the `CWnd` object has returned a nonzero value from a [OnQueryEndSession](#onqueryendsession) member function call.  
  
```  
afx_msg OnEndSession(BOOL bEnding); を無効にします。
```  
  
### Parameters  
 `bEnding`  
 Specifies whether or not the session is being ended. It is **TRUE** if the session is being ended; otherwise **FALSE**.  
  
### Remarks  
 The `OnEndSession` call informs the `CWnd` object whether the session is actually ending.  
  
 If `bEnding` is **TRUE**, Windows can terminate any time after all applications have returned from processing this call. Consequently, have an application perform all tasks required for termination within `OnEndSession`.  
  
 You do not need to call the [DestroyWindow](#destroywindow) member function or [PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945) Windows function when the session is ending.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onenteridle"></a>  CWnd::OnEnterIdle  
 The framework calls this member function to inform an application's main window procedure that a modal dialog box or a menu is entering an idle state.  
  
```  
afx_msg OnEnterIdle (UINT nWhy を無効にします。  
    CWnd* pWho) です。
```  
  
### Parameters  
 `nWhy`  
 Specifies whether the message is the result of a dialog box or a menu being displayed. This parameter can be one of the following values:  
  
- **MSGF_DIALOGBOX** The system is idle because a dialog box is being displayed.  
  
- **MSGF_MENU** The system is idle because a menu is being displayed.  
  
 *pWho*  
 Specifies a pointer to the dialog box (if `nWhy` is **MSGF_DIALOGBOX**), or the window that contains the displayed menu (if `nWhy` is **MSGF_MENU**). This pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 A modal dialog box or menu enters an idle state when no messages are waiting in its queue after it has processed one or more previous messages.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onentermenuloop"></a>  CWnd::OnEnterMenuLoop  
 The framework calls this member function when a menu modal loop has been entered.  
  
```  
afx_msg OnEnterMenuLoop (BOOL bIsTrackPopupMenu); を無効にします。
```  
  
### Parameters  
 `bIsTrackPopupMenu`  
 Specifies whether the menu involved is a popup menu. Has a nonzero value if the function is successful; otherwise 0.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onentersizemove"></a>  CWnd::OnEnterSizeMove  
 The framework calls this member function one time after the affected window enters a moving or sizing modal loop.  
  
```  
afx_msg OnEnterSizeMove(); を無効にします。
```  
  
### Remarks  
 This method receives the [WM_ENTERSIZEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms632622) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 A window enters a moving or sizing modal loop when the user clicks the window's title bar or sizing border, or when the window passes the [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) message to the [CWnd::DefWindowProc](#defwindowproc) function and the `wParam` parameter of that message specifies `SC_MOVE` or `SC_SIZE`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onerasebkgnd"></a>  CWnd::OnEraseBkgnd  
 The framework calls this member function when the `CWnd` object background needs erasing (for example, when resized).  
  
```  
afx_msg BOOL OnEraseBkgnd(CDC* pDC) です。
```  
  
### Parameters  
 `pDC`  
 Specifies the device-context object.  
  
### Return Value  
 Nonzero if it erases the background; otherwise 0.  
  
### Remarks  
 It is called to prepare an invalidated region for painting.  
  
 The default implementation erases the background using the window class background brush specified by the **hbrBackground** member of the window class structure.  
  
 If the **hbrBackground** member is **NULL**, your overridden version of `OnEraseBkgnd` should erase the background color. Your version should also align the origin of the intended brush with the `CWnd` coordinates by first calling [UnrealizeObject](http://msdn.microsoft.com/library/windows/desktop/dd145164) for the brush, and then selecting the brush.  
  
 An overridden `OnEraseBkgnd` should return nonzero in response to `WM_ERASEBKGND` if it processes the message and erases the background; this indicates that no further erasing is required. If it returns 0, the window will remain marked as needing to be erased. (Typically, this means that the **fErase** member of the `PAINTSTRUCT` structure will be **TRUE**.)  
  
 Windows assumes the background is computed with the `MM_TEXT` mapping mode. If the device context is using any other mapping mode, the area erased may not be within the visible part of the client area.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onexitmenuloop"></a>  CWnd::OnExitMenuLoop  
 The framework calls this member function when a menu modal loop has been exited.  
  
```  
afx_msg OnExitMenuLoop (BOOL bIsTrackPopupMenu); を無効にします。
```  
  
### Parameters  
 `bIsTrackPopupMenu`  
 Specifies whether the menu involved is a pop-up menu. Has a nonzero value if the function is successful; otherwise 0.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onexitsizemove"></a>  CWnd::OnExitSizeMove  
 The framework calls this member function one time after the affected window exits a moving or sizing modal loop.  
  
```  
afx_msg OnExitSizeMove(); を無効にします。
```  
  
### Remarks  
 This method receives the [WM_EXITSIZEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms632623) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 A window enters a moving or sizing modal loop when the user clicks the window's title bar or sizing border, or when the window passes the [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) message to the [CWnd::DefWindowProc](#defwindowproc) function and the `wParam` parameter of that message specifies `SC_MOVE` or `SC_SIZE`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onfontchange"></a>  CWnd::OnFontChange  
 All top-level windows in the system receive an `OnFontChange` call from the framework after the application changes the pool of font resources.  
  
```  
afx_msg OnFontChange(); を無効にします。
```  
  
### Remarks  
 An application that adds or removes fonts from the system (for example, through the [AddFontResource](http://msdn.microsoft.com/library/windows/desktop/dd183326) or [RemoveFontResource](http://msdn.microsoft.com/library/windows/desktop/dd162922) Windows function) should send the [WM_FONTCHANGE](http://msdn.microsoft.com/library/windows/desktop/dd145211) message to all top-level windows.  
  
 To send this message, use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function with the `hWnd` parameter set to **HWND_BROADCAST**.  
  
##  <a name="ongetdlgcode"></a>  CWnd::OnGetDlgCode  
 Called for a control so the control can process arrow-key and TAB-key input itself.  
  
```  
afx_msg UINT OnGetDlgCode() です。
```  
  
### Return Value  
 One or more of the following values, indicating which type of input the application processes:  
  
- **DLGC_BUTTON** Button (generic).  
  
- **DLGC_DEFPUSHBUTTON** Default pushbutton.  
  
- **DLGC_HASSETSEL EM_SETSEL** messages.  
  
- **DLGC_UNDEFPUSHBUTTON** No default pushbutton processing. (An application can use this flag with **DLGC_BUTTON** to indicate that it processes button input but relies on the system for default pushbutton processing.)  
  
- **DLGC_RADIOBUTTON** Radio button.  
  
- **DLGC_STATIC** Static control.  
  
- **DLGC_WANTALLKEYS** All keyboard input.  
  
- **DLGC_WANTARROWS** Arrow keys.  
  
- **DLGC_WANTCHARS** `WM_CHAR` messages.  
  
- **DLGC_WANTMESSAGE** All keyboard input. The application passes this message on to the control.  
  
- **DLGC_WANTTAB** TAB key.  
  
### Remarks  
 Normally, Windows handles all arrow-key and TAB-key input to a `CWnd` control. By overriding `OnGetDlgCode`, a `CWnd` control can choose a particular type of input to process itself.  
  
 The default `OnGetDlgCode` functions for the predefined control classes return a code appropriate for each class.  
  
##  <a name="ongetminmaxinfo"></a>  CWnd::OnGetMinMaxInfo  
 The framework calls this member function whenever Windows needs to know the maximized position or dimensions, or the minimum or maximum tracking size.  
  
```  
afx_msg OnGetMinMaxInfo (MINMAXINFO * lpMMI); を無効にします。
```  
  
### Parameters  
 *lpMMI*  
 Points to a `MINMAXINFO` structure that contains information about a window's maximized size and position and its minimum and maximum tracking size. For more about this structure, see the [MINMAXINFO](../../mfc/reference/minmaxinfo-structure.md) structure.  
  
### Remarks  
 The maximized size is the size of the window when its borders are fully extended. The maximum tracking size of the window is the largest window size that can be achieved by using the borders to size the window. The minimum tracking size of the window is the smallest window size that can be achieved by using the borders to size the window.  
  
 Windows fills in an array of points specifying default values for the various positions and dimensions. The application may change these values in `OnGetMinMaxInfo`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onhelp"></a>  CWnd::OnHelp  
 Handles F1 Help within the application (using the current context).  
  
```  
afx_msg OnHelp(); を無効にします。
```  
  
### Remarks  
 See [CWinApp::OnHelp](../../mfc/reference/cwinapp-class.md#onhelp) for more information.  
  
##  <a name="onhelpfinder"></a>  CWnd::OnHelpFinder  
 Handles the **ID_HELP_FINDER** and **ID_DEFAULT_HELP** commands.  
  
```  
afx_msg OnHelpFinder(); を無効にします。
```  
  
### Remarks  
 See [CWinApp::OnHelpFinder](../../mfc/reference/cwinapp-class.md#onhelpfinder) for more information.  
  
##  <a name="onhelpindex"></a>  CWnd::OnHelpIndex  
 Handles the **ID_HELP_INDEX** command and provides a default Help topic.  
  
```  
afx_msg OnHelpIndex(); を無効にします。
```  
  
### Remarks  
 See [CWinApp::OnHelpIndex](../../mfc/reference/cwinapp-class.md#onhelpindex) for more information.  
  
##  <a name="onhelpinfo"></a>  CWnd::OnHelpInfo  
 Called by the framework when the user presses the F1 key.  
  
```  
afx_msg BOOL OnHelpInfo(HELPINFO* lpHelpInfo) です。
```  
  
### Parameters  
 *lpHelpInfo*  
 Pointer to a [HELPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773313) structure that contains information about the menu item, control, dialog box, or window for which help is requested.  
  
### Return Value  
 Returns TRUE if a window has the keyboard focus or if a menu is active within a window. If no window has the keyboard focus, returns FALSE.  
  
### Remarks  
 If a menu is active when F1 is pressed, **WM_HELP** is sent to the window associated with the menu; otherwise, **WM_HELP** is sent to the window that has the keyboard focus. If no window has the keyboard focus, **WM_HELP** is sent to the currently active window.  
  
##  <a name="onhelpusing"></a>  CWnd::OnHelpUsing  
 Handles the **ID_HELP_USING** command.  
  
```  
afx_msg OnHelpUsing(); を無効にします。
```  
  
### Remarks  
 See [CWinApp::OnHelpUsing](../../mfc/reference/cwinapp-class.md#onhelpusing) for more information.  
  
##  <a name="onhotkey"></a>  CWnd::OnHotKey  
 The framework calls this member function when the user presses a system-wide hot key.  
  
```  
afx_msg OnHotKey (UINT nHotKeyId を無効にします。   
    UINT nKey1   
    UINT nKey2) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHotKeyId`|Identifier for the hot key that generated the message. If the message was generated by a system-defined hot key, this parameter will be one of the following values:<br /><br /> - `IDHOT_SNAPDESKTOP` - The snap desktop hot key was pressed.<br />- `IDHOT_SNAPWINDOW` - The snap window hot key was pressed.|  
|[in] `nKey1`|A bitwise combination (OR) of flags that indicate the keys that were pressed in combination with the key specified by the `nKey2` parameter. The possible values are:<br /><br /> - `MOD_ALT` - Either ALT key was held down.<br />- `MOD_CONTROL` - Either CTRL key was held down.<br />- `MOD_SHIFT` - Either SHIFT key was held down.<br />- `MOD_WIN` - Either WINDOWS key was held down. These keys are labeled with the Microsoft Windows logo.|  
|[in] `nKey2`|The virtual key code of the hot key.|  
  
### Remarks  
 This method receives the [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is placed at the top of the message queue associated with the thread that registered the hot key. Use the [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) function to register a system-wide hot key.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onhscroll"></a>  CWnd::OnHScroll  
 The framework calls this member function when the user clicks a window's horizontal scroll bar.  
  
```  
afx_msg OnHScroll (UINT nSBCode を無効にします。  
    UINT nPos  
    CScrollBar* pScrollBar) です。
```  
  
### Parameters  
 `nSBCode`  
 Specifies a scroll-bar code that indicates the user's scrolling request. This parameter can be one of the following:  
  
- **SB_LEFT** Scroll to far left.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINELEFT** Scroll left.  
  
- **SB_LINERIGHT** Scroll right.  
  
- **SB_PAGELEFT** Scroll one page left.  
  
- **SB_PAGERIGHT** Scroll one page right.  
  
- **SB_RIGHT** Scroll to far right.  
  
- **SB_THUMBPOSITION** Scroll to absolute position. The current position is specified by the `nPos` parameter.  
  
- **SB_THUMBTRACK** Drag scroll box to specified position. The current position is specified by the `nPos` parameter.  
  
 `nPos`  
 Specifies the scroll-box position if the scroll-bar code is **SB_THUMBPOSITION** or **SB_THUMBTRACK**; otherwise, not used. Depending on the initial scroll range, `nPos` may be negative and should be cast to an `int` if necessary.  
  
 `pScrollBar`  
 If the scroll message came from a scroll-bar control, contains a pointer to the control. If the user clicked a window's scroll bar, this parameter is **NULL**. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The **SB_THUMBTRACK** scroll-bar code typically is used by applications that give some feedback while the scroll box is being dragged.  
  
 If an application scrolls the contents controlled by the scroll bar, it must also reset the position of the scroll box with the [SetScrollPos](#setscrollpos) member function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#108](../../mfc/reference/codesnippet/cpp/cwnd-class_48.cpp)]  
  
##  <a name="onhscrollclipboard"></a>  CWnd::OnHScrollClipboard  
 The Clipboard owner's `OnHScrollClipboard` member function is called by the Clipboard viewer when the Clipboard data has the `CF_OWNERDISPLAY` format and there is an event in the Clipboard viewer's horizontal scroll bar.  
  
```  
afx_msg OnHScrollClipboard (CWnd * pClipAppWnd を無効にします。  
    UINT nSBCode  
    UINT nPos) です。
```  
  
### Parameters  
 `pClipAppWnd`  
 Specifies a pointer to a Clipboard-viewer window. The pointer may be temporary and should not be stored for later use.  
  
 `nSBCode`  
 Specifies one of the following scroll-bar codes in the low-order word:  
  
- **SB_BOTTOM** Scroll to lower right.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINEDOWN** Scroll one line down.  
  
- **SB_LINEUP** Scroll one line up.  
  
- **SB_PAGEDOWN** Scroll one page down.  
  
- **SB_PAGEUP** Scroll one page up.  
  
- **SB_THUMBPOSITION** Scroll to the absolute position. The current position is provided in `nPos`.  
  
- **SB_TOP** Scroll to upper left.  
  
 `nPos`  
 Contains the scroll-box position if the scroll-bar code is **SB_THUMBPOSITION**; otherwise not used.  
  
### Remarks  
 The owner should scroll the Clipboard image, invalidate the appropriate section, and update the scroll-bar values.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oniconerasebkgnd"></a>  CWnd::OnIconEraseBkgnd  
 The framework calls this member function for a minimized (iconic) `CWnd` object when the background of the icon must be filled before painting the icon.  
  
```  
afx_msg OnIconEraseBkgnd (CDC * pDC); を無効にします。
```  
  
### Parameters  
 `pDC`  
 Specifies the device-context object of the icon. May be temporary and should not be stored for later use.  
  
### Remarks  
 `CWnd` receives this call only if a class icon is defined for the window default implementation; otherwise [OnEraseBkgnd](#onerasebkgnd) is called.  
  
 The [DefWindowProc](#defwindowproc) member function fills the icon background with the background brush of the parent window.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninitmenu"></a>  CWnd::OnInitMenu  
 The framework calls this member function when a menu is about to become active.  
  
```  
afx_msg OnInitMenu (CMenu * pMenu); を無効にします。
```  
  
### Parameters  
 `pMenu`  
 Specifies the menu to be initialized. May be temporary and should not be stored for later use.  
  
### Remarks  
 `OnInitMenu` is called when the user clicks an item on the menu bar or presses a menu key. Override this member function to modify the menu before it is displayed.  
  
 `OnInitMenu` is only called once, when a menu is first accessed (for example, when a user clicks an item on the menu bar). This method does not provide information about menu items. As the user moves to items within the menu (for example, by moving the mouse across several menu items) the function is not called again. Once the user exits from the menu (for example, by clicking on the application client area) and later clicks an item on the menu bar, the function will be called again.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninitmenupopup"></a>  CWnd::OnInitMenuPopup  
 The framework calls this member function when a pop-up menu is about to become active.  
  
```  
afx_msg OnInitMenuPopup (CMenu * pPopupMenu を無効にします。  
    UINT nIndex  
    BOOL bSysMenu) です。
```  
  
### Parameters  
 *pPopupMenu*  
 Specifies the menu object of the pop-up menu. May be temporary and should not be stored for later use.  
  
 `nIndex`  
 Specifies the index of the pop-up menu in the main menu.  
  
 *bSysMenu*  
 **TRUE** if the pop-up menu is the Control menu; otherwise **FALSE**.  
  
### Remarks  
 This allows an application to modify the pop-up menu before it is displayed without changing the entire menu.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninputdevicechange"></a>  CWnd::OnInputDeviceChange  
 The framework calls this member function when an I/O device is added or removed from the system.  
  
```  
afx_msg OnInputDeviceChange (符号なし short uFlag); を無効にします。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `uFlag`|This flag can contain the following values:<br /><br /> - `GIDC_ARRIVAL` - A new device has been added to the system.<br />- `GIDC_REMOVAL` - A device has been removed from the system.|  
  
### Remarks  
 This method receives the [WM_INPUT_DEVICE_CHANGE](http://msdn.microsoft.com/library/windows/desktop/ms645591) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. The is a generic input device message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninputlangchange"></a>  CWnd::OnInputLangChange  
 The framework calls this member for the topmost affected window after an application's input language has been changed.  
  
```  
afx_msg OnInputLangChange (UINT nCharSet を無効にします。   
    UINT nLocaleId) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nCharSet`|The character set of the new locale. For more information, see the `lfCharSet` parameter of the [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) structure.|  
|[in] `nLocaleId`|The input locale identifier. For more information, see [Language Identifier Constants and Strings](http://msdn.microsoft.com/library/windows/desktop/dd318693).|  
  
### Remarks  
 This method receives the [WM_INPUTLANGCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms632629) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninputlangchangerequest"></a>  CWnd::OnInputLangChangeRequest  
 The framework calls this member for window with the focus when the user chooses a new input language.  
  
```  
afx_msg OnInputLangChangeRequest (UINT nFlags を無効にします。   
    UINT nLocaleId) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise (OR) combination of flags that indicate the new locale was selected from the previous or next locale in the installed list of locales, or that the new input locale's keyboard layout can be used with the system character set.<br /><br /> The possible values are `INPUTLANGCHANGE_BACKWARD`, `INPUTLANGCHANGE_FORWARD`, and `INPUTLANGCHANGE_SYSCHARSET`.|  
|[in] `nLocaleId`|The input locale identifier. For more information, see [Language Identifier Constants and Strings](http://msdn.microsoft.com/library/windows/desktop/dd318693).|  
  
### Remarks  
 This method receives the [WM_INPUTLANGCHANGEREQUEST](http://msdn.microsoft.com/library/windows/desktop/ms632630) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted when the user chooses a new input language with either a hotkey that is specified in the keyboard control panel application, or from the indicator on the system taskbar.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onkeydown"></a>  CWnd::OnKeyDown  
 The framework calls this member function when a nonsystem key is pressed.  
  
```  
afx_msg OnKeyDown (UINT nChar を無効にします。  
    UINT nRepCnt  
    UINT nFlags) です。
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the given key. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Repeat count (the number of times the keystroke is repeated as a result of the user holding down the key).  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Description|  
|-----------|-----------------|  
|0–7|Scan code (OEM-dependent value).|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For a `WM_KEYDOWN` message, the key-transition bit (bit 15) is 0 and the context-code bit (bit 13) is 0.  
  
### Remarks  
 A nonsystem key is a keyboard key that is pressed when the ALT key is not pressed or a keyboard key that is pressed when `CWnd` has the input focus.  
  
 Because of auto-repeat, more than one `OnKeyDown` call may occur before an [OnKeyUp](#onkeyup) member function call is made. The bit that indicates the previous key state can be used to determine whether the `OnKeyDown` call is the first down transition or a repeated down transition.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onkeyup"></a>  CWnd::OnKeyUp  
 The framework calls this member function when a nonsystem key is released.  
  
```  
afx_msg OnKeyUp (UINT nChar を無効にします。  
    UINT nRepCnt  
    UINT nFlags) です。
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the given key. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Repeat count (the number of times the keystroke is repeated as a result of the user holding down the key).  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Description|  
|-----------|-----------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For a `WM_KEYUP` message, the key-transition bit (bit 15) is 1 and the context-code bit (bit 13) is 0.  
  
### Remarks  
 A nonsystem key is a keyboard key that is pressed when the ALT key is not pressed or a keyboard key that is pressed when the `CWnd` has the input focus.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onkillfocus"></a>  CWnd::OnKillFocus  
 The framework calls this member function immediately before losing the input focus.  
  
```  
afx_msg OnKillFocus (CWnd * pNewWnd); を無効にします。
```  
  
### Parameters  
 *pNewWnd*  
 Specifies a pointer to the window that receives the input focus (may be **NULL** or may be temporary).  
  
### Remarks  
 If the `CWnd` object is displaying a caret, the caret should be destroyed at this point.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onlbuttondblclk"></a>  CWnd::OnLButtonDblClk  
 The framework calls this member function when the user double-clicks the left mouse button.  
  
```  
afx_msg 離し (UINT nFlags を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 Only windows that have the **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) style will receive `OnLButtonDblClk` calls. This is the default for Microsoft Foundation Class windows. Windows calls `OnLButtonDblClk` when the user presses, releases, and then presses the left mouse button again within the system's double-click time limit. Double-clicking the left mouse button actually generates four events: [WM_LBUTTONDOWN](#onlbuttondown), [WM_LBUTTONUP](#onlbuttonup) messages, the `WM_LBUTTONDBLCLK` call, and another `WM_LBUTTONUP` message when the button is released.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onlbuttondown"></a>  CWnd::OnLButtonDown  
 The framework calls this member function when the user presses the left mouse button.  
  
```  
afx_msg OnLButtonDown (UINT nFlags を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onlbuttonup"></a>  CWnd::OnLButtonUp  
 The framework calls this member function when the user releases the left mouse button.  
  
```  
afx_msg OnLButtonUp (UINT nFlags を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmbuttondblclk"></a>  CWnd::OnMButtonDblClk  
 The framework calls this member function when the user double-clicks the middle mouse button.  
  
```  
afx_msg 離し (UINT nFlags を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 Only windows that have the **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) style will receive `OnMButtonDblClk` calls. This is the default for all Microsoft Foundation Class windows. Windows generates an `OnMButtonDblClk` call when the user presses, releases, and then presses the middle mouse button again within the system's double-click time limit. Double-clicking the middle mouse button actually generates four events: [WM_MBUTTONDOWN](#onmbuttondown) and [WM_MBUTTONUP](#onmbuttonup) messages, the `WM_MBUTTONDBLCLK` call, and another `WM_MBUTTONUP` message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmbuttondown"></a>  CWnd::OnMButtonDown  
 The framework calls this member function when the user presses the middle mouse button.  
  
```  
afx_msg OnMButtonDown (UINT nFlags を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmbuttonup"></a>  CWnd::OnMButtonUp  
 The framework calls this member function when the user releases the middle mouse button.  
  
```  
afx_msg OnMButtonUp (UINT nFlags を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmdiactivate"></a>  CWnd::OnMDIActivate  
 The framework calls this member function for the child window being deactivated and the child window being activated.  
  
```  
afx_msg を無効になる (BOOL bActivate、  
    CWnd*受け取る CWnd* pDeactivateWnd) です。
```  
  
### Parameters  
 `bActivate`  
 **TRUE** if the child is being activated and **FALSE** if it is being deactivated.  
  
 `pActivateWnd`  
 Contains a pointer to the MDI child window to be activated. When received by an MDI child window, `pActivateWnd` contains a pointer to the child window being activated. This pointer may be temporary and should not be stored for later use.  
  
 *pDeactivateWnd*  
 Contains a pointer to the MDI child window being deactivated. This pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 An MDI child window is activated independently of the MDI frame window. When the frame becomes active, the child window that was last activated with a `OnMDIActivate` call receives an [WM_NCACTIVATE](#onncactivate) message to draw an active window frame and caption bar, but it does not receive another `OnMDIActivate` call.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmeasureitem"></a>  CWnd::OnMeasureItem  
 The framework calls this member function by the framework for the owner of an owner-draw button, combo box, list box, or menu item when the control is created.  
  
```  
afx_msg OnMeasureItem (int 送るとき、LPMEASUREITEMSTRUCT lpMeasureItemStruct) を無効にします。
```  
  
### Parameters  
 `nIDCtl`  
 The ID of the control.  
  
 `lpMeasureItemStruct`  
 Points to a [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) data structure that contains the dimensions of the owner-draw control.  
  
### Remarks  
 Override this member function and fill in the `MEASUREITEMSTRUCT` data structure pointed to by `lpMeasureItemStruct` and return; this informs Windows of the dimensions of the control and allows Windows to process user interaction with the control correctly.  
  
 If a list box or combo box is created with the [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) or [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) style, the framework calls this function for the owner for each item in the control; otherwise this function is called once.  
  
 Windows initiates the call to `OnMeasureItem` for the owner of combo boxes and list boxes created with the **OWNERDRAWFIXED** style before sending the [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) message. As a result, when the owner receives this call, Windows has not yet determined the height and width of the font used in the control; function calls and calculations that require these values should occur in the main function of the application or library.  
  
 If the item being measured is a `CMenu`, `CListBox` or `CComboBox` object, then the `MeasureItem` virtual function of the appropriate class is called. Override the `MeasureItem` member function of the appropriate control's class to calculate and set the size of each item.  
  
 `OnMeasureItem` will be called only if the control's class is created at run time, or it is created with the **LBS_OWNERDRAWVARIABLE** or **CBS_OWNERDRAWVARIABLE** style. If the control is created by the dialog editor, `OnMeasureItem` will not be called. This is because the [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) message is sent early in the creation process of the control. If you subclass by using `DDX_Control`, `SubclassDlgItem`, or `SubclassWindow`, the subclassing usually occurs after the creation process. Therefore, there is no way to handle the [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) message in the control's `OnChildNotify` function, which is the mechanism MFC uses to implement **ON_WM_MEASUREITEM_REFLECT**.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenuchar"></a>  CWnd::OnMenuChar  
 The framework calls this member function when the user presses a menu mnemonic character that doesn't match any of the predefined mnemonics in the current menu.  
  
```  
afx_msg LRESULT OnMenuChar (UINT nChar、  
    UINT nFlags  
    CMenu* pMenu) です。
```  
  
### Parameters  
 `nChar`  
 Depending on the build settings, specifies the ANSI or Unicode character that the user pressed.  
  
 `nFlags`  
 Contains the **MF_POPUP** flag if the menu is a pop-up menu. It contains the **MF_SYSMENU** flag if the menu is a Control menu.  
  
 `pMenu`  
 Contains a pointer to the selected `CMenu`. The pointer may be temporary and should not be stored.  
  
### Return Value  
 The high-order word of the return value should contain one of the following command codes:  
  
|Value|Description|  
|-----------|-----------------|  
|0|Tells Windows to discard the character that the user pressed and creates a short beep on the system speaker.|  
|1|Tells Windows to close the current menu.|  
|2|Informs Windows that the low-order word of the return value contains the item number for a specific item. This item is selected by Windows.|  
  
 The low-order word is ignored if the high-order word contains 0 or 1. Applications should process this message when accelerator (shortcut) keys are used to select bitmaps placed in a menu.  
  
### Remarks  
 It is sent to the `CWnd` that owns the menu. `OnMenuChar` is also called when the user presses ALT and any other key, even if the key does not correspond to a mnemonic character. In this case, `pMenu` points to the menu owned by the `CWnd`, and `nFlags` is 0.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenudrag"></a>  CWnd::OnMenuDrag  
 The framework calls this member function of the current drag-and-drop menu when the user begins to drag a menu item.  
  
```  
afx_msg UINT OnMenuDrag (UINT nPos、   
    CMenu* pMenu) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nPos`|The index position of the menu item when the drag operation begins.|  
|[in] `pMenu`|Pointer to the [CMenu](../../mfc/reference/cmenu-class.md) object that contains the menu item.|  
  
### Return Value  
  
|Return Value|Meaning|  
|------------------|-------------|  
|`MND_CONTINUE`|The menu should remain active. If the mouse is released, it should be ignored.|  
|`MND_ENDMENU`|The menu should be ended.|  
  
### Remarks  
 This method receives the [WM_MENUDRAG](http://msdn.microsoft.com/library/windows/desktop/ms647606) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenugetobject"></a>  CWnd::OnMenuGetObject  
 The framework calls this member function of the current drag-and-drop menu when the mouse cursor enters a menu item or moves from the center of the item to the top or bottom of the item.  
  
```  
afx_msg UINT OnMenuGetObject(MENUGETOBJECTINFO* pMenuGetObjectInfo) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pMenu`|Pointer to a [MENUGETOBJECTINFO](http://msdn.microsoft.com/library/windows/desktop/ms647572) structure that contains information about the drag-and-drop menu the mouse cursor is on.|  
  
### Return Value  
  
|Return Value|Meaning|  
|------------------|-------------|  
|`MNGO_NOERROR`|An interface pointer that supports drop-and-drag operations is returned in the `pvObj` member of the [MENUGETOBJECTINFO](http://msdn.microsoft.com/library/windows/desktop/ms647572) structure. Currently, only the [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) interface is supported.|  
|`MNGO_NOINTERFACE`|No drop-and-drag interface is supported.|  
  
### Remarks  
 This method receives the [WM_MENUGETOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms647607) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenurbuttonup"></a>  CWnd::OnMenuRButtonUp  
 The framework calls this member function when the user releases the right mouse button while the cursor is on a menu item.  
  
```  
afx_msg OnMenuRButtonUp (UINT nPos を無効にします。  
    CMenu* pMenu) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nPos`|The index position of the menu item when the right mouse button was released.|  
|[in] `pMenu`|Pointer to the [CMenu](../../mfc/reference/cmenu-class.md) object that contains the menu item.|  
  
### Remarks  
 This method receives the [WM_MENURBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms647610) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. The [WM_MENURBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms647610) message enables an application to provide a context-sensitive menu for the menu item specified in the message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenuselect"></a>  CWnd::OnMenuSelect  
 If the `CWnd` object is associated with a menu, `OnMenuSelect` is called by the framework when the user selects a menu item.  
  
```  
afx_msg OnMenuSelect (UINT nItemID を無効にします。  
    UINT nFlags  
    HMENU hSysMenu) です。
```  
  
### Parameters  
 `nItemID`  
 Identifies the item selected. If the selected item is a menu item, `nItemID` contains the menu-item ID. If the selected item contains a pop-up menu, `nItemID` contains the pop-up menu index, and *hSysMenu* contains the handle of the main (clicked-on) menu.  
  
 `nFlags`  
 Contains a combination of the following menu flags:  
  
- **MF_BITMAP** Item is a bitmap.  
  
- **MF_CHECKED** Item is checked.  
  
- **MF_DISABLED** Item is disabled.  
  
- **MF_GRAYED** Item is dimmed.  
  
- **MF_MOUSESELECT** Item was selected with a mouse.  
  
- `MF_OWNERDRAW` Item is an owner-draw item.  
  
- **MF_POPUP** Item contains a pop-up menu.  
  
- **MF_SEPARATOR** Item is a menu-item separator.  
  
- **MF_SYSMENU** Item is contained in the Control menu.  
  
 `hSysMenu`  
 If `nFlags` contains **MF_SYSMENU**, identifies the menu associated with the message. If `nFlags` contains **MF_POPUP**, identifies the handle of the main menu. If `nFlags` contains neither **MF_SYSMENU** nor **MF_POPUP**, it is unused.  
  
### Remarks  
 If `nFlags` contains 0xFFFF and `hSysMenu` contains 0, Windows has closed the menu because the user pressed the ESC key or clicked outside the menu.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmouseactivate"></a>  CWnd::OnMouseActivate  
 The framework calls this member function when the cursor is in an inactive window and the user presses a mouse button.  
  
```  
afx_msg int OnMouseActivate (CWnd * pDesktopWnd、  
    UINT nHitTest  
    UINT メッセージ)。
```  
  
### Parameters  
 *pDesktopWnd*  
 Specifies a pointer to the top-level parent window of the window being activated. The pointer may be temporary and should not be stored.  
  
 `nHitTest`  
 Specifies the [hit-test](#onnchittest) area code. A hit test is a test that determines the location of the cursor.  
  
 `message`  
 Specifies the mouse message number.  
  
### Return Value  
 Specifies whether to activate the `CWnd` and whether to discard the mouse event. It must be one of the following values:  
  
- **MA_ACTIVATE** Activate `CWnd` object.  
  
- **MA_NOACTIVATE** Do not activate `CWnd` object.  
  
- **MA_ACTIVATEANDEAT** Activate `CWnd` object and discard the mouse event.  
  
- **MA_NOACTIVATEANDEAT** Do not activate `CWnd` object and discard the mouse event.  
  
### Remarks  
 The default implementation passes this message to the parent window before any processing occurs. If the parent window returns **TRUE**, processing is halted.  
  
 For a description of the individual hit-test area codes, see the [OnNcHitTest](#onnchittest) member function  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCAxCtl#9](../../mfc/reference/codesnippet/cpp/cwnd-class_49.cpp)]  
  
##  <a name="onmousehover"></a>  CWnd::OnMouseHover  
 The framework calls this member function when the cursor hovers over the client area of the window for the period of time specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
afx_msg OnMouseHover (UINT nFlags を無効にします。   
    CPoint ポイント)。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_MOUSEHOVER](http://msdn.microsoft.com/library/windows/desktop/ms645613) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmousehwheel"></a>  CWnd::OnMouseHWheel  
 The framework calls this member when the current window is composed by the Desktop Window Manager (DWM), and that window is maximized.  
  
```  
afx_msg OnMouseHWheel (UINT nFlags を無効にします。   
    短い zDelta   
    CPoint pt) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.<br /><br /> For a list of flags, see the "Message Parameters" subheading in [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).|  
|[in] `zDelta`|Indicates the distance the wheel is rotated, expressed in multiples or divisions of `WHEEL_DELTA`, which is 120. A positive value indicates that the wheel was rotated to the right; a negative value indicates that the wheel was rotated to the left.|  
|[in] `pt`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_MOUSEHWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645614) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is sent to the window that has the focus when the mouse's horizontal scroll wheel is tilted or rotated.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmouseleave"></a>  CWnd::OnMouseLeave  
 The framework calls this member function when the cursor leaves the client area of the window specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
afx_msg OnMouseLeave(); を無効にします。
```  
  
### Remarks  
 This method receives the [WM_MOUSELEAVE](http://msdn.microsoft.com/library/windows/desktop/ms645615) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmousemove"></a>  CWnd::OnMouseMove  
 The framework calls this member function when the mouse cursor moves.  
  
```  
afx_msg OnMouseMove (UINT nFlags を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 If the mouse is not captured, the `WM_MOUSEMOVE` message is received by the `CWnd` object beneath the mouse cursor; otherwise, the message goes to the window that has captured the mouse.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmousewheel"></a>  CWnd::OnMouseWheel  
 The framework calls this member function as a user rotates the mouse wheel and encounters the wheel's next notch.  
  
```  
afx_msg BOOL OnMouseWheel (UINT nFlags、  
    短い zDelta  
    CPoint pt) です。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `zDelta`  
 Indicates distance rotated. The `zDelta` value is expressed in multiples or divisions of **WHEEL_DELTA**, which is 120. A value less than zero indicates rotating back (toward the user) while a value greater than zero indicates rotating forward (away from the user). The user can reverse this response by changing the Wheel setting in the mouse software. See the Remarks for more information about this parameter.  
  
 `pt`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the screen.  
  
### Return Value  
 Nonzero if mouse wheel scrolling is enabled; otherwise 0.  
  
### Remarks  
 Unless overridden, `OnMouseWheel` calls the default of [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617). Windows automatically routes the message to the control or child window that has the focus. The Win32 function [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) propagates the message up the parent chain to the window that processes it.  
  
 The `zDelta` parameter is a multiple of **WHEEL_DELTA**, which is set at 120. This value is the threshold for an action to be taken, and one such action (for example, scrolling forward one notch) should occur for each delta.  
  
 **WHEEL_DELTA** was set to 120 to allow for finer-resolution wheels, such as a freely-rotating wheel with no notches. A finer-resolution wheel sends more messages per rotation, but each message has a smaller delta value. To use such a wheel, either add the incoming `zDelta` values until **WHEEL_DELTA** is reached (so that you get the same response for a given delta-rotation), or scroll partial lines in response to the more frequent messages. You can also choose a scroll granularity and accumulate deltas until **WHEEL_DELTA** is reached.  
  
 Override this member function to provide your own mouse-wheel scrolling behavior.  
  
> [!NOTE]
> `OnMouseWheel` handles messages for Windows NT 4.0 and later versions. For Windows 95/98 or Windows NT 3.51 message handling, use [OnRegisteredMouseWheel](#onregisteredmousewheel).  
  
##  <a name="onmove"></a>  CWnd::OnMove  
 The framework calls this member function after the `CWnd` object has been moved.  
  
```  
afx_msg void OnMove (int x  
    int y) にします。
```  
  
### Parameters  
 *x*  
 Specifies the new x-coordinate location of the upper-left corner of the client area. This new location is given in screen coordinates for overlapped and pop-up windows, and parent-client coordinates for child windows.  
  
 *y*  
 Specifies the new y-coordinate location of the upper-left corner of the client area. This new location is given in screen coordinates for overlapped and pop-up windows, and parent-client coordinates for child windows.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmoving"></a>  CWnd::OnMoving  
 The framework calls this member function while a user is moving a `CWnd` object.  
  
```  
afx_msg OnMoving (UINT nSide を無効にします。  
    LPRECT lpRect) です。
```  
  
### Parameters  
 `nSide`  
 The edge of window to be moved.  
  
 `lpRect`  
 Address of the [CRect](../../atl-mfc-shared/reference/crect-class.md) or [RECT structure](../../mfc/reference/rect-structure1.md) that will contain the item's coordinates.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncactivate"></a>  CWnd::OnNcActivate  
 The framework calls this member function when the nonclient area needs to be changed to indicate an active or inactive state.  
  
```  
afx_msg BOOL OnNcActivate(BOOL bActive) です。
```  
  
### Parameters  
 `bActive`  
 Specifies when a caption bar or icon needs to be changed to indicate an active or inactive state. The `bActive` parameter is **TRUE** if an active caption or icon is to be drawn. It is **FALSE** for an inactive caption or icon.  
  
### Return Value  
 Nonzero if Windows should proceed with default processing; 0 to prevent the caption bar or icon from being deactivated.  
  
### Remarks  
 The default implementation draws the title bar and title-bar text in their active colors if `bActive` is **TRUE** and in their inactive colors if `bActive` is **FALSE**.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnccalcsize"></a>  CWnd::OnNcCalcSize  
 The framework calls this member function when the size and position of the client area needs to be calculated.  
  
```  
afx_msg OnNcCalcSize (BOOL bCalcValidRects を無効にします。  
    NCCALCSIZE_PARAMS* lpncsp) です。
```  
  
### Parameters  
 `bCalcValidRects`  
 Specifies whether the application should specify which part of the client area contains valid information. Windows will copy the valid information to the specified area within the new client area. If this parameter is **TRUE**, the application should specify which part of the client area is valid.  
  
 `lpncsp`  
 Points to a [NCCALCSIZE_PARAMS](../../mfc/reference/nccalcsize-params-structure.md) data structure that contains information an application can use to calculate the new size and position of the `CWnd` rectangle (including client area, borders, caption, scroll bars, and so on).  
  
### Remarks  
 By processing this message, an application can control the contents of the window's client area when the size or position of the window changes.  
  
 Regardless of the value of `bCalcValidRects`, the first rectangle in the array specified by the **rgrc** structure member of the `NCCALCSIZE_PARAMS` structure contains the coordinates of the window. For a child window, the coordinates are relative to the parent window's client area. For top-level windows, the coordinates are screen coordinates. An application should modify the **rgrc[0]** rectangle to reflect the size and position of the client area.  
  
 The **rgrc[1]** and **rgrc[2]** rectangles are valid only if `bCalcValidRects` is **TRUE**. In this case, the **rgrc[1]** rectangle contains the coordinates of the window before it was moved or resized. The **rgrc[2]** rectangle contains the coordinates of the window's client area before the window was moved. All coordinates are relative to the parent window or screen.  
  
 The default implementation calculates the size of the client area based on the window characteristics (presence of scroll bars, menu, and so on), and places the result in `lpncsp`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnccreate"></a>  CWnd::OnNcCreate  
 The framework calls this member function prior to the [WM_CREATE](#oncreate) message when the `CWnd` object is first created.  
  
```  
afx_msg BOOL OnNcCreate(LPCREATESTRUCT lpCreateStruct) です。
```  
  
### Parameters  
 `lpCreateStruct`  
 Points to the [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) data structure for `CWnd`.  
  
### Return Value  
 Nonzero if the nonclient area is created. It is 0 if an error occurs; the **Create** function will return **failure** in this case.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncdestroy"></a>  CWnd::OnNcDestroy  
 Called by the framework when the nonclient area is being destroyed, and is the last member function called when the Windows window is destroyed.  
  
```  
afx_msg OnNcDestroy(); を無効にします。
```  
  
### Remarks  
 The default implementation performs some cleanup, then calls the virtual member function [PostNcDestroy](#postncdestroy).  
  
 Override `PostNcDestroy` if you want to perform your own cleanup, such as a **delete this** operation. If you override `OnNcDestroy`, you must call `OnNcDestroy` in your base class to ensure that any memory internally allocated for the window is freed.  
  
##  <a name="onnchittest"></a>  CWnd::OnNcHitTest  
 The framework calls this member function for the `CWnd` object that contains the cursor (or the `CWnd` object that used the [SetCapture](#setcapture) member function to capture the mouse input) every time the mouse is moved.  
  
```  
afx_msg LRESULT OnNcHitTest(CPoint point) です。
```  
  
### Parameters  
 `point`  
 Contains the x- and y-coordinates of the cursor. These coordinates are always screen coordinates.  
  
### Return Value  
 One of the mouse hit-test enumerated values listed below.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnclbuttondblclk"></a>  CWnd::OnNcLButtonDblClk  
 The framework calls this member function when the user double-clicks the left mouse button while the cursor is within a nonclient area of `CWnd`.  
  
```  
afx_msg OnNcLButtonDblClk (UINT nHitTest を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, the [WM_SYSCOMMAND](#onsyscommand) message is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnclbuttondown"></a>  CWnd::OnNcLButtonDown  
 The framework calls this member function when the user presses the left mouse button while the cursor is within a nonclient area of the `CWnd` object.  
  
```  
afx_msg OnNcLButtonDown (UINT nHitTest を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, the [WM_SYSCOMMAND](#onsyscommand) is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received.If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnclbuttonup"></a>  CWnd::OnNcLButtonUp  
 The framework calls this member function when the user releases the left mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg OnNcLButtonUp (UINT nHitTest を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, [WM_SYSCOMMAND](#onsyscommand) is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmbuttondblclk"></a>  CWnd::OnNcMButtonDblClk  
 The framework calls this member function when the user double-clicks the middle mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg OnNcMButtonDblClk (UINT nHitTest を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmbuttondown"></a>  CWnd::OnNcMButtonDown  
 The framework calls this member function when the user presses the middle mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg OnNcMButtonDown (UINT nHitTest を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmbuttonup"></a>  CWnd::OnNcMButtonUp  
 The framework calls this member function when the user releases the middle mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg OnNcMButtonUp (UINT nHitTest を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmousehover"></a>  CWnd::OnNcMouseHover  
 The framework calls this member function when the cursor hovers over the nonclient area of the window for the period of time specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
afx_msg OnNcMouseHover (UINT nHitTest を無効にします。   
    CPoint ポイント)。  
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the screen.|  
  
### Remarks  
 This method receives the [WM_NCMOUSEHOVER](http://msdn.microsoft.com/library/windows/desktop/ms645625) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmouseleave"></a>  CWnd::OnNcMouseLeave  
 The framework calls this member function when the cursor leaves the nonclient area of the window specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
afx_msg OnNcMouseLeave(); を無効にします。
```  
  
### Remarks  
 This method receives the [WM_NCMOUSELEAVE](http://msdn.microsoft.com/library/windows/desktop/ms645626) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmousemove"></a>  CWnd::OnNcMouseMove  
 The framework calls this member function when the cursor is moved within a nonclient area.  
  
```  
afx_msg OnNcMouseMove (UINT nHitTest を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, the [WM_SYSCOMMAND](#onsyscommand) message is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncpaint"></a>  CWnd::OnNcPaint  
 The framework calls this member function when the nonclient area needs to be painted.  
  
```  
afx_msg OnNcPaint(); を無効にします。
```  
  
### Remarks  
 The default implementation paints the window frame.  
  
 An application can override this call and paint its own custom window frame. The clipping region is always rectangular, even if the shape of the frame is altered.  
  
##  <a name="onncrbuttondblclk"></a>  CWnd::OnNcRButtonDblClk  
 The framework calls this member function when the user double-clicks the right mouse button while the cursor is within a nonclient area of `CWnd`.  
  
```  
afx_msg OnNcRButtonDblClk (UINT nHitTest を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncrbuttondown"></a>  CWnd::OnNcRButtonDown  
 The framework calls this member function when the user presses the right mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg OnNcRButtonDown (UINT nHitTest を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncrbuttonup"></a>  CWnd::OnNcRButtonUp  
 The framework calls this member function when the user releases the right mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg OnNcRButtonUp (UINT nHitTest を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncrenderingchanged"></a>  CWnd::OnNcRenderingChanged  
 The framework calls this member when the rendering policy for the nonclient area has changed.  
  
```  
afx_msg OnNcRenderingChanged (BOOL bIsRendering); を無効にします。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `bIsRendering`|`true` if Desktop Window Manager (DWM) rendering is enabled for the nonclient area of the window; `false` if rendering is disabled.|  
  
### Remarks  
 This method receives the [WM_DWMNCRENDERINGCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388200) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncxbuttondblclk"></a>  CWnd::OnNcXButtonDblClk  
 The framework calls this member function when the user double-clicks XBUTTON1 or XBUTTON2 while the cursor is in the nonclient area of a window.  
  
```  
void OnNcXButtonDblClk (短い nHitTest、   
    UINT nButton   
    CPoint ポイント)。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button is double-clicked, or `XBUTTON2` if the second X button is double-clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms646244) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted to the window that contains the cursor. If a window has captured the mouse, this message is not posted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncxbuttondown"></a>  CWnd::OnNcXButtonDown  
 The framework calls this member function when the user presses XBUTTON1 or XBUTTON2 of the mouse while the cursor is in the nonclient area of a window.  
  
```  
afx_msg OnNcXButtonDown (短い nHitTest を無効にします。   
    UINT nButton   
    CPoint ポイント)。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `nButton`|A value of `XBUTTON1` if the first mouse X button is pressed, or `XBUTTON2` if the second X button is pressed.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the screen.|  
  
### Remarks  
 This method receives the [WM_NCXBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645632) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted to the window that contains the cursor. If a window has captured the mouse, this message is not posted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncxbuttonup"></a>  CWnd::OnNcXButtonUp  
 The framework calls this member function when the user releases XBUTTON1 or XBUTTON2 of the mouse while the cursor is in the nonclient area of a window.  
  
```  
afx_msg OnNcXButtonUp (短い nHitTest を無効にします。   
    UINT nButton   
    CPoint ポイント)。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `nButton`|A value of `XBUTTON1` if the first mouse X button is released, or `XBUTTON2` if the second X button is released.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the screen.|  
  
### Remarks  
 This method receives the [WM_NCXBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646240) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted to the window that contains the cursor. If a window has captured the mouse, this message is not posted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnextmenu"></a>  CWnd::OnNextMenu  
 The framework calls this member function when when the right or left arrow key is used to switch between the menu bar and the system menu.  
  
```  
afx_msg OnNextMenu (UINT nKey を無効にします。  
    LPMDINEXTMENU lpMdiNextMenu) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nKey`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.<br /><br /> For a list of flags, see the "Message Parameters" subheading in [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).|  
|[in] `lpMdiNextMenu`|Pointer to a [MDINEXTMENU](http://msdn.microsoft.com/library/windows/desktop/ms647561) structure that contains information about the menu to be activated.|  
  
### Remarks  
 This method receives the [WM_UNINITMENUPOPUP](http://msdn.microsoft.com/library/windows/desktop/ms647614) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In response to this message, your application can set the `hmenuNext` member of the [MDINEXTMENU](http://msdn.microsoft.com/library/windows/desktop/ms647561) structure to specify the menu to switch to, and the `hwndNext` member to specify the window to receive menu notification messages.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnotify"></a>  CWnd::OnNotify  
 The framework calls this member function to inform the parent window of a control that an event has occurred in the control or that the control requires some kind of information.  
  
```  
仮想 BOOL OnNotify (WPARAM の wParam は、  
    LPARAM lParam  
    LRESULT* pResult) です。
```  
  
### Parameters  
 `wParam`  
 Identifies the control that sends the message if the message is from a control. Otherwise, `wParam` is 0.  
  
 `lParam`  
 Pointer to a notification message ( **NMHDR**) structure that contains the notification code and additional information. For some notification messages, this parameter points to a larger structure that has the **NMHDR** structure as its first member.  
  
 `pResult`  
 Pointer to an **LRESULT** variable in which to store the result code if the message is handled.  
  
### Return Value  
 An application returns nonzero if it processes this message; otherwise 0.  
  
### Remarks  
 `OnNotify` processes the message map for control notification.  
  
 Override this member function in your derived class to handle the **WM_NOTIFY** message. An override will not process the message map unless the base class `OnNotify` is called.  
  
 For more information on the WM_NOTIFY message, see Technical Note 61 (TN061), [ON_NOTIFY and WM_NOTIFY messages](../../mfc/tn061-on-notify-and-wm-notify-messages.md). You may also be interested the related topics described in [Control Topics](../../mfc/controls-mfc.md), and TN062, [Message Reflection for Windows Controls](../../mfc/tn062-message-reflection-for-windows-controls.md).  
  
##  <a name="onnotifyformat"></a>  CWnd::OnNotifyFormat  
 The framework calls this member function to determine if the current window accepts ANSI or Unicode structures in the WM_NOTIFY notification message.  
  
```  
afx_msg UINT OnNotifyFormat (CWnd * 我が物、   
    UINT %t%7) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pWnd`|A pointer to a `CWnd` object that represents the window sending the [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) message.<br /><br /> This parameter is the pointer to a control if the `nCommand` parameter is `NF_QUERY`, or the pointer to the parent window of a control if `nCommand` is `NF_REQUERY`.|  
|[in] `nCommand`|A command value that specializes the **WM_NOTIFY** message. The possible values are:<br /><br /> - `NF_QUERY` -<br />     The message is a query to determine whether ANSI or Unicode structures should be used in **WM_NOTIFY** messages. This message is sent from a control to its parent window during the creation of a control, and in response to the `NF_REQUERY` form of this message.<br />- `NF_REQUERY` -<br />     The message is a request for a control to send the `NF_QUERY` form of this message to its parent window. This request is sent from the parent window, and asks the control to requery the parent about the type of structure to use in **WM_NOTIFY** messages. If the `nCommand` parameter is `NF_REQUERY`, the return value is the result of the requery operation.|  
  
### Return Value  
  
|Return value|Meaning|  
|------------------|-------------|  
|`NFR_ANSI`|ANSI structures should be used in **WM_NOTIFY** messages sent by the control.|  
|`NFR_UNICODE`|Unicode structures should be used in **WM_NOTIFY** messages sent by the control.|  
|0|An error occurred.|  
  
### Remarks  
 This method receives the [WM_NOTIFYFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb775584) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. **WM_NOTIFY** messages are sent from a common control to its parent window, and from the parent window to the common control.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpaint"></a>  CWnd::OnPaint  
 The framework calls this member function when Windows or an application makes a request to repaint a portion of an application's window.  
  
```  
afx_msg OnPaint(); を無効にします。
```  
  
### Remarks  
 The [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145137) message is sent when the [UpdateWindow](#updatewindow) or [RedrawWindow](#redrawwindow) member function is called.  
  
 A window may receive internal paint messages as a result of calling the `RedrawWindow` member function with the **RDW_INTERNALPAINT** flag set. In this case, the window may not have an update region. An application should call the [GetUpdateRect](#getupdaterect) member function to determine whether the window has an update region. If `GetUpdateRect` returns 0, the application should not call the [BeginPaint](#beginpaint) and [EndPaint](#endpaint) member functions.  
  
 It is an application's responsibility to check for any necessary internal repainting or updating by looking at its internal data structures for each `WM_PAINT` message because a `WM_PAINT` message may have been caused by both an invalid area and a call to the `RedrawWindow` member function with the **RDW_INTERNALPAINT** flag set.  
  
 An internal `WM_PAINT` message is sent only once by Windows. After an internal `WM_PAINT` message is sent to a window by the `UpdateWindow` member function, no further `WM_PAINT` messages will be sent or posted until the window is invalidated or until the `RedrawWindow` member function is called again with the **RDW_INTERNALPAINT** flag set.  
  
 For information on rendering an image in document/view applications, see [CView::OnDraw](../../mfc/reference/cview-class.md#ondraw).  
  
 For more information about using **WM_Paint**, see the following topics in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]:  
  
- [The WM_PAINT Message](http://msdn.microsoft.com/library/windows/desktop/dd145137)  
  
- [Using the WM_PAINT Message](http://msdn.microsoft.com/library/windows/desktop/dd145193)  
  
##  <a name="onpaintclipboard"></a>  CWnd::OnPaintClipboard  
 A Clipboard owner's `OnPaintClipboard` member function is called by a Clipboard viewer when the Clipboard owner has placed data on the Clipboard in the `CF_OWNERDISPLAY` format and the Clipboard viewer's client area needs repainting.  
  
```  
afx_msg OnPaintClipboard (CWnd * pClipAppWnd を無効にします。  
    HGLOBAL hPaintStruct) です。
```  
  
### Parameters  
 `pClipAppWnd`  
 Specifies a pointer to the Clipboard-application window. The pointer may be temporary and should not be stored for later use.  
  
 *hPaintStruct*  
 Identifies a [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) data structure that defines what part of the client area to paint.  
  
### Remarks  
 To determine whether the entire client area or just a portion of it needs repainting, the Clipboard owner must compare the dimensions of the drawing area given in the **rcpaint** member of the `PAINTSTRUCT` structure to the dimensions given in the most recent [OnSizeClipboard](#onsizeclipboard) member function call.  
  
 `OnPaintClipboard` should use the [GlobalLock](http://msdn.microsoft.com/library/windows/desktop/aa366584) Windows function to lock the memory that contains the `PAINTSTRUCT` data structure and unlock that memory with the [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows function before it exits.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpalettechanged"></a>  CWnd::OnPaletteChanged  
 The framework calls this member function for all top-level windows after the window with input focus has realized its logical palette, thereby changing the system palette.  
  
```  
afx_msg OnPaletteChanged (CWnd * pFocusWnd); を無効にします。
```  
  
### Parameters  
 `pFocusWnd`  
 Specifies a pointer to the window that caused the system palette to change. The pointer may be temporary and should not be stored.  
  
### Remarks  
 This call allows a window without the input focus that uses a color palette to realize its logical palettes and update its client area.  
  
 The `OnPaletteChanged` member function is called for all top-level and overlapped windows, including the one that changed the system palette and caused the `WM_PALETTECHANGED` message to be sent. If any child window uses a color palette, this message must be passed on to it.  
  
 To avoid an infinite loop, the window shouldn't realize its palette unless it determines that `pFocusWnd` does not contain a pointer to itself.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpaletteischanging"></a>  CWnd::OnPaletteIsChanging  
 The framework calls this member function to inform applications that an application is going to realize its logical palette.  
  
```  
afx_msg OnPaletteIsChanging (CWnd * pRealizeWnd); を無効にします。
```  
  
### Parameters  
 *pRealizeWnd*  
 Specifies the window that is about to realize its logical palette.  
  
### Remarks  
 This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onparentnotify"></a>  CWnd::OnParentNotify  
 A parent's `OnParentNotify` member function is called by the framework when its child window is created or destroyed, or when the user clicks a mouse button while the cursor is over the child window.  
  
```  
afx_msg OnParentNotify (UINT、メッセージを無効にします。  
    LPARAM lParam) です。
```  
  
### Parameters  
 `message`  
 Specifies the event for which the parent is being notified and the identifier of the child window. The event is the low-order word of `message`. If the event is `WM_CREATE` or `WM_DESTROY`, the high-order word of `message` is the identifier of the child window; otherwise, the high-order word is undefined. The event (low-order word of `message`) can be any of these values:  
  
- `WM_CREATE` The child window is being created.  
  
- `WM_DESTROY` The child window is being destroyed.  
  
- `WM_LBUTTONDOWN` The user has placed the mouse cursor over the child window and clicked the left mouse button.  
  
- `WM_MBUTTONDOWN` The user has placed the mouse cursor over the child window and clicked the middle mouse button.  
  
- `WM_RBUTTONDOWN` The user has placed the mouse cursor over the child window and clicked the right mouse button.  
  
 `lParam`  
 If the event (low-order word) of `message` is `WM_CREATE` or `WM_DESTROY`, `lParam` specifies the window handle of the child window; otherwise `lParam` contains the x and y coordinates of the cursor. The x coordinate is in the low-order word and the y coordinate is in the high-order word.  
  
### Remarks  
 When the child window is being created, the system calls `OnParentNotify` just before the [Create](#create) member function that creates the window returns. When the child window is being destroyed, the system calls `OnParentNotify` before any processing takes place to destroy the window.  
  
 `OnParentNotify` is called for all ancestor windows of the child window, including the top-level window.  
  
 All child windows except those that have the [WS_EX_NOPARENTNOTIFY](../../mfc/reference/extended-window-styles.md) style send this message to their parent windows. By default, child windows in a dialog box have the **WS_EX_NOPARENTNOTIFY** style unless the child window was created without this style by calling the [CreateEx](#createex) member function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpowerbroadcast"></a>  CWnd::OnPowerBroadcast  
 The framework calls this member function when a power-management event occurs.  
  
```  
afx_msg UINT OnPowerBroadcast (UINT nPowerEvent、   
    UINT nEventData) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nPowerEvent`|The power-management event.|  
|[in] `nEventData`|Event-specific data.|  
  
### Return Value  
 If the event is a request, return `true` to grant the request, or `BROADCAST_QUERY_DENY` to deny the request.  
  
### Remarks  
 This method receives the [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 The `nPowerEvent` parameter specifies events such as battery power is low, the power status has changed, permission to suspend operation is requested or denied, an operation is resuming automatically after an event, the system is suspending operation, or an operation is resuming after suspension. The `nEventData` parameter is typically not used. For more information, see the `wParam` and `lParam` parameters of the [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onquerydragicon"></a>  CWnd::OnQueryDragIcon  
 The framework calls this member function by a minimized (iconic) window that does not have an icon defined for its class.  
  
```  
afx_msg HCURSOR OnQueryDragIcon() です。
```  
  
### Return Value  
 A doubleword value that contains a cursor or icon handle in the low-order word. The cursor or icon must be compatible with the display driver's resolution. If the application returns **NULL**, the system displays the default cursor. The default return value is **NULL**.  
  
### Remarks  
 The system makes this call to obtain the cursor to display while the user drags the minimized window. If an application returns the handle of an icon or cursor, the system converts it to black-and-white. If an application returns a handle, the handle must identify a monochrome cursor or icon compatible with the display driver's resolution. The application can call the [CWinApp::LoadCursor](../../mfc/reference/cwinapp-class.md#loadcursor) or [CWinApp::LoadIcon](../../mfc/reference/cwinapp-class.md#loadicon) member functions to load a cursor or icon from the resources in its executable file and to obtain this handle.  
  
##  <a name="onqueryendsession"></a>  CWnd::OnQueryEndSession  
 The framework calls this member function when the user chooses to end the Windows session or when an application calls the [ExitWindows](http://msdn.microsoft.com/library/windows/desktop/aa376867) Windows function.  
  
```  
afx_msg BOOL OnQueryEndSession() です。
```  
  
### Return Value  
 Nonzero if an application can be conveniently shut down; otherwise 0.  
  
### Remarks  
 If any application returns 0, the Windows session is not ended. Windows stops calling `OnQueryEndSession` as soon as one application returns 0 and sends the [WM_ENDSESSION](#onendsession) message with a parameter value of **FALSE** for any application that has already returned nonzero.  
  
##  <a name="onquerynewpalette"></a>  CWnd::OnQueryNewPalette  
 The framework calls this member function when the `CWnd` object is about to receive the input focus, giving the `CWnd` an opportunity to realize its logical palette when it receives the focus.  
  
```  
afx_msg BOOL OnQueryNewPalette() です。
```  
  
### Return Value  
 Nonzero if the `CWnd` realizes its logical palette; otherwise 0.  
  
##  <a name="onqueryopen"></a>  CWnd::OnQueryOpen  
 The framework calls this member function when the `CWnd` object is minimized and the user requests that the `CWnd` be restored to its preminimized size and position.  
  
```  
afx_msg BOOL OnQueryOpen() です。
```  
  
### Return Value  
 Nonzero if the icon can be opened, or 0 to prevent the icon from being opened.  
  
### Remarks  
 While in `OnQueryOpen`, `CWnd` should not perform any action that would cause an activation or focus change (for example, creating a dialog box).  
  
##  <a name="onqueryuistate"></a>  CWnd::OnQueryUIState  
 Called to retrieve the user interface (UI) state for a window.  
  
```  
afx_msg UINT OnQueryUIState() です。
```  
  
### Return Value  
 The return value is **NULL** if the focus indicators and the keyboard accelerators are visible. Otherwise, the return value can be one or more of the following values:  
  
- **UISF_HIDEFOCUS** Focus indicators are hidden.  
  
- **UISF_HIDEACCEL** Keyboard accelerators are hidden.  
  
- **UISF_ACTIVE Windows XP:** A control should be drawn in the style used for active controls.  
  
### Remarks  
 This member function emulates the functionality of the [WM_QUERYUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646355) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onrawinput"></a>  CWnd::OnRawInput  
 The framework calls this member function when the current window gets raw input.  
  
```  
afx_msg OnRawInput (UINT nInputCode を無効にします。  
    HRAWINPUT hRawInput) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nInputCode`|Input code that indicates whether the input occurred while the application was in the foreground or not. In either case, the application must call [CWnd::DefWindowProc](#defwindowproc) so the system can perform cleanup.<br /><br /> This parameter can be one of the following values:<br /><br /> - `RIM_INPUT` - Input occurred while the application was in the foreground.<br />- `RIM_INPUTSINK` - Input occurred while the application was not in the foreground.|  
|[in] `hRawInput`|Handle to a [RAWINPUT](http://msdn.microsoft.com/library/windows/desktop/ms645562) structure that contains the raw input from the device.|  
  
### Remarks  
 This method receives the [WM_INPUT](http://msdn.microsoft.com/library/windows/desktop/ms646275) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onrbuttondblclk"></a>  CWnd::OnRButtonDblClk  
 The framework calls this member function when the user double-clicks the right mouse button.  
  
```  
afx_msg 離し (UINT nFlags を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if CTRL key is down.  
  
- **MK_LBUTTON** Set if left mouse button is down.  
  
- **MK_MBUTTON** Set if middle mouse button is down.  
  
- **MK_RBUTTON** Set if right mouse button is down.  
  
- **MK_SHIFT** Set if SHIFT key is down.  
  
 `point`  
 Specifies the x and y coordinates of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 Only windows that have the **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) style can receive `OnRButtonDblClk` calls. This is the default for windows within the Microsoft Foundation Class Library. Windows calls `OnRButtonDblClk` when the user presses, releases, and then again presses the right mouse button within the system's double-click time limit. Double-clicking the right mouse button actually generates four events: [WM_RBUTTONDOWN](#onrbuttondown) and [WM_RBUTTONUP](#onrbuttonup) messages, the `OnRButtonDblClk` call, and another `WM_RBUTTONUP` message when the button is released.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onrbuttondown"></a>  CWnd::OnRButtonDown  
 The framework calls this member function when the user presses the right mouse button.  
  
```  
afx_msg OnRButtonDown (UINT nFlags を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if CTRL key is down.  
  
- **MK_LBUTTON** Set if left mouse button is down.  
  
- **MK_MBUTTON** Set if middle mouse button is down.  
  
- **MK_RBUTTON** Set if right mouse button is down.  
  
- **MK_SHIFT** Set if SHIFT key is down.  
  
 `point`  
 Specifies the x and y coordinates of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onrbuttonup"></a>  CWnd::OnRButtonUp  
 The framework calls this member function when the user releases the right mouse button.  
  
```  
afx_msg OnRButtonUp (UINT nFlags を無効にします。  
    CPoint ポイント)。
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if CTRL key is down.  
  
- **MK_LBUTTON** Set if left mouse button is down.  
  
- **MK_MBUTTON** Set if middle mouse button is down.  
  
- **MK_SHIFT** Set if SHIFT key is down.  
  
 `point`  
 Specifies the x and y coordinates of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onregisteredmousewheel"></a>  CWnd::OnRegisteredMouseWheel  
 The framework calls this member function as a user rotates the mouse wheel and encounters the wheel's next notch.  
  
```  
afx_msg LRESULT OnRegisteredMouseWheel (WPARAM の wParam は、  
    LPARAM lParam) です。
```  
  
### Parameters  
 `wParam`  
 Horizontal position of the pointer.  
  
 `lParam`  
 Vertical position of the pointer.  
  
### Return Value  
 Insignificant at this time. Always zero.  
  
### Remarks  
 Unless overridden, `OnRegisteredMouseWheel` routes the message to the appropriate window (the parent window with focus), and calls the [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617) handler for that window.  
  
 Override this member function to provide your own message routing or to alter the mouse-wheel scrolling behavior.  
  
> [!NOTE]
> `OnRegisteredMouseWheel` handles messages for Windows 95/98 and Windows NT 3.51. For Windows NT 4.0 message handling, use [OnMouseWheel](#onmousewheel).  
  
##  <a name="onrenderallformats"></a>  CWnd::OnRenderAllFormats  
 The Clipboard owner's `OnRenderAllFormats` member function is called by the framework when the owner application is being destroyed.  
  
```  
afx_msg OnRenderAllFormats(); を無効にします。
```  
  
### Remarks  
 The Clipboard owner should render the data in all the formats it is capable of generating and pass a data handle for each format to the Clipboard by calling the [SetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms649051) Windows function. This ensures that the Clipboard contains valid data even though the application that rendered the data is destroyed. The application should call the [OpenClipboard](#openclipboard) member function before calling the [SetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms649051) Windows function and call the [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Windows function afterward.  
  
##  <a name="onrenderformat"></a>  CWnd::OnRenderFormat  
 The Clipboard owner's `OnRenderFormat` member function is called by the framework when a particular format with delayed rendering needs to be rendered.  
  
```  
afx_msg void OnRenderFormat (UINT パラメーター)。
```  
  
### Parameters  
 `nFormat`  
 Specifies the Clipboard format.  
  
### Remarks  
 The receiver should render the data in that format and pass it to the Clipboard by calling the [SetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms649051) Windows function.  
  
 Do not call the `OpenClipboard` member function or the **CloseClipboard** Windows function from within `OnRenderFormat`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsessionchange"></a>  CWnd::OnSessionChange  
 The framework calls this member function to notify an application of a change in session state.  
  
```  
afx_msg OnSessionChange (UINT nSessionState を無効にします。   
    UINT nId) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nSessionState`|A status code describes the session state change.|  
|[in] `nId`|A session identifier.|  
  
### Remarks  
 This method receives the [WM_WTSSESSION_CHANGE](http://msdn.microsoft.com/library/aa383828) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 The `nSessionState` parameter specifies that a session is connected or disconnected from the console or a remote terminal, a user logged on or off, a session is locked or unlocked, or a session has changed to remote-controlled status. For more information, see the `wParam` parameter of the the [WM_WTSSESSION_CHANGE](http://msdn.microsoft.com/library/aa383828) message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsetcursor"></a>  CWnd::OnSetCursor  
 The framework calls this member function if mouse input is not captured and the mouse causes cursor movement within the `CWnd` object.  
  
```  
afx_msg BOOL OnSetCursor (CWnd * 我が物、  
    UINT nHitTest  
    UINT メッセージ)。
```  
  
### Parameters  
 `pWnd`  
 Specifies a pointer to the window that contains the cursor. The pointer may be temporary and should not be stored for later use.  
  
 `nHitTest`  
 Specifies the [hit-test](#onnchittest) area code. The hit test determines the cursor's location.  
  
 `message`  
 Specifies the mouse message number.  
  
### Return Value  
 Nonzero to halt further processing, or 0 to continue.  
  
### Remarks  
 The default implementation calls the parent window's `OnSetCursor` before processing. If the parent window returns **TRUE**, further processing is halted. Calling the parent window gives the parent window control over the cursor's setting in a child window.  
  
 The default implementation sets the cursor to an arrow if it is not in the client area or to the registered-class cursor if it is.  
  
 If `nHitTest` is **HTERROR** and `message` is a mouse button-down message, the **MessageBeep** member function is called.  
  
 The `message` parameter is 0 when `CWnd` enters menu mode.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsetfocus"></a>  CWnd::OnSetFocus  
 The framework calls this member function after gaining the input focus.  
  
```  
afx_msg OnSetFocus (CWnd * pOldWnd); を無効にします。
```  
  
### Parameters  
 *pOldWnd*  
 Contains the `CWnd` object that loses the input focus (may be **NULL**). The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 To display a caret, `CWnd` should call the appropriate caret functions at this point.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsettingchange"></a>  CWnd::OnSettingChange  
 The framework calls `OnSettingChange` for all top-level windows when the Win32 SystemParametersInfo function changes a system-wide setting.  
  
```  
afx_msg OnSettingChange (UINT uFlags を無効にします。  
    LPCTSTR 区別)。
```  
  
### Parameters  
 `uFlags`  
 When the system sends the message as a result of a **SystemParametersInfo** call, this parameter is a flag that indicates the system parameter that was changed. For a list of values, see [SystemParametersInfo](http://msdn.microsoft.com/library/windows/desktop/ms724947) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. When an application sends the message, this parameter must be 0.  
  
 `lpszSection`  
 Points to a string that specifies the name of the section that has changed. (The string does not include the square brackets that enclose the section name.)  
  
### Remarks  
 An application should send the message to all top-level windows when it makes changes to system parameters, and Windows will send the message if the user changes settings via the Control Panel.  
  
 The **ON_WM_SETTINGCHANGE** message is similar to the **ON_WM_WININICHANGE** message, with the following difference:  
  
-   Use **ON_WM_SETTINGCHANGE** when running Windows NT 4.0 or newer, or under Windows 95/98.  
  
-   Use **ON_WININICHANGE** when running Windows NT 3.51 or older. This message is now obsolete.  
  
 You should have only one of these macros in your message map. To write a program that works for both Windows 95/98 and Windows NT 4.0, write a handler for **ON_WM_SETTINGCHANGE**. Under Windows NT 3.51, your handler will be called by `OnSettingChange` and `uFlags` and will always be zero.  
  
##  <a name="onshowwindow"></a>  CWnd::OnShowWindow  
 The framework calls this member function when the `CWnd` object is about to be hidden or shown.  
  
```  
afx_msg OnShowWindow (BOOL bShow を無効にします。  
    UINT 送ら) です。
```  
  
### Parameters  
 `bShow`  
 Specifies whether a window is being shown. It is **TRUE** if the window is being shown; it is **FALSE** if the window is being hidden.  
  
 `nStatus`  
 Specifies the status of the window being shown. It is 0 if the message is sent because of a `ShowWindow` member function call; otherwise `nStatus` is one of the following:  
  
- **SW_PARENTCLOSING** Parent window is closing (being made iconic) or a pop-up window is being hidden.  
  
- **SW_PARENTOPENING** Parent window is opening (being displayed) or a pop-up window is being shown.  
  
### Remarks  
 A window is hidden or shown when the `ShowWindow` member function is called, when an overlapped window is maximized or restored, or when an overlapped or pop-up window is closed (made iconic) or opened (displayed on the screen). When an overlapped window is closed, all pop-up windows associated with that window are hidden.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsize"></a>  CWnd::OnSize  
 The framework calls this member function after the window's size has changed.  
  
```  
afx_msg void OnSize (UINT 形式、  
    int/cx では、  
    int cy) です。
```  
  
### Parameters  
 `nType`  
 Specifies the type of resizing requested. This parameter can be one of the following values:  
  
- **SIZE_MAXIMIZED** Window has been maximized.  
  
- **SIZE_MINIMIZED** Window has been minimized.  
  
- **SIZE_RESTORED** Window has been resized, but neither **SIZE_MINIMIZED** nor **SIZE_MAXIMIZED** applies.  
  
- **SIZE_MAXHIDE** Message is sent to all pop-up windows when some other window is maximized.  
  
- **SIZE_MAXSHOW** Message is sent to all pop-up windows when some other window has been restored to its former size.  
  
 `cx`  
 Specifies the new width of the client area.  
  
 `cy`  
 Specifies the new height of the client area.  
  
### Remarks  
 If the [SetScrollPos](#setscrollpos) or [MoveWindow](#movewindow) member function is called for a child window from `OnSize`, the `bRedraw` parameter of `SetScrollPos` or `MoveWindow` should be nonzero to cause the `CWnd` to be repainted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#109](../../mfc/reference/codesnippet/cpp/cwnd-class_50.cpp)]  
  
##  <a name="onsizeclipboard"></a>  CWnd::OnSizeClipboard  
 The Clipboard owner's `OnSizeClipboard` member function is called by the Clipboard viewer when the Clipboard contains data with the `CF_OWNERDISPLAY` attribute and the size of the client area of the Clipboard-viewer window has changed.  
  
```  
afx_msg 指定 (CWnd * pClipAppWnd を無効にします。  
    HGLOBAL hRect) です。
```  
  
### Parameters  
 `pClipAppWnd`  
 Identifies the Clipboard-application window. The pointer may be temporary and should not be stored.  
  
 *hRect*  
 Identifies a global memory object. The memory object contains a RECT data structure that specifies the area for the Clipboard owner to paint.  
  
### Remarks  
 The `OnSizeClipboard` member function is called with a null rectangle (0,0,0,0) as the new size when the Clipboard application is about to be destroyed or minimized. This permits the Clipboard owner to free its display resources.  
  
 Within `OnSizeClipboard`, an application must use the [GlobalLock](http://msdn.microsoft.com/library/windows/desktop/aa366584) Windows function to lock the memory that contains the RECT data structure. Have the application unlock that memory with the [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows function before it yields or returns control.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsizing"></a>  CWnd::OnSizing  
 The framework calls this member function to indicate that the user is resizing the rectangle.  
  
```  
afx_msg OnSizing (UINT nSide を無効にします。  
    LPRECT lpRect) です。
```  
  
### Parameters  
 `nSide`  
 The edge of window to be moved.  
  
 `lpRect`  
 Address of the [CRect](../../atl-mfc-shared/reference/crect-class.md) or [RECT structure](../../mfc/reference/rect-structure1.md) that will contain the item's coordinates.  
  
### Remarks  
 By processing this message, an application can monitor the size and position of the drag rectangle and, if needed, change its size or position.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#110](../../mfc/reference/codesnippet/cpp/cwnd-class_51.cpp)]  
  
##  <a name="onspoolerstatus"></a>  CWnd::OnSpoolerStatus  
 The framework calls this member function from Print Manager whenever a job is added to or removed from the Print Manager queue.  
  
```  
afx_msg OnSpoolerStatus (UINT 送らを無効にします。  
    UINT nJobs) です。
```  
  
### Parameters  
 `nStatus`  
 Specifies the **SP_JOBSTATUS** flag.  
  
 *nJobs*  
 Specifies the number of jobs remaining in the Print Manager queue.  
  
### Remarks  
 This call is for informational purposes only.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onstylechanged"></a>  CWnd::OnStyleChanged  
 The framework calls this member function after the [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) function has changed one or more of the window's styles.  
  
```  
afx_msg OnStyleChanged (int nStyleType を無効にします。  
    LPSTYLESTRUCT lpStyleStruct) です。
```  
  
### Parameters  
 `nStyleType`  
 Specifies whether the window's extended or nonextended styles have changed. This parameter can be a combination of the following values:  
  
- **GWL_EXSTYLE** The window's extended styles have changed.  
  
- **GWL_STYLE** The window's nonextended styles have changed.  
  
 `lpStyleStruct`  
 Points to a [STYLESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632607) structure that contains the new styles for the window. An application can examine the styles, but it can not change them.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onstylechanging"></a>  CWnd::OnStyleChanging  
 The framework calls this member function when the [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) function is about to change one or more of the window's styles.  
  
```  
afx_msg OnStyleChanging (int nStyleType を無効にします。  
    LPSTYLESTRUCT lpStyleStruct) です。
```  
  
### Parameters  
 `nStyleType`  
 Specifies whether the window's extended or nonextended styles have changed. This parameter can be a combination of the following values:  
  
- **GWL_EXSTYLE** The window's extended styles have changed.  
  
- **GWL_STYLE** The window's nonextended styles have changed.  
  
 `lpStyleStruct`  
 Points to a [STYLESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632607) structure that contains the new styles for the window. An application can examine the styles and change them.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyschar"></a>  CWnd::OnSysChar  
 The framework calls this member function if `CWnd` has the input focus and the [WM_SYSKEYUP](#onsyskeyup) and [WM_SYSKEYDOWN](#onsyskeydown) messages are translated.  
  
```  
afx_msg OnSysChar (UINT nChar を無効にします。  
    UINT nRepCnt  
    UINT nFlags) です。
```  
  
### Parameters  
 `nChar`  
 Specifies the ASCII-character key code of a Control-menu key.  
  
 `nRepCnt`  
 Specifies the repeat count (the number of times the keystroke is repeated as a result of the user holding down the key).  
  
 `nFlags`  
 The `nFlags` parameter can have these values:  
  
|Value|Meaning|  
|-----------|-------------|  
|0-15|Specifies the repeat count. The value is the number of times the keystroke is repeated as a result of the user holding down the key..|  
|16-23|Specifies the scan code. The value depends on the original equipment manufacturer (OEM)|  
|24|Specifies whether the key is an extended key, such as the right-hand ALT and CTRL keys that appear on an enhanced 101- or 102-key keyboard. The value is 1 if it is an extended key; otherwise, it is 0.|  
|25-28|Used internally by Windows.|  
|29|Specifies the context code. The value is 1 if the ALT key is held down while the key is pressed; otherwise, the value is 0.|  
|30|Specifies the previous key state. The value is 1 if the key is down before the message is sent, or it is 0 if the key is up.|  
|31|Specifies the transition state. The value is 1 if the key is being released, or it is 0 if the key is being pressed.|  
  
### Remarks  
 It specifies the virtual key code of the Control-menu key. (For a list of of standard virtual key codes, see Winuser.h)  
  
 When the context code is 0, `WM_SYSCHAR` can pass the [WM_SYSCHAR](http://msdn.microsoft.com/library/windows/desktop/ms646357) message to the [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows function, which will handle it as though it were a normal key message instead of a system character-key. This allows accelerator keys to be used with the active window even if the active window does not have the input focus.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyscolorchange"></a>  CWnd::OnSysColorChange  
 The framework calls this member function for all top-level windows when a change is made in the system color setting.  
  
```  
afx_msg OnSysColorChange(); を無効にします。
```  
  
### Remarks  
 Windows calls `OnSysColorChange` for any window that is affected by a system color change.  
  
 Applications that have brushes that use the existing system colors should delete those brushes and re-create them with the new system colors.  
  
##  <a name="onsyscommand"></a>  CWnd::OnSysCommand  
 The framework calls this member function when the user selects a command from the Control menu, or when the user selects the Maximize or the Minimize button.  
  
```  
afx_msg (UINT では、必ずを無効にします。  
    LPARAM lParam) です。
```  
  
### Parameters  
 `nID`  
 Specifies the type of system command requested. This parameter can be any one of the following values:  
  
- **SC_CLOSE** Close the `CWnd` object.  
  
- **SC_HOTKEY** Activate the `CWnd` object associated with the application-specified hot key. The low-order word of `lParam` identifies the `HWND` of the window to activate.  
  
- **SC_HSCROLL** Scroll horizontally.  
  
- **SC_KEYMENU** Retrieve a menu through a keystroke.  
  
- **SC_MAXIMIZE** (or **SC_ZOOM**)   Maximize the `CWnd` object.  
  
- **SC_MINIMIZE** (or **SC_ICON**)   Minimize the `CWnd` object.  
  
- **SC_MOUSEMENU** Retrieve a menu through a mouse click.  
  
- **SC_MOVE** Move the `CWnd` object.  
  
- **SC_NEXTWINDOW** Move to the next window.  
  
- **SC_PREVWINDOW** Move to the previous window.  
  
- **SC_RESTORE** Restore window to normal position and size.  
  
- **SC_SCREENSAVE** Executes the screen-saver application specified in the [boot] section of the SYSTEM.INI file.  
  
- **SC_SIZE** Size the `CWnd` object.  
  
- **SC_TASKLIST** Execute or activate the Windows Task Manager application.  
  
- **SC_VSCROLL** Scroll vertically.  
  
 `lParam`  
 If a Control-menu command is chosen with the mouse, `lParam` contains the cursor coordinates. The low-order word contains the x coordinate, and the high-order word contains the y coordinate. Otherwise this parameter is not used.  
  
- **SC_HOTKEY** Activate the window associated with the application-specified hot key. The low-order word of `lParam` identifies the window to activate.  
  
- **SC_SCREENSAVE** Execute the screen-save application specified in the Desktop section of Control Panel.  
  
### Remarks  
 By default, `OnSysCommand` carries out the Control-menu request for the predefined actions specified in the preceding table.  
  
 In `WM_SYSCOMMAND` messages, the four low-order bits of the `nID` parameter are used internally by Windows. When an application tests the value of `nID`, it must combine the value 0xFFF0 with the `nID` value by using the bitwise-AND operator to obtain the correct result.  
  
 The menu items in a Control menu can be modified with the `GetSystemMenu`, `AppendMenu`, `InsertMenu`, and `ModifyMenu` member functions. Applications that modify the Control menu must process `WM_SYSCOMMAND` messages, and any `WM_SYSCOMMAND` messages not handled by the application must be passed on to `OnSysCommand`. Any command values added by an application must be processed by the application and cannot be passed to `OnSysCommand`.  
  
 An application can carry out any system command at any time by passing a `WM_SYSCOMMAND` message to `OnSysCommand`.  
  
 Accelerator (shortcut) keystrokes that are defined to select items from the Control menu are translated into `OnSysCommand` calls; all other accelerator keystrokes are translated into [WM_COMMAND](#oncommand) messages.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsysdeadchar"></a>  CWnd::OnSysDeadChar  
 The framework calls this member function if the `CWnd` object has the input focus when the [OnSysKeyUp](#onsyskeyup) or [OnSysKeyDown](#onsyskeydown) member function is called.  
  
```  
afx_msg OnSysDeadChar (UINT nChar を無効にします。  
    UINT nRepCnt  
    UINT nFlags) です。
```  
  
### Parameters  
 `nChar`  
 Specifies the dead-key character value.  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
### Remarks  
 It specifies the character value of a dead key.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyskeydown"></a>  CWnd::OnSysKeyDown  
 If the `CWnd` object has the input focus, the `OnSysKeyDown` member function is called by the framework when the user holds down the ALT key and then presses another key.  
  
```  
afx_msg 持つ (UINT nChar を無効にします。  
    UINT nRepCnt  
    UINT nFlags) です。
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the key being pressed. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed, 0 otherwise).|  
|14|Previous key state (1 if the key is down before the message is sent, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For `OnSysKeyDown` calls, the key-transition bit (bit 15) is 0. The context-code bit (bit 13) is 1 if the ALT key is down while the key is pressed; it is 0 if the message is sent to the active window because no window has the input focus.  
  
### Remarks  
 If no window currently has the input focus, the active window's `OnSysKeyDown` member function is called. The `CWnd` object that receives the message can distinguish between these two contexts by checking the context code in `nFlags`.  
  
 When the context code is 0, the `WM_SYSKEYDOWN` message received by `OnSysKeyDown` can be passed to the [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows function, which will handle it as though it were a normal key message instead of a system-key message. This allows accelerator keys to be used with the active window even if the active window does not have the input focus.  
  
 Because of auto-repeat, more than one `OnSysKeyDown` call may occur before the [WM_SYSKEYUP](#onsyskeyup) message is received. The previous key state (bit 14) can be used to determine whether the `OnSysKeyDown` call indicates the first down transition or a repeated down transition.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyskeyup"></a>  CWnd::OnSysKeyUp  
 If the `CWnd` object has the focus, the `OnSysKeyUp` member function is called by the framework when the user releases a key that was pressed while the ALT key was held down.  
  
```  
afx_msg OnSysKeyUp (UINT nChar を無効にします。  
    UINT nRepCnt  
    UINT nFlags) です。
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the key being pressed. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed, 0 otherwise).|  
|14|Previous key state (1 if the key is down before the message is sent, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For `OnSysKeyUp` calls, the key-transition bit (bit 15) is 1. The context-code bit (bit 13) is 1 if the ALT key is down while the key is pressed; it is 0 if the message is sent to the active window because no window has the input focus.  
  
### Remarks  
 If no window currently has the input focus, the active window's `OnSysKeyUp` member function is called. The `CWnd` object that receives the call can distinguish between these two contexts by checking the context code in `nFlags`.  
  
 When the context code is 0, the `WM_SYSKEYUP` message received by `OnSysKeyUp` can be passed to the [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows function, which will handle it as though it were a normal key message instead of a system-key message. This allows accelerator (shortcut) keys to be used with the active window even if the active window does not have the input focus.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
 For non-U.S. Enhanced 102-key keyboards, the right ALT key is handled as the CTRL+ALT key combination. The following shows the sequence of messages and calls that result when the user presses and releases this key:  
  
|Sequence|Function Accessed|Message Passed|  
|--------------|-----------------------|--------------------|  
|1.|[WM_KEYDOWN](#onkeydown)|**VK_CONTROL**|  
|2.|[WM_KEYDOWN](#onkeydown)|**VK_MENU**|  
|3.|[WM_KEYUP](#onkeyup)|**VK_CONTROL**|  
|4.|[WM_SYSKEYUP](http://msdn.microsoft.com/library/windows/desktop/ms646287)|**VK_MENU**|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ontcard"></a>  CWnd::OnTCard  
 The framework calls this member function when the user clicks an authorable button.  
  
```  
afx_msg OnTCard (UINT idAction を無効にします。  
    DWORD dwActionData) です。
```  
  
### Parameters  
 `idAction`  
 Indicates the action the user has taken. This parameter can be one of these values:  
  
- **IDABORT** The user clicked an authorable Abort button.  
  
- **IDCANCEL** The user clicked an authorable Cancel button.  
  
- **IDCLOSE** The user closed the training card.  
  
- **IDHELP** The user clicked an authorable Windows Help button.  
  
- **IDIGNORE** The user clicked an authorable Ignore button.  
  
- **IDOK** The user clicked an authorable OK button.  
  
- **IDNO** The user clicked an authorable No button.  
  
- **IDRETRY** The user clicked an authorable Retry button.  
  
- **HELP_TCARD_DATA** The user clicked an authorable button. The `dwActionData` parameter contains a long integer specified by the help author.  
  
- **HELP_TCARD_NEXT** The user clicked an authorable Next button.  
  
- **HELP_TCARD_OTHER_CALLER** Another application has requested training cards.  
  
- **IDYES** The user clicked an authorable Yes button.  
  
 `dwActionData`  
 If `idAction` specifies **HELP_TCARD_DATA**, this parameter is a long integer specified by the help author. Otherwise, this parameter is zero.  
  
### Remarks  
 This function is called only when an application has initiated a training card with Windows Help. An application initiates a training card by specifying the **HELP_TCARD** command in a call to the [WinHelp](../../mfc/reference/cwinapp-class.md#winhelp) function.  
  
##  <a name="ontimechange"></a>  CWnd::OnTimeChange  
 The framework calls this member function after the system time is changed.  
  
```  
afx_msg OnTimeChange(); を無効にします。
```  
  
### Remarks  
 Have any application that changes the system time send this message to all top-level windows. To send the `WM_TIMECHANGE` message to all top-level windows, an application can use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function with its *hwnd* parameter set to **HWND_BROADCAST**.  
  
##  <a name="ontimer"></a>  CWnd::OnTimer  
 The framework calls this member function after each interval specified in the [SetTimer](#settimer) member function used to install a timer.  
  
```  
afx_msg OnTimer (UINT_PTR 呼び出した); を無効にします。
```  
  
### Parameters  
 `nIDEvent`  
 Specifies the identifier of the timer.  
  
### Remarks  
 The [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows function sends a [WM_TIMER](http://msdn.microsoft.com/library/windows/desktop/ms644902) message when no other messages are in the application's message queue.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
  See the example in [CWnd::SetTimer](#settimer).  
  
##  <a name="ontoolhittest"></a>  CWnd::OnToolHitTest  
 The framework calls this member function to detemine whether a point is in the bounding rectangle of the specified tool.  
  
```  
仮想 INT_PTR OnToolHitTest (CPoint ポイント、  
    TOOLINFO* pTI) const です。  
```  
  
### Parameters  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window  
  
 `pTI`  
 A pointer to a [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) structure. The following structure values are set by default:  
  
- *hwnd* = `m_hWnd` Handle to a window  
  
- `uId` = **(UINT)hWndChild** Handle to a child window  
  
- `uFlags` &#124;= **TTF_IDISHWND** Handle of the tool  
  
- `lpszText` = **LPSTR_TEXTCALLBACK** Pointer to the string that is to be displayed in the specified window  
  
### Return Value  
 If the tooltip control was found, the window control ID. If the tooltip control was not found, -1.  
  
### Remarks  
 If the point is in the rectangle, it retrieves information about the tool.  
  
 If the area with which the tooltip is associated is not a button, `OnToolHitTest` sets the structure flags to **TTF_NOTBUTTON** and **TTF_CENTERTIP**.  
  
 Override `OnToolHitTest` to provide different information than the default provides.  
  
 See [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256), in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], for more information about the structure.  
  
##  <a name="ontouchinput"></a>  CWnd::OnTouchInput  
 Process single input from Windows touch.  
  
```  
仮想 BOOL OnTouchInput (CPoint pt、  
    int nInputNumber  
    int nInputsCount  
    PTOUCHINPUT pInput) です。
```  
  
### Parameters  
 `pt`  
 Point where screen has been touched (in the client coordinates).  
  
 `nInputNumber`  
 Number of touch input.  
  
 `nInputsCount`  
 Total number of touch inputs.  
  
 `pInput`  
 Pointer to TOUCHINPUT structure.  
  
### Return Value  
 `TRUE` if the application processes Windows touch input; otherwise `FALSE`.  
  
### Remarks  
  
##  <a name="ontouchinputs"></a>  CWnd::OnTouchInputs  
 Processes inputs from Windows touch.  
  
```  
仮想 BOOL OnTouchInputs (UINT nInputsCount、  
    PTOUCHINPUT pInputs) です。
```  
  
### Parameters  
 `nInputsCount`  
 Total number of Windows touch inputs.  
  
 `pInputs`  
 Array of TOUCHINPUT.  
  
### Return Value  
 `TRUE` if application processes Windows touch inputs; otherwise `FALSE`.  
  
### Remarks  
  
##  <a name="onunichar"></a>  CWnd::OnUniChar  
 The framework calls this member function when a key is pressed. That is, the current window has the keyboard focus and a [WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) message is translated by the [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) function.  
  
```  
afx_msg OnUniChar (UINT nChar を無効にします。   
    UINT nRepCnt   
    UINT nFlags) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nChar`|Specifies the character code of the pressed key.|  
|[in] `nRepCnt`|Specifies the repeat count for the current message. The value is the number of times the keystroke is autorepeated as a result of the user holding down the key. If the keystroke is held long enough, multiple messages are sent. However, the repeat count is not cumulative.|  
|[in] `nFlags`|Flags that specify the scan code, extended key, context code, previous key state, and transition state, as shown in the following table:<br /><br /> **0-7:** Specifies the scan code. The value depends on the original equipment manufacturer (OEM).<br /><br /> **8:** Specifies an extended key, such as the right-hand ALT and CTRL keys that appear on an enhanced 101 or 102-key keyboard. The flag is 1 if the key is an extended key; otherwise, it is 0.<br /><br /> **9-12:**  Used internally by Windows.<br /><br /> **13:**  Specifies the context code. The flag is 1 if the ALT key is held down while the key is pressed; otherwise, the value is 0.<br /><br /> **14:**  Specifies the previous key state. The flag is 1 if the key is down before the message is sent, or 0 if the key is up.<br /><br /> **15:**  Specifies the transition state. The flag is 1 if the key is being released, or 0 if the key is being pressed.|  
  
### Remarks  
 This method receives the [WM_UNICHAR](http://msdn.microsoft.com/library/windows/desktop/ms646288) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. The [WM_UNICHAR](http://msdn.microsoft.com/library/windows/desktop/ms646288) message is designed to send or post Unicode characters to ANSI windows. It is equivalent to the [WM_CHAR](http://msdn.microsoft.com/library/windows/desktop/ms646276) message, but uses Unicode Transformation Format-32 encoding (UTF-32), whereas the [WM_CHAR](http://msdn.microsoft.com/library/windows/desktop/ms646276) message uses UTF-16.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onuninitmenupopup"></a>  CWnd::OnUnInitMenuPopup  
 The framework calls this member function when a drop-down menu or submenu has been destroyed.  
  
```  
afx_msg OnUnInitMenuPopup (CMenu * pPopupMenu を無効にします。   
    UINT nFlags) です。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pMenu`|Pointer to the [CMenu](../../mfc/reference/cmenu-class.md) object that represents the menu or submenu.|  
|[in] `nFlags`|The menu that was destroyed. Currently, it can only be the window menu, `MF_SYSMENU`.|  
  
### Remarks  
 This method receives the [WM_UNINITMENUPOPUP](http://msdn.microsoft.com/library/windows/desktop/ms647614) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onupdateuistate"></a>  CWnd::OnUpdateUIState  
 Called to to change the user interface (UI) state for the specified window and all its child windows.  
  
```  
afx_msg OnUpdateUIState (UINT %5%6%7%8 を無効にします。  
    UINT nUIElement) です。
```  
  
### Parameters  
 `nAction`  
 Specifies the action to be performed. Can be one of the following values:  
  
- **UIS_CLEAR** The UI state element (specified by `nUIElement`) should be hidden.  
  
- **UIS_INITIALIZE** The UI state element (specified by `nUIElement`) should be changed based on the last input event. For more information, see the **Remarks** section of [WM_UPDATEISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646361).  
  
- **UIS_SET** The UI state element (specified by `nUIElement`) should be visible.  
  
 `nUIElement`  
 Specifies which UI state elements are affected or the style of the control. Can be one of the following values:  
  
- **UISF_HIDEACCEL** Keyboard accelerators.  
  
- **UISF_HIDEFOCUS** Focus indicators.  
  
- **UISF_ACTIVE Windows XP:** A control should be drawn in the style used for active controls.  
  
### Remarks  
 This member function emulates the functionality of the [WM_UPDATEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646361) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onuserchanged"></a>  CWnd::OnUserChanged  
 The framework calls this member for all windows after the user has logged on or off.  
  
```  
afx_msg OnUserChanged(); を無効にします。
```  
  
### Remarks  
 This method receives the [WM_USERCHANGED](http://msdn.microsoft.com/library/windows/desktop/ms632651) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. When the user logs on or off, the operating system updates user-specific settings. The system sends this message immediately after updating the settings.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onvkeytoitem"></a>  CWnd::OnVKeyToItem  
 If the `CWnd` object owns a list box with the [LBS_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) style, the list box will send the `WM_VKEYTOITEM` message in response to a `WM_KEYDOWN` message.  
  
```  
afx_msg int OnVKeyToItem (UINT nKey、  
    CListBox * pListBox、  
    UINT nIndex) です。
```  
  
### Parameters  
 `nKey`  
 Specifies the virtual key code of the key that the user pressed. For a list of of standard virtual key codes, see Winuser.h  
  
 `pListBox`  
 Specifies a pointer to the list box. The pointer may be temporary and should not be stored for later use.  
  
 `nIndex`  
 Specifies the current caret position.  
  
### Return Value  
 Specifies the action that the application performed in response to the message. A return value of –2 indicates that the application handled all aspects of selecting the item and requires no further action by the list box. A return value of –1 indicates that the list box should perform the default action in response to the keystroke. A return value of 0 or greater specifies the zero-based index of an item in the list box and indicates that the list box should perform the default action for the keystroke on the given item.  
  
### Remarks  
 This member function is called by the framework only for list boxes that have the [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) style.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onvscroll"></a>  CWnd::OnVScroll  
 The framework calls this member function when the user clicks the window's vertical scroll bar.  
  
```  
afx_msg OnVScroll (UINT nSBCode を無効にします。  
    UINT nPos  
    CScrollBar* pScrollBar) です。
```  
  
### Parameters  
 `nSBCode`  
 Specifies a scroll-bar code that indicates the user's scrolling request. This parameter can be one of the following:  
  
- **SB_BOTTOM** Scroll to bottom.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINEDOWN** Scroll one line down.  
  
- **SB_LINEUP** Scroll one line up.  
  
- **SB_PAGEDOWN** Scroll one page down.  
  
- **SB_PAGEUP** Scroll one page up.  
  
- **SB_THUMBPOSITION** Scroll to the absolute position. The current position is provided in `nPos`.  
  
- **SB_THUMBTRACK** Drag scroll box to specified position. The current position is provided in `nPos`.  
  
- **SB_TOP** Scroll to top.  
  
 `nPos`  
 Contains the current scroll-box position if the scroll-bar code is **SB_THUMBPOSITION** or **SB_THUMBTRACK**; otherwise not used. Depending on the initial scroll range, `nPos` may be negative and should be cast to an `int` if necessary.  
  
 `pScrollBar`  
 If the scroll message came from a scroll-bar control, contains a pointer to the control. If the user clicked a window's scroll bar, this parameter is **NULL**. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 `OnVScroll` typically is used by applications that give some feedback while the scroll box is being dragged.  
  
 If `OnVScroll` scrolls the contents of the `CWnd` object, it must also reset the position of the scroll box with the [SetScrollPos](#setscrollpos) member function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onvscrollclipboard"></a>  CWnd::OnVScrollClipboard  
 The Clipboard owner's `OnVScrollClipboard` member function is called by the Clipboard viewer when the Clipboard data has the `CF_OWNERDISPLAY` format and there is an event in the Clipboard viewer's vertical scroll bar.  
  
```  
afx_msg OnVScrollClipboard (CWnd * pClipAppWnd を無効にします。  
    UINT nSBCode  
    UINT nPos) です。
```  
  
### Parameters  
 `pClipAppWnd`  
 Specifies a pointer to a Clipboard-viewer window. The pointer may be temporary and should not be stored for later use.  
  
 `nSBCode`  
 Specifies one of the following scroll-bar values:  
  
- **SB_BOTTOM** Scroll to bottom.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINEDOWN** Scroll one line down.  
  
- **SB_LINEUP** Scroll one line up.  
  
- **SB_PAGEDOWN** Scroll one page down.  
  
- **SB_PAGEUP** Scroll one page up.  
  
- **SB_THUMBPOSITION** Scroll to the absolute position. The current position is provided in `nPos`.  
  
- **SB_TOP** Scroll to top.  
  
 `nPos`  
 Contains the scroll-box position if the scroll-bar code is **SB_THUMBPOSITION**; otherwise `nPos` is not used.  
  
### Remarks  
 The owner should scroll the Clipboard image, invalidate the appropriate section, and update the scroll-bar values.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwindowmaximizedchanged"></a>  CWnd::OnWindowMaximizedChanged  
 The framework calls this member when the current window is maximized, and the window is composed by the Desktop Window Manager (DWM).  
  
```  
afx_msg OnWindowMaximizedChanged (BOOL bIsMaximized); を無効にします。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `bIsMaximized`|`true` if the current window is maximized, and `false` if it is not.|  
  
### Remarks  
 This method receives the [WM_DWMWINDOWMAXIMIZEDCHANGE](http://msdn.microsoft.com/library/windows/desktop/dd388201) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwindowposchanged"></a>  CWnd::OnWindowPosChanged  
 The framework calls this member function when the size, position, or Z-order has changed as a result of a call to the [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) member function or another window-management function.  
  
```  
afx_msg 呼び出さず (WINDOWPOS * lpwndpos); を無効にします。
```  
  
### Parameters  
 `lpwndpos`  
 Points to a [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) data structure that contains information about the window's new size and position.  
  
### Remarks  
 The default implementation sends the [WM_SIZE](http://msdn.microsoft.com/library/windows/desktop/ms632646) and [WM_MOVE](http://msdn.microsoft.com/library/windows/desktop/ms632631) messages to the window. These messages are not sent if an application handles the `OnWindowPosChanged` call without calling its base class. It is more efficient to perform any move or size change processing during the call to `OnWindowPosChanged` without calling its base class.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwindowposchanging"></a>  CWnd::OnWindowPosChanging  
 The framework calls this member function when the size, position, or Z-order is about to change as a result of a call to the [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) member function or another window-management function.  
  
```  
afx_msg OnWindowPosChanging (WINDOWPOS * lpwndpos); を無効にします。
```  
  
### Parameters  
 `lpwndpos`  
 Points to a `WINDOWPOS` data structure that contains information about the window's new size and position.  
  
### Remarks  
 An application can prevent changes to the window by setting or clearing the appropriate bits in the **flags** member of the [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) structure.  
  
 For a window with the [WS_OVERLAPPED](../../mfc/reference/window-styles.md) or [WS_THICKFRAME](../../mfc/reference/window-styles.md) style, the default implementation sends a [WM_GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626) message to the window. This is done to validate the new size and position of the window and to enforce the **CS_BYTEALIGNCLIENT** and **CS_BYTEALIGN** client styles. An application can override this functionality by not calling its base class.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwininichange"></a>  CWnd::OnWinIniChange  
 The framework calls this member function after a change has been made to the Windows initialization file, WIN.INI.  
  
```  
afx_msg OnWinIniChange (LPCTSTR 大文字、小文字); を無効にします。
```  
  
### Parameters  
 `lpszSection`  
 Points to a string that specifies the name of the section that has changed. (The string does not include the square brackets that enclose the section name.)  
  
### Remarks  
 The [SystemParametersInfo](http://msdn.microsoft.com/library/windows/desktop/ms724947) Windows function calls `OnWinIniChange` after an application uses the function to change a setting in the WIN.INI file.  
  
 To send the `WM_WININICHANGE` message to all top-level windows, an application can use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function with its *hwnd* parameter set to **HWND_BROADCAST**.  
  
 If an application changes many different sections in WIN.INI at the same time, the application should send one `WM_WININICHANGE` message with `lpszSection` set to **NULL**. Otherwise, an application should send `WM_WININICHANGE` each time it makes a change to WIN.INI.  
  
 If an application receives an `OnWinIniChange` call with `lpszSection` set to **NULL**, the application should check all sections in WIN.INI that affect the application.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwndmsg"></a>  CWnd::OnWndMsg  
 This member function is called by `WindowProc`, or is called during message reflection.  
  
```  
仮想 BOOL OnWndMsg (UINT メッセージ、  
    WPARAM wParam  
    LPARAM lParam  
    LRESULT* pResult) です。
```  
  
### Parameters  
 `message`  
 Specifies the message to be sent.  
  
 `wParam`  
 Specifies additional message-dependent information.  
  
 `lParam`  
 Specifies additional message-dependent information.  
  
 `pResult`  
 The return value of [WindowProc](#windowproc). Depends on the message; may be **NULL**.  
  
### Return Value  
 **TRUE** if message was handled; otherwise **FALSE**.  
  
### Remarks  
 `OnWndMsg` determines the message type and either calls the appropriate framework function (for example, [OnCommand](#oncommand) for **WM_COMMAND**) or finds the appropriate message in the message map.  
  
 For more information about message reflection, see [Handling Reflected Messages](../../mfc/handling-reflected-messages.md).  
  
##  <a name="onxbuttondblclk"></a>  CWnd::OnXButtonDblClk  
 The framework calls this member function when the user double-clicks XBUTTON1 or XBUTTON2 while the cursor is in the client area of a window.  
  
```  
afx_msg OnXButtonDblClk (UINT nFlags を無効にします。   
    UINT nButton   
    CPoint ポイント)。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button is double-clicked, or `XBUTTON2` if the second X button is double-clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms646244) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. If the mouse is not captured, the message is posted to the window beneath the cursor. Otherwise, the message is posted to the window that has captured the mouse.  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onxbuttondown"></a>  CWnd::OnXButtonDown  
 The framework calls this member function when the user presses XBUTTON1 or XBUTTON2 while the cursor is in the client area of a window.  
  
```  
afx_msg OnXButtonDown (UINT nFlags を無効にします。   
    UINT nButton   
    CPoint ポイント)。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button was clicked, or `XBUTTON2` if the second X button was clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646245) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. If the mouse is not captured, the message is posted to the window beneath the cursor. Otherwise, the message is posted to the window that has captured the mouse.  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onxbuttonup"></a>  CWnd::OnXButtonUp  
 The framework calls this member function when the user releases XBUTTON1 or XBUTTON2 while the cursor is in the client area of a window.  
  
```  
afx_msg OnXButtonUp (UINT nFlags を無効にします。   
    UINT nButton   
    CPoint ポイント)。
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button was double-clicked, or `XBUTTON2` if the second X button was double-clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646246) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. If the mouse is not captured, the message is posted to the window beneath the cursor. Otherwise, the message is posted to the window that has captured the mouse.  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="openclipboard"></a>  CWnd::OpenClipboard  
 Opens the Clipboard.  
  
```  
BOOL OpenClipboard() です。
```  
  
### Return Value  
 Nonzero if the Clipboard is opened via `CWnd`, or 0 if another application or window has the Clipboard open.  
  
### Remarks  
 Other applications will not be able to modify the Clipboard until the [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Windows function is called.  
  
 The current `CWnd` object will not become the owner of the Clipboard until the [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) Windows function is called.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#111](../../mfc/reference/codesnippet/cpp/cwnd-class_52.cpp)]  
  
##  <a name="operator_hwnd"></a>  CWnd::operator HWND  
 Use this operator to get the handle to the `CWnd` object.  
  
```  
演算子 HWND() const です。  
```  
  
##  <a name="operator_neq"></a>  CWnd::operator !=  
 Compares two `CWnd` objects to determine if they do not have the same [m_hWnd](#m_hwnd).  
  
```  
BOOL 演算子! = (const CWnd >/reportbuilder/reportbuilder_3_0_0_0.application wnd) const です。  
```  
  
### Parameters  
 `wnd`  
 A reference to a `CWnd` object.  
  
### Return Value  
 Nonzero if equal; otherwise 0.  
  
##  <a name="operator_eq_eq"></a>  CWnd::operator ==  
 Compares two `CWnd` objects to determine if they have the same [m_hWnd](#m_hwnd).  
  
```  
BOOL 演算子 (const CWnd >/reportbuilder/reportbuilder_3_0_0_0.application wnd) = = const です。  
```  
  
### Parameters  
 `wnd`  
 A reference to a `CWnd` object.  
  
### Return Value  
 Nonzero if equal; otherwise 0.  
  
##  <a name="paintwindowlesscontrols"></a>  CWnd::PaintWindowlessControls  
 Draws windowless controls on the control container.  
  
```  
BOOL PaintWindowlessControls(CDC* pDC) です。
```  
  
### Parameters  
 `pDC`  
 The device context on which to draw the windowless controls.  
  
### Return Value  
 Returns TRUE if there is a control container and the windowless controls are drawn successfully, otherwise FALSE.  
  
##  <a name="postmessage"></a>  CWnd::PostMessage  
 Places a message in the window's message queue and then returns without waiting for the corresponding window to process the message.  
  
```  
BOOL PostMessage (UINT メッセージ、  
    WPARAM wParam = 0、  
    LPARAM lParam = 0) です。
```  
  
### Parameters  
 `message`  
 Specifies the message to be posted.  
  
 `wParam`  
 Specifies additional message information. The content of this parameter depends on the message being posted.  
  
 `lParam`  
 Specifies additional message information. The content of this parameter depends on the message being posted.  
  
### Return Value  
 Nonzero if the message is posted; otherwise 0.  
  
### Remarks  
 Messages in a message queue are retrieved by calls to the [GetMessage](http://msdn.microsoft.com/library/windows/desktop/ms644936) or [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Windows function.  
  
 The Windows [PostMessage](http://msdn.microsoft.com/library/windows/desktop/ms644944) function can be used to access another application.  
  
### Example  
  See the example for [AfxGetMainWnd](../../mfc/reference/application-information-and-management.md#afxgetmainwnd).  
  
##  <a name="postncdestroy"></a>  CWnd::PostNcDestroy  
 Called by the default [OnNcDestroy](#onncdestroy) member function after the window has been destroyed.  
  
```  
仮想 void PostNcDestroy() です。
```  
  
### Remarks  
 Derived classes can use this function for custom cleanup such as the deletion of the **this** pointer.  
  
##  <a name="precreatewindow"></a>  CWnd::PreCreateWindow  
 Called by the framework before the creation of the Windows window attached to this `CWnd` object.  
  
```  
仮想 BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### Parameters  
 *cs*  
 A [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) structure.  
  
### Return Value  
 Nonzero if the window creation should continue; 0 to indicate creation failure.  
  
### Remarks  
  
> [!WARNING]
> `CWnd::PreCreateWindow` now assigns the hMenu member of `cs` to the `this` pointer if the menu is `NULL` and the style contains `WS_CHILD`. For proper functionality, ensure that your dialog control has an ID that is not `NULL`.  
>   
>  This change fixes a crash in managed/native interop scenarios. A `TRACE` statement in `CWnd::Create` alerts the developer of the problem.  
  
 Never call this function directly.  
  
 The default implementation of this function checks for a **NULL** window class name and substitutes an appropriate default. Override this member function to modify the `CREATESTRUCT` structure before the window is created.  
  
 Each class derived from `CWnd` adds its own functionality to its override of `PreCreateWindow`. By design, these derivations of `PreCreateWindow` are not documented. To determine the styles appropriate to each class and the interdependencies between the styles, you can examine the MFC source code for your application's base class. If you choose to override **PreCreateWindow,** you can determine whether the styles used in your application's base class provide the functionality you need by using information gathered from the MFC source code.  
  
 For more information on changing window styles, see the [Changing the Styles of a Window Created by MFC](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#112](../../mfc/reference/codesnippet/cpp/cwnd-class_53.cpp)]  
  
##  <a name="presubclasswindow"></a>  CWnd::PreSubclassWindow  
 This member function is called by the framework to allow other necessary subclassing to occur before the window is subclassed.  
  
```  
仮想 void PreSubclassWindow() です。
```  
  
### Remarks  
 Overriding this member function allows for dynamic subclassing of controls. It is an advanced overridable.  
  
##  <a name="pretranslatemessage"></a>  CWnd::PreTranslateMessage  
 Used by class [CWinApp](../../mfc/reference/cwinapp-class.md) to translate window messages before they are dispatched to the [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) and [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows functions.  
  
```  
仮想 BOOL PreTranslateMessage(MSG* pMsg) です。
```  
  
### Parameters  
 `pMsg`  
 Points to a [MSG](../../mfc/reference/msg-structure1.md) structure that contains the message to process.  
  
### Return Value  
 Nonzero if the message was translated and should not be dispatched; 0 if the message was not translated and should be dispatched.  
  
##  <a name="print"></a>  CWnd::Print  
 Call this member function to draw the current window in the specified device context, which is most commonly in a printer device context.  
  
```  
印刷 (CDC * pDC を無効にします。  
    DWORD dwFlags) const です。  
```  
  
### Parameters  
 `pDC`  
 A pointer to a device context.  
  
 `dwFlags`  
 Specifies the drawing options. This parameter can be one or more of these flags:  
  
- `PRF_CHECKVISIBLE` Draw the window only if it is visible.  
  
- `PRF_CHILDREN` Draw all visible children windows.  
  
- `PRF_CLIENT` Draw the client area of the window.  
  
- `PRF_ERASEBKGND` Erase the background before drawing the window.  
  
- `PRF_NONCLIENT` Draw the nonclient area of the window.  
  
- `PRF_OWNED` Draw all owned windows.  
  
### Remarks  
 [CWnd::DefWindowProc](#defwindowproc) function processes this message based on which drawing option is specified:  
  
-   If `PRF_CHECKVISIBLE` is specified and the window is not visible, do nothing.  
  
-   If `PRF_NONCLIENT` is specified, draw the nonclient area in the given device context.  
  
-   If `PRF_ERASEBKGND` is specified, send the window a [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) message.  
  
-   If `PRF_CLIENT` is specified, send the window a [WM_PRINTCLIENT](http://msdn.microsoft.com/library/windows/desktop/dd145217) message.  
  
-   If `PRF_CHILDREN` is set, send each visible child window a [WM_PRINT](http://msdn.microsoft.com/library/windows/desktop/dd145216) message.  
  
-   If `PRF_OWNED` is set, send each visible owned window a `WM_PRINT` message.  
  
##  <a name="printclient"></a>  CWnd::PrintClient  
 Call this member function to draw any window in the specified device context (usually a printer device context).  
  
```  
void PrintClient (CDC * pDC、  
    DWORD dwFlags) const です。  
```  
  
### Parameters  
 `pDC`  
 A pointer to a device context.  
  
 `dwFlags`  
 Specifies drawing options. This parameter can be one or more of these flags:  
  
- `PRF_CHECKVISIBLE` Draw the window only if it is visible.  
  
- `PRF_CHILDREN` Draw all visible children windows.  
  
- `PRF_CLIENT` Draw the client area of the window.  
  
- `PRF_ERASEBKGND` Erase the background before drawing the window.  
  
- `PRF_NONCLIENT` Draw the nonclient area of the window.  
  
- `PRF_OWNED` Draw all owned windows.  
  
##  <a name="printwindow"></a>  CWnd::PrintWindow  
 Copies a visual window into the specified device context, typically a printer DC.  
  
```  
BOOL PrintWindow (CDC * pDC、  
    UINT nFlags) const です。  
```  
  
### Parameters  
 `pDC`  
 A pointer to the device context to be printed to.  
  
 `nFlags`  
 Specifies the drawing options. For a list of possible values, see [PrintWindow](http://msdn.microsoft.com/library/windows/desktop/dd162869).  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [PrintWindow](http://msdn.microsoft.com/library/windows/desktop/dd162869), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="redrawwindow"></a>  CWnd::RedrawWindow  
 Updates the specified rectangle or region in the given window's client area.  
  
```  
BOOL、(LPCRECT lpRectUpdate = NULL の場合、  
    CRgn * prgnUpdate = NULL の場合、  
    UINT フラグ = RDW_INVALIDATE |RDW_UPDATENOW |RDW_ERASE) です。
```  
  
### Parameters  
 `lpRectUpdate`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) containing the coordinates of the update rectangle. This parameter is ignored if *prgnUpdate* contains a valid region handle.  
  
 *prgnUpdate*  
 Identifies the update region. If both *prgnUpdate* and `lpRectUpdate` are **NULL**, the entire client area is added to the update region.  
  
 `flags`  
 The following flags are used to invalidate the window:  
  
- **RDW_ERASE** Causes the window to receive a [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) message when the window is repainted. The **RDW_INVALIDATE** flag must also be specified; otherwise **RDW_ERASE** has no effect.  
  
- **RDW_FRAME** Causes any part of the nonclient area of the window that intersects the update region to receive a [WM_NCPAINT](http://msdn.microsoft.com/library/windows/desktop/dd145212) message. The **RDW_INVALIDATE** flag must also be specified; otherwise **RDW_FRAME** has no effect.  
  
- **RDW_INTERNALPAINT** Causes a [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message to be posted to the window regardless of whether the window contains an invalid region.  
  
- **RDW_INVALIDATE** Invalidate `lpRectUpdate` or *prgnUpdate* (only one may be not **NULL**). If both are **NULL**, the entire window is invalidated.  
  
 The following flags are used to validate the window:  
  
- **RDW_NOERASE** Suppresses any pending `WM_ERASEBKGND` messages.  
  
- **RDW_NOFRAME** Suppresses any pending `WM_NCPAINT` messages. This flag must be used with **RDW_VALIDATE** and is typically used with **RDW_NOCHILDREN**. This option should be used with care, as it could prevent parts of a window from painting properly.  
  
- **RDW_NOINTERNALPAINT** Suppresses any pending internal `WM_PAINT` messages. This flag does not affect `WM_PAINT` messages resulting from invalid areas.  
  
- **RDW_VALIDATE** Validates `lpRectUpdate` or *prgnUpdate* (only one may be not **NULL**). If both are **NULL**, the entire window is validated. This flag does not affect internal `WM_PAINT` messages.  
  
 The following flags control when repainting occurs. Painting is not performed by the `RedrawWindow` function unless one of these bits is specified.  
  
- **RDW_ERASENOW** Causes the affected windows (as specified by the **RDW_ALLCHILDREN** and **RDW_NOCHILDREN** flags) to receive `WM_NCPAINT` and `WM_ERASEBKGND` messages, if necessary, before the function returns. `WM_PAINT` messages are deferred.  
  
- **RDW_UPDATENOW** Causes the affected windows (as specified by the **RDW_ALLCHILDREN** and **RDW_NOCHILDREN** flags) to receive `WM_NCPAINT`, `WM_ERASEBKGND`, and `WM_PAINT` messages, if necessary, before the function returns.  
  
 By default, the windows affected by the `RedrawWindow` function depend on whether the specified window has the **WS_CLIPCHILDREN** style. The child windows of **WS_CLIPCHILDREN** windows are not affected. However, those windows that are not **WS_CLIPCHILDREN** windows are recursively validated or invalidated until a **WS_CLIPCHILDREN** window is encountered. The following flags control which windows are affected by the `RedrawWindow` function:  
  
- **RDW_ALLCHILDREN** Includes child windows, if any, in the repainting operation.  
  
- **RDW_NOCHILDREN** Excludes child windows, if any, from the repainting operation.  
  
### Return Value  
 Nonzero if the window was redrawn successfully; otherwise 0.  
  
### Remarks  
 When the `RedrawWindow` member function is used to invalidate part of the desktop window, that window does not receive a [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message. To repaint the desktop, an application should use [CWnd::ValidateRgn](#validatergn), [CWnd::InvalidateRgn](#invalidatergn), [CWnd::UpdateWindow](#updatewindow), or [RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911)  
  
##  <a name="reflectchildnotify"></a>  CWnd::ReflectChildNotify  
 This message function is called by the framework from [OnChildNotify](#onchildnotify).  
  
```  
BOOL ReflectChildNotify (UINT メッセージ、  
    WPARAM wParam  
    LPARAM lParam  
    LRESULT* pResult) です。
```  
  
### Parameters  
 `message`  
 Specifies the message to be reflected.  
  
 `wParam`  
 Specifies additional message-dependent information.  
  
 `lParam`  
 Specifies additional message-dependent information.  
  
 `pResult`  
 The result generated by the child window to be returned by the parent window. Can be **NULL**.  
  
### Return Value  
 **TRUE** if message was reflected; otherwise **FALSE**.  
  
### Remarks  
 It is a helper function which reflects `message` to its source.  
  
 Reflected messages are sent directly to [CWnd::OnWndMsg](#onwndmsg) or [CCmdTarget::OnCmdMsg](../../mfc/reference/ccmdtarget-class.md#oncmdmsg).  
  
 For more information about message reflection, see [Handling Reflected Messages](../../mfc/handling-reflected-messages.md).  
  
##  <a name="reflectlastmsg"></a>  CWnd::ReflectLastMsg  
 This member function is called by the framework to reflect the last message to the child window.  
  
```  
静的な BOOL PASCAL ReflectLastMsg (HWND hWndChild、  
    LRESULT* pResult = NULL);
```  
  
### Parameters  
 `hWndChild`  
 A handle to a child window.  
  
 `pResult`  
 The result generated by the child window to be returned by the parent window. Can be **NULL**.  
  
### Return Value  
 Nonzero if the message was handled; otherwise 0.  
  
### Remarks  
 This member function calls [SendChildNotifyLastMsg](#sendchildnotifylastmsg) if the window identified by `hWndChild` is an OLE control or a window in the permanent map.  
  
 For more information about message reflection, see [Handling Reflected Messages](../../mfc/handling-reflected-messages.md).  
  
##  <a name="releasedc"></a>  CWnd::ReleaseDC  
 Releases a device context, freeing it for use by other applications.  
  
```  
int ReleaseDC (CDC * pDC) です。
```  
  
### Parameters  
 `pDC`  
 Identifies the device context to be released.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 The effect of the `ReleaseDC` member function depends on the device-context type.  
  
 The application must call the `ReleaseDC` member function for each call to the [GetWindowDC](#getwindowdc) member function and for each call to the [GetDC](#getdc) member function.  
  
##  <a name="repositionbars"></a>  CWnd::RepositionBars  
 Called to reposition and resize control bars in the client area of a window.  
  
```  
RepositionBars を無効にする (UINT のど、UINT nIDLast UINT nIDLeftOver、UINT 指します reposDefault LPRECT lpRectParam の = = NULL の場合、LPCRECT lpRectClient = NULL の場合、BOOL bStretch = TRUE)。  
```  
  
### Parameters  
 `nIDFirst`  
 The ID of the first in a range of control bars to reposition and resize.  
  
 `nIDLast`  
 The ID of the last in a range of control bars to reposition and resize.  
  
 `nIDLeftOver`  
 Specifies ID of pane that fills the rest of the client area.  
  
 `nFlag`  
 Can have one of the following values:  
  
- **CWnd::reposDefault** Performs the layout of the control bars. `lpRectParam` is not used and can be **NULL**.  
  
- **CWnd::reposQuery** The layout of the control bars is not done; instead `lpRectParam` is initialized with the size of the client area, as if the layout had actually been done.  
  
- **CWnd::reposExtra** Adds the values of `lpRectParam` to the client area of `nIDLast` and also performs the layout *.*  
  
 `lpRectParam`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md); the usage of which depends on the value of `nFlag`.  
  
 *lpRectClient*  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) containing the available client area. If **NULL**, the window's client area will be used.  
  
 `bStretch`  
 Indicates whether the bar should be stretched to the size of the frame.  
  
### Remarks  
 The `nIDFirst` and `nIDLast` parameters define a range of control-bar IDs to be repositioned in the client area. The `nIDLeftOver` parameter specifies the ID of the child window (normally the view) which is repositioned and resized to fill the rest of the client area not filled by control bars.  
  
##  <a name="runmodalloop"></a>  CWnd::RunModalLoop  
 Call this member function to retrieve, translate, or dispatch messages until [ContinueModal](#continuemodal) returns **FALSE**.  
  
```  
int RunModalLoop (DWORD dwFlags = 0) です。
```  
  
### Parameters  
 `dwFlags`  
 Specifies the Windows message to be sent. Can be one of the following values:  
  
- **MLF_NOIDLEMSG** Don't send [WM_ENTERIDLE](http://msdn.microsoft.com/library/windows/desktop/ms645422) messages to the parent.  
  
- **MLF_NOKICKIDLE** Don't send **WM_KICKIDLE** messages to the window.  
  
- **MLF_SHOWONIDLE** Show the window when message queue goes idle.  
  
### Return Value  
 Specifies the value of the `nResult` parameter passed to the [EndModalLoop](#endmodalloop) member function, which is then used to end the modal loop.  
  
### Remarks  
 By default, `ContinueModal` returns **FALSE** after `EndModalLoop` is called. Returns the value provided as `nResult` to `EndModalLoop`.  
  
##  <a name="screentoclient"></a>  CWnd::ScreenToClient  
 Converts the screen coordinates of a given point or rectangle on the display to client coordinates.  
  
```  
void ScreenToClient (LPPOINT lpPoint) const です。 void ScreenToClient (LPRECT lpRect) const です。 ```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoint`  
 指す、 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトまたは[POINT 構造体](../../mfc/reference/point-structure1.md)変換する画面座標を格納しています。  
  
 `lpRect`  
 指す、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)変換する画面座標を格納しています。  
  
### <a name="remarks"></a>コメント  
 `ScreenToClient`メンバー関数で指定した画面座標を置換する`lpPoint`または`lpRect`クライアント座標を使用しています。 新しい座標がの左上隅に対して相対的には、`CWnd`クライアント領域です。  
  
### <a name="example"></a>例  
  例を参照してください[CListCtrl::GetItemRect](../../mfc/reference/clistctrl-class.md#getitemrect)します。  
  
##  <a name="a-namescrollwindowa--cwndscrollwindow"></a><a name="scrollwindow"></a>CWnd::ScrollWindow  
 現在のクライアント領域の内容をスクロール`CWnd`オブジェクトです。  
  
```  
void ScrollWindow(
    int xAmount,  
    int yAmount,  
    LPCRECT lpRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `xAmount`  
 水平方向のスクロールのデバイス単位の量を指定します。 このパラメーターは、左にスクロールする負の値を指定する必要があります。  
  
 `yAmount`  
 垂直方向のスクロールのデバイス単位の量を指定します。 このパラメーターは、上にスクロールする負の値を指定する必要があります。  
  
 `lpRect`  
 指す、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)方向にスクロールするクライアント領域の部分を指定します。 場合`lpRect`は**NULL**、クライアント領域全体をスクロールします。 カーソルの四角形には、スクロールする四角形と交差している場合、カレットの位置を変更します。  
  
 `lpClipRect`  
 指す、`CRect`オブジェクトまたは`RECT`スクロールするクリッピング四角形を指定します。 この四角形の内側のビットだけがスクロールされたとき。 この四角形の外側のビットである場合でも、`lpRect`四角形。 場合`lpClipRect`は**NULL**、スクロール四角形のクリップは実行されません。  
  
### <a name="remarks"></a>コメント  
 カレットの場合、`CWnd`スクロールされる`ScrollWindow`自動的に消去することを防ぐことにキャレットを非表示にされ、スクロールが完了したら、キャレットが復元されます。 キャレット位置が適切に調整します。  
  
 領域が検出された、`ScrollWindow`メンバー関数が再描画されませんが、現在に結合`CWnd`オブジェクトの更新領域です。 アプリケーションで受信が最終的に、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)領域に再描画が必要があることを通知するメッセージ。 スクロール終了と同時にカバーされていない領域を再描画呼び出し、[と](#updatewindow)呼び出し直後後のメンバー関数`ScrollWindow`します。  
  
 場合`lpRect`は**NULL**、 ウィンドウで、子ウィンドウの位置のオフセットで指定した量だけ`xAmount`と`yAmount`、および無効なされていない領域で、`CWnd`のオフセットもします。 `ScrollWindow`高速な場合は、`lpRect`は**NULL**します。  
  
 場合`lpRect`は**NULL**、子ウィンドウの位置は、内の変更、および無効な領域ではない`CWnd`はオフセット排出されません。 防ぐために更新に関する問題と`lpRect`は**NULL**を呼び出す、`UpdateWindow`メンバー関数を再描画を`CWnd`呼び出す前に`ScrollWindow`します。  
  
##  <a name="a-namescrollwindowexa--cwndscrollwindowex"></a><a name="scrollwindowex"></a>CWnd::ScrollWindowEx  
 ウィンドウのクライアント領域の内容をスクロールします。  
  
```  
int ScrollWindowEx(
    int dx,  
    int dy,  
    LPCRECT lpRectScroll,  
    LPCRECT lpRectClip,  
    CRgn* prgnUpdate,  
    LPRECT lpRectUpdate,  
    UINT flags);
```  
  
### <a name="parameters"></a>パラメーター  
 `dx`  
 水平方向のスクロールのデバイス単位の量を指定します。 このパラメーターには、負の値を左にスクロールする必要があります。  
  
 *dy*  
 垂直方向のスクロールのデバイス単位の量を指定します。 このパラメーターには、負の値をスクロールする必要があります。  
  
 `lpRectScroll`  
 指す、 [RECT 構造体](../../mfc/reference/rect-structure1.md)方向にスクロールするクライアント領域の部分を指定します。 このパラメーターは場合**NULL**、クライアント領域全体をスクロールします。  
  
 `lpRectClip`  
 指す、`RECT`スクロールするクリッピング四角形を指定します。 この構造体によって指される四角形よりも優先`lpRectScroll`します。 この四角形の内側のビットだけがスクロールされたとき。 この四角形の外側のビットである場合でも、`lpRectScroll`四角形。 このパラメーターは場合**NULL**、スクロール四角形のクリップは実行されません。  
  
 *prgnUpdate*  
 スクロールすることにより無効となる領域を保持するために、修正される領域を識別します。 このパラメーターがあります**NULL**します。  
  
 `lpRectUpdate`  
 指す、`RECT`をスクロールによって無効にする四角形の境界を受け取る。 このパラメーターがあります**NULL**します。  
  
 `flags`  
 次の値のいずれかを設定できます。  
  
- **SW_ERASE**と共に指定した場合**SW_INVALIDATE**、送信することによって、新しく無効化された領域を消去、 [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055)ウィンドウへのメッセージ。  
  
- **SW_INVALIDATE**で識別される領域を無効に*prgnUpdate*スクロール後します。  
  
- **SW_SCROLLCHILDREN**によって指される四角形の交差するすべての子ウィンドウをスクロール`lpRectScroll`ピクセル単位で指定された数だけ`dx`と*dy*します。 Windows を送り、 [WM_MOVE](http://msdn.microsoft.com/library/windows/desktop/ms632631)交差しているすべての子ウィンドウにメッセージ`lpRectScroll`移動しない場合でも、します。 キャレットの子ウィンドウをスクロールすると、カーソル四角形には、スクロールする四角形が交差する位置を変更します。  
  
### <a name="return-value"></a>戻り値  
 戻り値は**SIMPLEREGION** (四角形の無効化された領域) **COMPLEXREGION** (四角形以外の無効化された領域、四角形を重複している)、または**NULLREGION** (無効化された地域のない)、関数が成功した場合は、それ以外の場合、戻り値は**エラー**します。  
  
### <a name="remarks"></a>コメント  
 この関数は、 [ScrollWindow](http://msdn.microsoft.com/library/windows/desktop/bb787591)関数をその他の機能です。  
  
 場合[SW_INVALIDATE](http://msdn.microsoft.com/library/windows/desktop/bb787593)と[SW_ERASE](http://msdn.microsoft.com/library/windows/desktop/bb787593)が指定されていない、`ScrollWindowEx`メンバー関数に、領域の外にスクロールされても無効にされません。 これらのフラグのいずれかを設定すると場合、`ScrollWindowEx`この領域を無効にします。 領域は、アプリケーションが更新されない、[と](http://msdn.microsoft.com/library/windows/desktop/dd145167)メンバー関数を呼び出して、 [RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911)メンバー関数 (を指定する[RDW_UPDATENOW](http://msdn.microsoft.com/library/windows/desktop/dd162911)または[RDW_ERASENOW](http://msdn.microsoft.com/library/windows/desktop/dd162911))、または取得、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)アプリケーション キューからメッセージをします。  
  
 ウィンドウがある場合、 [WS_CLIPCHILDREN](http://msdn.microsoft.com/library/windows/desktop/ms632679)スタイルで指定された返される部分*prgnUpdate*と`lpRectUpdate`更新する必要があります更新が必要な子ウィンドウにすべての領域を含むスクロールのウィンドウの合計領域を表現します。  
  
 場合、 [SW_SCROLLCHILDREN](http://msdn.microsoft.com/library/windows/desktop/bb787593)フラグを指定すると、Windows が正しく画面が更新されない場合は、子ウィンドウの一部がスクロールされる基準します。 元の四角形の外側にあるスクロールした子ウィンドウの一部は削除されませんし、ない再描画される正しく新しい送信先にします。 使用して、 [DeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632681)を完全に内に配置されていない子ウィンドウを移動する Windows の機能、`lpRectScroll`四角形。 場合、カーソル位置が、 **SW_SCROLLCHILDREN**フラグが設定され、カレット長方形には、スクロールする四角形と交差しています。  
  
 すべての入力呼び出し力の座標 (の`lpRectScroll`、 `lpRectClip`、 `lpRectUpdate`、および*prgnUpdate*) ウィンドウを持つかどうかに関係なく、クライアント座標であると見なされますが、 **CS_OWNDC**または**CS_CLASSDC**クラスのスタイル。 使用して、 [LPtoDP](http://msdn.microsoft.com/library/windows/desktop/dd145042)と[行うには](http://msdn.microsoft.com/library/windows/desktop/dd162474)変換を実行する論理座標から必要に応じて Windows 関数です。  
  
##  <a name="a-namesendchildnotifylastmsga--cwndsendchildnotifylastmsg"></a><a name="sendchildnotifylastmsg"></a>CWnd::SendChildNotifyLastMsg  
 このメンバー関数は、子ウィンドウは、タスクを処理できるようにの親ウィンドウから、子ウィンドウへの通知メッセージを提供するためにフレームワークによって呼び出されます。  
  
```  
BOOL SendChildNotifyLastMsg(LRESULT* pResult = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResult`  
 親ウィンドウによって返される子ウィンドウによって生成された結果です。  
  
### <a name="return-value"></a>戻り値  
 子ウィンドウの親に送信されるメッセージが処理される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `SendChildNotifyLastMsg`リフレクションされたメッセージである場合は、現在のメッセージをソースに送信します。  
  
 メッセージ リフレクションについての詳細については、次を参照してください。[反映されたメッセージの処理](../../mfc/handling-reflected-messages.md)します。  
  
##  <a name="a-namesenddlgitemmessagea--cwndsenddlgitemmessage"></a><a name="senddlgitemmessage"></a>CWnd::SendDlgItemMessage  
 コントロールにメッセージを送信します。  
  
```  
LRESULT SendDlgItemMessage(
    int nID,  
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 メッセージを受信するダイアログ コントロールの識別子を指定します。  
  
 `message`  
 送信するメッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
### <a name="return-value"></a>戻り値  
 コントロールが見つからなかった場合、コントロールのウィンドウ プロシージャ、または 0 が返される値を指定します。  
  
### <a name="remarks"></a>コメント  
 `SendDlgItemMessage`メンバー関数は、メッセージが処理されるまでを返しません。  
  
 使用して`SendDlgItemMessage`を取得するのと同じ、 `CWnd`* 指定されたコントロールと呼び出しを[SendMessage](#sendmessage)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&113;](../../mfc/reference/codesnippet/cpp/cwnd-class_54.cpp)]  
  
##  <a name="a-namesendmessagea--cwndsendmessage"></a><a name="sendmessage"></a>CWnd::SendMessage  
 このウィンドウには、指定したメッセージを送信します。  
  
```  
LRESULT SendMessage(
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 送信するメッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
### <a name="return-value"></a>戻り値  
 メッセージの処理の結果その値は、送信されたメッセージによって異なります。  
  
### <a name="remarks"></a>コメント  
 **SendMessage**メンバー関数はウィンドウ プロシージャを直接呼び出すし、そのウィンドウ プロシージャがメッセージを処理するまで戻りません。 これは、対照的に、 [PostMessage](#postmessage)メンバー関数は、ウィンドウのメッセージ キューにメッセージを直ちに返されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&101;](../../mfc/reference/codesnippet/cpp/cwnd-class_41.cpp)]  
  
##  <a name="a-namesendmessagetodescendantsa--cwndsendmessagetodescendants"></a><a name="sendmessagetodescendants"></a>ハンドラー  
 すべての子孫ウィンドウに指定された Windows メッセージを送信するには、このメンバー関数を呼び出します。  
  
```  
void SendMessageToDescendants(
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0,  
    BOOL bDeep = TRUE,  
    BOOL bOnlyPerm = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 送信するメッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `bDeep`  
 検索するレベルを指定します。 場合**TRUE**、再帰的に場合は、すべての子を検索する**FALSE**、直下の子のみを検索します。  
  
 `bOnlyPerm`  
 一時的なウィンドウで、メッセージが発生するかどうかを指定します。 場合**TRUE**場合、一時的なウィンドウは、メッセージを受信できます**FALSE**、永続的な windows メッセージが表示されるだけです。 一時的なウィンドウの詳細については、次を参照してください。[テクニカル ノート 3:](../../mfc/tn003-mapping-of-windows-handles-to-objects.md)です。  
  
### <a name="remarks"></a>コメント  
 場合`bDeep`は**FALSE**、メッセージは、ウィンドウの直下の子にのみ送信。 それ以外の場合は、メッセージはすべての子孫ウィンドウに送信します。  
  
 場合`bDeep`と`bOnlyPerm`は**TRUE**検索を続行する一時的なウィンドウの下です。 この場合、検索中に発生した永続的な windows のみでは、メッセージが表示されます。 場合`bDeep`は**FALSE**ウィンドウの直下の子にのみ、メッセージを送信します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&114;](../../mfc/reference/codesnippet/cpp/cwnd-class_55.cpp)]  
  
##  <a name="a-namesendnotifymessagea--cwndsendnotifymessage"></a><a name="sendnotifymessage"></a>CWnd::SendNotifyMessage  
 ウィンドウを指定したメッセージを送信します。  
  
```  
BOOL SendNotifyMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 送信するメッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のスレッドがウィンドウを作成した場合`SendNotifyMessage`ウィンドウのウィンドウ プロシージャを呼び出し、ウィンドウ プロシージャがメッセージを処理するまで戻りません。 ウィンドウが別のスレッドによって作成された場合`SendNotifyMessage`ウィンドウ プロシージャにメッセージを渡すし、返しますすぐにそれを待たず、ウィンドウ プロシージャをメッセージの処理を完了します。  
  
##  <a name="a-namesetactivewindowa--cwndsetactivewindow"></a><a name="setactivewindow"></a>CWnd::SetActiveWindow  
 `CWnd`作業中のウィンドウです。  
  
```  
CWnd* SetActiveWindow();
```  
  
### <a name="return-value"></a>戻り値  
 アクティブだったウィンドウです。  
  
 返されたポインターは、一時的なとを後で使用しない格納されている必要があります。  
  
### <a name="remarks"></a>コメント  
 `SetActiveWindow`メンバー関数はアプリケーションのアクティブなウィンドウとの入力フォーカスを任意に有効にすることができるため、注意して使用する必要があります。 通常、Windows は、すべてのアクティブ化の行われます。  
  
##  <a name="a-namesetcapturea--cwndsetcapture"></a><a name="setcapture"></a>CWnd::SetCapture  
 後続のすべてのマウスが現在に送信される入力`CWnd`カーソルの位置に関係なくオブジェクトです。  
  
```  
CWnd* SetCapture();
```  
  
### <a name="return-value"></a>戻り値  
 すべてのマウス入力を既に受信した、ウィンドウ オブジェクトへのポインター。 `NULL`このようなウィンドウがない場合。 返されたポインターは、一時的なとを後で使用しない格納されている必要があります。  
  
### <a name="remarks"></a>コメント  
 `CWnd`必要なくなるとすべてのマウス入力、アプリケーションを呼び出す必要があります、 [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261)関数の他のウィンドウは、マウス入力を受信できるようにします。  
  
 マウス入力をキャプチャ中にない`WM_NCHITTEST`または`WM_SETCURSOR`作業中のウィンドウにメッセージが送信されます。  
  
##  <a name="a-namesetcaretposa--cwndsetcaretpos"></a><a name="setcaretpos"></a>CWnd::SetCaretPos  
 キャレットの位置を設定します。  
  
```  
static void PASCAL SetCaretPos(POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 新しい x と y を指定します (クライアント座標) でのキャレットの座標。  
  
### <a name="remarks"></a>コメント  
 `SetCaretPos`メンバー関数は、現在のタスク ウィンドウによって所有されている場合にのみにキャレットを移動します。 `SetCaretPos`キャレットが非表示かどうかは、キャレットを移動します。  
  
 キャレットは、共有リソースです。 ウィンドウは、キャレットを所有していない場合、キャレットを移動しないでください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&115;](../../mfc/reference/codesnippet/cpp/cwnd-class_56.cpp)]  
  
##  <a name="a-namesetclipboardviewera--cwndsetclipboardviewer"></a><a name="setclipboardviewer"></a>CWnd::SetClipboardViewer  
 メッセージが表示されるウィンドウのチェーンをこのウィンドウに追加 (によって、`WM_DRAWCLIPBOARD`メッセージ)、クリップボードの内容が変更されるたびにします。  
  
```  
HWND SetClipboardViewer();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合、クリップボード ビューアー チェーンで次のウィンドウのハンドル。 アプリケーションはこのハンドルを (メンバー変数とその格納できます) を保存する必要がありますクリップボード ビューアー チェイン メッセージに応答する場合は、それを使用しています。  
  
### <a name="remarks"></a>コメント  
 クリップボード ビューアー チェーンの一部であるウィンドウが対応する必要が[WM_DRAWCLIPBOARD](#ondrawclipboard)、 [WM_CHANGECBCHAIN](#onchangecbchain)、および[WM_DESTROY](#ondestroy)メッセージし、チェーン内の次のウィンドウに、メッセージを渡します。  
  
 このメンバー関数は、`WM_DRAWCLIPBOARD`ウィンドウへのメッセージ。 クリップボード ビューアー チェーンで次のウィンドウを識別するハンドルが返されていないため、アプリケーションを渡さないでください、`WM_DRAWCLIPBOARD`呼び出し中に受信したメッセージ`SetClipboardViewer`します。  
  
 アプリケーションを呼び出す必要がありますクリップボード ビューアー チェーンからには、それ自体を削除するには[ウィンドウ](#changeclipboardchain)メンバー関数。  
  
##  <a name="a-namesetdlgctrlida--cwndsetdlgctrlid"></a><a name="setdlgctrlid"></a>CWnd::SetDlgCtrlID  
 ウィンドウ ID またはウィンドウのコントロール ID を新しい値に設定します。  
  
```  
int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コントロールの識別子に設定する新しい値。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、ウィンドウの以前の識別子それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウには、ダイアログ ボックスの制御だけでなく、任意の子ウィンドウを指定できます。 ウィンドウがトップレベル ウィンドウをすることはできません。  
  
##  <a name="a-namesetdlgiteminta--cwndsetdlgitemint"></a><a name="setdlgitemint"></a>CWnd::SetDlgItemInt  
 指定した整数値の文字列形式にダイアログ ボックスで、特定のコントロールのテキストを設定します。  
  
```  
void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 変更するコントロールの整数 ID を指定します。  
  
 `nValue`  
 項目のテキストを生成するために使用する整数値を指定します。  
  
 `bSigned`  
 整数値が符号付きまたは符号なしかどうかを指定します。 このパラメーターがある場合**TRUE**、`nValue`が署名されています。 このパラメーターは、する場合**TRUE**と`nValue`が 0、マイナス記号は、文字列の最初の桁の前に置か未満です。 このパラメーターは、する場合**FALSE**、`nValue`が署名されていません。  
  
### <a name="remarks"></a>コメント  
 `SetDlgItemInt`送信、[によって](http://msdn.microsoft.com/library/windows/desktop/ms632644)メッセージを指定したコントロールにします。  
  
### <a name="example"></a>例  
  例を参照してください[CWnd::SetDlgItemText](#setdlgitemtext)します。  
  
##  <a name="a-namesetdlgitemtexta--cwndsetdlgitemtext"></a><a name="setdlgitemtext"></a>CWnd::SetDlgItemText  
 キャプションまたはウィンドウまたはダイアログ ボックスが所有するコントロールのテキストを設定します。  
  
```  
void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 テキストを設定するコントロールを識別します。  
  
 `lpszString`  
 指す、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトまたはコントロールにコピーするテキストを表す null で終わる文字列。  
  
### <a name="remarks"></a>コメント  
 `SetDlgItemText`送信、[によって](http://msdn.microsoft.com/library/windows/desktop/ms632644)メッセージを指定したコントロールにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&116; 位](../../mfc/reference/codesnippet/cpp/cwnd-class_57.cpp)]  
  
##  <a name="a-namesetforegroundwindowa--cwndsetforegroundwindow"></a><a name="setforegroundwindow"></a>CWnd::SetForegroundWindow  
 ウィンドウを作成したスレッドをフォアグラウンドに置き、そのウィンドウをアクティブにします。  
  
```  
BOOL SetForegroundWindow();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 キーボード入力は、ウィンドウに送られ、ユーザーのさまざまな視覚的な合図を変更します。 前面のウィンドウとは、使用するユーザーが現在実行されてウィンドウです。 前面のウィンドウは、トップレベル ウィンドウ (フレーム ウィンドウまたはダイアログ ボックス) にのみ適用されます。  
  
### <a name="example"></a>例  
  例を参照してください[:findwindow](#findwindow)します。  
  
##  <a name="a-namesetfocusa--cwndsetfocus"></a><a name="setfocus"></a>:Setfocus  
 入力フォーカスを要求します。  
  
```  
CWnd* SetFocus();
```  
  
### <a name="return-value"></a>戻り値  
 入力フォーカスを持っていたウィンドウ オブジェクトへのポインター。 **NULL**このようなウィンドウがない場合。 返されたポインターでは、一時的な場合があり、保存されません。  
  
### <a name="remarks"></a>コメント  
 入力のフォーカスは、このウィンドウにすべての後続のキーボード入力を指示します。 入力フォーカスを持っていたすべてのウィンドウでは、それが失われます。  
  
 `SetFocus`メンバー関数は、 [WM_KILLFOCUS](http://msdn.microsoft.com/library/windows/desktop/ms646282)が入力フォーカスを失ったウィンドウへのメッセージと[WM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/ms646283)入力フォーカスを受け取るウィンドウへのメッセージ。 また、ウィンドウまたはその親をアクティブになります。  
  
 現在のウィンドウはアクティブですが、フォーカスがないかどうか (つまり、ウィンドウのフォーカスなし)、任意のキーが押されたが、メッセージを生成[wm_syschar です](#onsyschar)、 [WM_SYSKEYDOWN](#onsyskeydown)、または[WM_SYSKEYUP](#onsyskeyup)します。  
  
##  <a name="a-namesetfonta--cwndsetfont"></a><a name="setfont"></a>Cwnd::setfont  
 送信、`WM_SETFONT`ウィンドウにメッセージに指定したフォントを使用します。  
  
```  
void SetFont(
    CFont* pFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 ポインター、`CFont`オブジェクトです。  
  
 `bRedraw`  
 `TRUE`その後すぐに再描画するウィンドウ処理、`WM_SETFONT`メッセージです。 それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドも何も起こりませんウィンドウを処理しない限り、`WM_SETFONT`メッセージです。 多くの MFC クラスから派生した`CWnd`用のメッセージ ハンドラーを含む定義済みのウィンドウ クラスにアタッチされているために、このメッセージの処理、`WM_SETFONT`メッセージです。 このメソッドから派生するクラスを使用して`CWnd`のメソッドのハンドラーを定義する必要があります、`WM_SETFONT`メッセージです。  
  
##  <a name="a-nameseticona--cwndseticon"></a><a name="seticon"></a>CWnd::SetIcon  
 識別されるように、ハンドルを特定のアイコンに設定するには、このメンバー関数を呼び出して`hIcon`します。  
  
```  
HICON SetIcon(
    HICON hIcon,  
    BOOL bBigIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 `hIcon`  
 以前のアイコンへのハンドル。  
  
 `bBigIcon`  
 場合に、32 ピクセルのアイコンで 32 のピクセルを指定**TRUE**; 場合は、16 ピクセルのアイコンで 16 ピクセルを指定**FALSE**します。  
  
### <a name="return-value"></a>戻り値  
 アイコンのハンドル。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ クラスが登録されている場合は、アイコンを選択します。  
  
### <a name="example"></a>例  
  例を参照してください[CWnd::GetSystemMenu](#getsystemmenu)します。  
  
##  <a name="a-namesetlayeredwindowattributesa--cwndsetlayeredwindowattributes"></a><a name="setlayeredwindowattributes"></a>CWnd::SetLayeredWindowAttributes  
 レイヤード ウィンドウの不透明度および透明度のカラー キーを設定します。  
  
```  
BOOL SetLayeredWindowAttributes(
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `crKey`  
 ポインター、 **COLORREF**レイヤード ウィンドウの作成時に使用される透明色キーを指定する値。 この色のウィンドウで描画されたすべてのピクセルは透明になります。 生成する、 **COLORREF**、RGB マクロを使用します。  
  
 `bAlpha`  
 アルファ値がレイヤード ウィンドウの不透明度を記述するために使用します。 詳細については、次を参照してください。、 **SourceConstantAlpha**のメンバー、 [BLENDFUNCTION](http://msdn.microsoft.com/library/windows/desktop/dd183393)構造体。 `bAlpha`が 0 の場合、ウィンドウが完全に透過的です。 `bAlpha` 255 は、ウィンドウは非透過的です。  
  
 `dwFlags`  
 実行するアクションを指定します。 このパラメーターには、次の値の&1; つ以上を指定できます。 使用可能な値の一覧は、次を参照してください。 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)します。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetmenua--cwndsetmenu"></a><a name="setmenu"></a>CWnd::SetMenu  
 指定されたメニューには、現在のメニューを設定します。  
  
```  
BOOL SetMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenu`  
 新しいメニューを識別します。 このパラメーターは場合**NULL**、現在のメニューを削除します。  
  
### <a name="return-value"></a>戻り値  
 メニューが変更された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 によってメニューの変更を反映するように再描画されるウィンドウです。  
  
 `SetMenu`前のメニューは削除されません。 アプリケーションを呼び出す必要があります、[メニューを破棄](../../mfc/reference/cmenu-class.md#destroymenu)メンバー関数は、このタスクを実行します。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::LoadMenu](../../mfc/reference/cmenu-class.md#loadmenu)します。  
  
##  <a name="a-namesetownera--cwndsetowner"></a><a name="setowner"></a>CWnd::SetOwner  
 現在のウィンドウの所有者を指定したウィンドウのオブジェクトに設定します。  
  
```  
void SetOwner(CWnd* pOwnerWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pOwnerWnd*  
 ウィンドウ オブジェクトの新しい所有者を識別します。 このパラメーターは、する場合**NULL**、window オブジェクトに所有者がありません。  
  
### <a name="remarks"></a>コメント  
 この所有者は、現在のウィンドウのオブジェクトからコマンド メッセージを受け取ることができます。 既定では、現在のウィンドウの親は、所有者です。  
  
 ウィンドウの階層構造とは無関係のウィンドウ オブジェクト間の接続を確立すると便利です。 たとえば、 [CToolBar](../../mfc/reference/ctoolbar-class.md)はその親の代わりにその所有者に通知を送信します。 これにより、ツールバー (埋め込み先フレーム ウィンドウに) などの別のウィンドウに通知を送信する (OLE コンテナー アプリケーションのウィンドウ) などの&1; つのウィンドウの子になります。 さらに、server ウィンドウを非アクティブ化またはインプレース中にアクティブ化を編集するフレーム ウィンドウが所有するすべてのウィンドウは非表示または表示します。 次の所有権はへの呼び出しで明示的に設定されて`SetOwner`します。  
  
 この関数の所有権の概念の所有権の概念を異なる[GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms633515)します。  
  
##  <a name="a-namesetparenta--cwndsetparent"></a><a name="setparent"></a>CWnd::SetParent  
 子ウィンドウの親ウィンドウを変更します。  
  
```  
CWnd* SetParent(CWnd* pWndNewParent);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndNewParent*  
 新しい親ウィンドウを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合、以前親ウィンドウ オブジェクトへのポインター。 返されたポインターは、一時的なとを後で使用しない格納されている必要があります。  
  
### <a name="remarks"></a>コメント  
 子ウィンドウが表示されている場合、Windows は、適切な再描画し、再描画を実行します。  
  
##  <a name="a-namesetpropertya--cwndsetproperty"></a><a name="setproperty"></a>CWnd::SetProperty  
 指定された OLE コントロール プロパティを設定するには、このメンバー関数を呼び出す`dwDispID`します。  
  
```  
void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 設定するプロパティを識別します。  
  
 `vtProp`  
 設定するプロパティの型を指定します。 指定できる値の「解説」セクションを参照してください。[について](../../mfc/reference/coledispatchdriver-class.md#invokehelper)します。  
  
 *...*  
 `vtProp`によって指定された型の&1; つのパラメーターです。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  この関数は、上でのみ呼び出す必要があります、 `CWnd` OLE コントロールを表すオブジェクト。  
  
 OLE コントロールのコンテナーでこのメンバー関数の使用に関する詳細については、記事を参照してください。 [ActiveX コントロール コンテナー: ActiveX コントロール コンテナーで ActiveX コントロールのプログラミング](../../mfc/programming-activex-controls-in-a-activex-control-container.md)します。  
  
##  <a name="a-namesetredrawa--cwndsetredraw"></a><a name="setredraw"></a>CWnd::SetRedraw  
 アプリケーションが呼び出す`SetRedraw`を再描画または変更が再描画されるようにする変更を許可するようにします。  
  
```  
void SetRedraw(BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRedraw`  
 再描画フラグの状態を指定します。 場合、このパラメーターは**TRUE**、再描画フラグが設定されている場合は**FALSE**フラグをクリアします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を設定または再描画フラグをクリアします。 再描画フラグをオフにしたときに、内容は変更するたびに更新されませんあり、再描画フラグが設定されるまで再描画されません。 たとえば、アプリケーションをリスト ボックスに複数の項目を追加する必要があるは、再描画フラグをオフに、項目を追加し、再描画フラグを設定します。 最後に、アプリケーションが呼び出すことができます、 [Invalidate](#invalidate)または[InvalidateRect](#invalidaterect)メンバー関数をリスト ボックスに再描画が発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&117;](../../mfc/reference/codesnippet/cpp/cwnd-class_58.cpp)]  
  
##  <a name="a-namesetscrollinfoa--cwndsetscrollinfo"></a><a name="setscrollinfo"></a>CWnd::SetScrollInfo  
 このメンバー関数を呼び出して情報を設定、`SCROLLINFO`スクロール バーの構造を維持します。  
  
```  
BOOL SetScrollInfo(
    int nBar,  
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 スクロール バーが、コントロールまたはウィンドウの非クライアント領域の一部であるかどうかを指定します。 非クライアント領域の一部である場合は、れるによって、水平、垂直にスクロール バーを配置するかどうかまたは両方がも示します。 次のいずれかを指定する必要があります。  
  
- **SB_CTL**スクロール バー コントロールのパラメーターが含まれています。 `m_hWnd`データ メンバーは、スクロール バー コントロールのハンドルである必要があります。  
  
- **SB_HORZ**ウィンドウに水平スクロール バーことを指定します。  
  
- **SB_VERT**ウィンドウに垂直スクロール バーことを指定します。  
  
 `lpScrollInfo`  
 ポインター、 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造体。 参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細については、この構造体。  
  
 `bRedraw`  
 新しい位置を反映するように、スクロール バーを再描画されるかどうかを指定します。 場合`bRedraw`は**TRUE**、スクロール バーが再描画します。 ある場合**FALSE**が再描画されません。 スクロール バーは既定で再描画されます。  
  
### <a name="return-value"></a>戻り値  
 成功すると、戻り値が**TRUE**します。 以外の場合は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造体には、スクロール バーの最小値、最大の位置、ページ サイズおよびスクロール ボックス (つまみ) の位置をスクロールなどに関する情報が含まれています。 参照してください、`SCROLLINFO`構造体のトピックで、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細については、構造体の既定値を変更します。  
  
 MFC のウィンドウ メッセージ ハンドラーをスクロール バーの位置を示す[CWnd::OnHScroll](#onhscroll)と[ために](#onvscroll)、位置データの 16 ビットのみを提供します。 [GetScrollInfo](#getscrollinfo)と`SetScrollInfo`32 ビットのスクロール バーの位置データを提供します。 したがって、アプリケーションが呼び出すことができます`GetScrollInfo`いずれかの処理中に`CWnd::OnHScroll`または`CWnd::OnVScroll`32 ビットのスクロール バーの位置データを取得します。  
  
> [!NOTE]
> [CWnd::GetScrollInfo](#getscrollinfo)アプリケーションを 32 ビットのスクロール バーの位置を使用できます。  
  
##  <a name="a-namesetscrollposa--cwndsetscrollpos"></a><a name="setscrollpos"></a>CWnd::SetScrollPos  
 スクロール ボックスの現在位置を設定し、要求の場合は、スクロール ボックスの新しい位置を反映するようにスクロール バーを再描画します。  
  
```  
int SetScrollPos(
    int nBar,  
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 設定するスクロール バーを指定します。 このパラメーターには、次のいずれかを指定できます。  
  
- **SB_HORZ**ウィンドウの水平スクロール バーのスクロール ボックスの位置を設定します。  
  
- **SB_VERT**ウィンドウの垂直スクロール バーのスクロール ボックスの位置を設定します。  
  
 `nPos`  
 スクロール ボックスの新しい位置を指定します。 スクロールの範囲でなければなりません。  
  
 `bRedraw`  
 スクロール ボックスの新しい位置を反映するように、スクロール バーを再描画するかどうかを指定します。 このパラメーターがある場合**TRUE**、スクロール バーが再描画される; 場合**FALSE**、スクロール バーが再描画されません。  
  
### <a name="return-value"></a>戻り値  
 スクロール ボックスの前の位置。  
  
### <a name="remarks"></a>コメント  
 設定`bRedraw`に**FALSE**スクロール バーを別の関数の後続の呼び出しで再描画される場合に便利です。  
  
##  <a name="a-namesetscrollrangea--cwndsetscrollrange"></a><a name="setscrollrange"></a>CWnd::SetScrollRange  
 指定されたスクロール バーの最小位置と最大位置の値を設定します。  
  
```  
void SetScrollRange(
    int nBar,  
    int nMinPos,  
    int nMaxPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 設定するスクロール バーを指定します。 このパラメーターには、次の値のいずれかを指定できます。  
  
- **SB_HORZ**ウィンドウの水平スクロール バーの範囲を設定します。  
  
- **SB_VERT**ウィンドウの垂直スクロール バーの範囲を設定します。  
  
 `nMinPos`  
 最小のスクロール位置を指定します。  
  
 `nMaxPos`  
 最大のスクロール位置を指定します。  
  
 `bRedraw`  
 変更を反映するように、スクロール バーを再描画されるかどうかを指定します。 場合`bRedraw`は**TRUE**、スクロール バーが再描画される; 場合**FALSE**、スクロール バーが再描画されません。  
  
### <a name="remarks"></a>コメント  
 これは、標準のスクロール バーを表示または非表示に使用できます。  
  
 アプリケーションは、スクロール バーの通知メッセージの処理中に、スクロール バーを非表示にするには、この関数を呼び出さないでください。  
  
 場合への呼び出し`SetScrollRange`への呼び出しの直後に、 [SetScrollPos](#setscrollpos)メンバー関数の場合、`bRedraw`内のパラメーター、`SetScrollPos`メンバー関数が、スクロール バーが 2 回描画されていることを防止する場合は 0 にする必要があります。  
  
 標準のスクロール バーの既定の範囲は、0 ~ 100 です。 スクロール バー コントロールの既定の範囲が空 (両方の`nMinPos`と`nMaxPos`の値は 0)。 指定された値の差`nMinPos`と`nMaxPos`以下である必要があります**INT_MAX**します。  
  
##  <a name="a-namesettimera--cwndsettimer"></a><a name="settimer"></a>で  
 システム タイマーをインストールします。  
  
```  
UINT_PTR SetTimer(
    UINT_PTR nIDEvent,  
    UINT nElapse,  
    void (CALLBACK* lpfnTimer)(HWND,  
    UINT, 
    UINT_PTR, 
    DWORD));
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDEvent`  
 0 以外のタイマーの識別子を指定します。 タイマーの識別子が一意の場合、この同じ値が `SetTimer` によって返されます。 一意でない場合、`SetTimer` は、新しい一意の値を指定して返します。 ウィンドウ タイマー (NULL コールバック関数を持つ) の場合、値は現在のウィンドウに関連付けられている他のウィンドウ タイマーについてのみ一意である必要があります。 コールバックのタイマーの場合、値はすべてのプロセスのすべてのタイマーで一意である必要があります。 したがって、コールバック タイマーを作成すると、戻り値が指定した値と異なる可能性が高くなります。  
  
 `nElapse`  
 タイムアウト値 (間隔) をミリ秒単位で指定します。  
  
 `lpfnTimer`  
 アプリケーションによって提供されるアドレス指定`TimerProc`を処理するコールバック関数、 [WM_TIMER](http://msdn.microsoft.com/library/windows/desktop/ms644902)メッセージです。 このパラメーターが `NULL` の場合、`WM_TIMER` メッセージはアプリケーションのメッセージ キューに登録され、`CWnd` オブジェクトによって処理されます。  
  
### <a name="return-value"></a>戻り値  
 関数が正常に完了した場合の、新しいタイマーのタイマー識別子。 この値は `nIDEvent` パラメーター経由で渡された値と一致する場合も異なる場合もあります。 アプリケーションは、戻り値を常に成功、 [KillTimer](#killtimer)メンバー関数をタイマーを終了します。 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 間隔の値を指定すると、システムは間隔が経過するたびに、インストール アプリケーションのインストール メッセージ キューに `WM_TIMER` メッセージをポストするか、アプリケーション定義された `TimerProc` コールバック関数にメッセージを渡します。  
  
 `lpfnTimer` コールバック関数は `TimerProc` という名前である必要はありませんが、静的として宣言し、次のように定義する必要があります。  
  
```  
void CALLBACK TimerProc(
    HWND hWnd,   // handle of CWnd that called SetTimer  
    UINT nMsg,   // WM_TIMER  
    UINT_PTR nIDEvent,   // timer identification  
    DWORD dwTime    // system time);
```  
  
### <a name="example"></a>例  
 この例では、`CWnd::SetTimer`、`CWnd::OnTimer`、および `CWnd::KillTimer` を使用して、`WM_TIMER` メッセージを処理しています。 最初のタイマーは、`WM_TIMER` で 2 秒ごとにメイン フレーム ウィンドウに `OnStartTimer` メッセージを送信するように設定されます。 `OnTimer` イベント ハンドラーは、メイン フレーム ウィンドウ用に `WM_TIMER` メッセージを処理します。 このメソッドにより、PC スピーカーは 2 秒ごとにビープ音を鳴らします。 2 番目のタイマーは、3.75 秒ごとにコールバック関数にメッセージを送信します。 `OnStopTimer` は、各タイマー ID の `CWnd::KillTimer` を呼び出して、両方のタイマーを停止します。  
  
 [!code-cpp[NVC_MFCWindowing #&118;](../../mfc/reference/codesnippet/cpp/cwnd-class_59.cpp)]  
  
##  <a name="a-namesetwindowcontexthelpida--cwndsetwindowcontexthelpid"></a><a name="setwindowcontexthelpid"></a>CWnd::SetWindowContextHelpId  
 指定したウィンドウにヘルプ コンテキスト id を関連付けるには、このメンバー関数を呼び出します。  
  
```  
BOOL SetWindowContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwContextHelpId`  
 ヘルプ コンテキスト id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 子ウィンドウがヘルプ コンテキスト id を持たない場合、親ウィンドウの識別子を継承します。 同様に、所有されるウィンドウがヘルプ コンテキスト id を持たない場合は、そのオーナー ウィンドウの識別子を継承します。 ヘルプ コンテキスト識別子には、この継承により、ダイアログ ボックスの&1; つの識別子とそのすべてのコントロールを設定するアプリケーションです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&119;](../../mfc/reference/codesnippet/cpp/cwnd-class_60.cpp)]  
  
##  <a name="a-namesetwindowplacementa--cwndsetwindowplacement"></a><a name="setwindowplacement"></a>CWnd::SetWindowPlacement  
 ウィンドウの表示状態、通常の位置 (復元された位置)、最小化された位置、および最大表示された位置を設定します。  
  
```  
BOOL SetWindowPlacement(const WINDOWPLACEMENT* lpwndpl);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpwndpl`  
 指す、 [WINDOWPLACEMENT](../../mfc/reference/windowplacement-structure.md)新しい表示状態と位置を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namesetwindowposa--cwndsetwindowpos"></a><a name="setwindowpos"></a>CWnd::SetWindowPos  
 サイズ、位置、および子、ポップアップ ウィンドウ、および最上位レベルのウィンドウの Z オーダーを変更します。  
  
```  
BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndInsertAfter`  
 識別、`CWnd`は前にあるオブジェクト (よりも多くなる) この`CWnd`Z オーダー内のオブジェクト。 このパラメーターへのポインターを指定できます、`CWnd`または**ポインター**次の値のいずれかにします。  
  
- **wndBottom**ウィンドウを Z オーダーの一番下に置きます。 この場合`CWnd`最上位のウィンドウは、ウィンドウが最上位の状態を失った; システムが他のすべてのウィンドウの下部にあるウィンドウを置きます。  
  
- **wndTop**ウィンドウを Z オーダーの一番上に置きます。  
  
- **wndTopMost**ウィンドウにすべての非最を置きます。 非アクティブ化している場合でも、ウィンドウは最上位の位置を保持します。  
  
- **wndNoTopMost**を最前面以外のすべてのウィンドウの上部にウィンドウの位置を変更 (つまり、すべての最上位のウィンドウの背後にある)。 ウィンドウが最前面以外のウィンドウでは既に場合は、このフラグを指定しても効果はありません。  
  
 このパラメーターを使用する方法に関する規則は、このトピックの「解説」セクションを参照してください。  
  
 *x*  
 新しいウィンドウの左側の位置を指定します。  
  
 *y*  
 ウィンドウの上部の新しい位置を指定します。  
  
 `cx`  
 ウィンドウの新しい幅を指定します。  
  
 `cy`  
 ウィンドウの新しい高さを指定します。  
  
 `nFlags`  
 サイズ指定および配置オプションを指定します。 このパラメーターは、次のフラグの組み合わせを指定できます。  
  
- **SWP_DRAWFRAME**ウィンドウの周囲 (ウィンドウの作成時に定義されている) の枠を描画します。  
  
- **SWP_FRAMECHANGED**送信、`WM_NCCALCSIZE`ウィンドウのサイズが変更されていない場合でも、ウィンドウに表示するメッセージします。 このフラグが指定されていない場合`WM_NCCALCSIZE`ウィンドウのサイズが変更されている場合にのみに送信します。  
  
- **SWP_HIDEWINDOW**ウィンドウを非表示にします。  
  
- `SWP_NOACTIVATE`ウィンドウをアクティブにしません。 このフラグが設定されていない場合、ウィンドウをアクティブ化し、最上位または最前面以外のグループの先頭に移動 (の設定に応じて、`pWndInsertAfter`パラメーター)。  
  
- **SWP_NOCOPYBITS**クライアント領域の内容全体を破棄します。 このフラグが指定されていない場合、クライアント領域の有効な内容が保存され、ウィンドウのサイズや位置を変更した後、クライアント領域にコピーします。  
  
- `SWP_NOMOVE`現在の位置が保持されます (無視、 *x*と*y*パラメーター)。  
  
- **SWP_NOOWNERZORDER** Z オーダーでオーナー ウィンドウの位置は変更されません。  
  
- **SWP_NOREDRAW**の変更が再描画されません。 このフラグが設定されている場合どのような再描画は行われません。 これは、クライアント領域、(タイトルやスクロール バーを含む)、非クライアント領域とウィンドウが移動の結果として検出された親ウィンドウの任意の部分に適用されます。 このフラグが設定されている場合、アプリケーション必要があります明示的に無効にしたりウィンドウと再描画する必要がある親ウィンドウの任意の部分を再描画します。  
  
- **SWP_NOREPOSITION**と同じ**SWP_NOOWNERZORDER**します。  
  
- **SWP_NOSENDCHANGING**受信ウィンドウのことを回避、`WM_WINDOWPOSCHANGING`メッセージです。  
  
- `SWP_NOSIZE`現在のサイズが保持されます (無視、`cx`と`cy`パラメーター)。  
  
- `SWP_NOZORDER`現在の順序が保持されます (無視`pWndInsertAfter`)。  
  
- **SWP_SHOWWINDOW**ウィンドウを表示します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 Windows は、Z オーダーに従って画面に基づいて並べ替えられます順序で他のすべてのウィンドウの上に Z オーダーの一番上に表示されるウィンドウが表示されます。  
  
 子ウィンドウのすべての座標は、(基準とする親ウィンドウのクライアント領域の左上隅) クライアント座標です。  
  
 Z オーダーの一番上にウィンドウを移動できます設定するか、`pWndInsertAfter`パラメーターを**>/documents/report1.rdl」の wndTopMost**ことを確認して、`SWP_NOZORDER`フラグがない設定したりするには、ウィンドウの Z オーダー、既存の最上位ウィンドウを超えていることができるようにします。 最前面以外のウィンドウが行われる最上位と所有されるウィンドウは一番上にあるでも行われます。 その所有者は変更されません。  
  
 最上位ウィンドウが最上位は、一番下に再配置される場合は、不要になった ( **>/documents/report1.rdl」の wndBottom**) の最前面以外のウィンドウの前後の Z オーダー。 最上位ウィンドウが行われる最前面以外とは、最前面以外の windows でも行わすべての所有者に、および所有されるウィンドウれます。  
  
 どちらの場合`SWP_NOACTIVATE`も`SWP_NOZORDER`(つまり、アプリケーションを要求すると、ウィンドウのアクティブ化し指定の Z オーダーで配置される同時に) に指定で指定された値`pWndInsertAfter`は、次の状況でのみ使用します。  
  
-   どちらも**>/documents/report1.rdl」の wndTopMost**も**>/documents/report1.rdl」の wndNoTopMost**で指定された、`pWndInsertAfter`パラメーター。  
  
-   このウィンドウは、作業中のウィンドウではありません。  
  
 アプリケーションも Z オーダーの先頭に先立ち、せず、アクティブでないウィンドウをアクティブにすることはできません。 アプリケーションでは、制限なしのアクティブ化されたウィンドウの Z オーダーを変更できます。  
  
 最前面以外のウィンドウが最上位のウィンドウを所有できますが、その逆は不可能です。 最上位ウィンドウが所有するウィンドウ (たとえば、ダイアログ ボックス) は、windows が、所有者の上に所有されているすべてのことを確認する最上位ウィンドウ自体です。  
  
 Windows 3.1 以降のバージョンで windows Z オーダーの一番上に移動してそこでロックを設定して、 **WS_EX_TOPMOST**スタイル。 このような最上位ウィンドウは、非アクティブになる場合でも、最上位の位置を保持します。 たとえば、WinHelp 常に手前に表示 をクリックして、ヘルプ ウィンドウの一番上にある、およびそのし、アプリケーションに戻るときに表示されたままします。  
  
 最上位ウィンドウを作成するには`SetWindowPos`で、`pWndInsertAfter`パラメーターと等しい**wndTopMost >/documents/report1.rdl」**、または設定、 **WS_EX_TOPMOST**ウィンドウを作成するときのスタイルを設定します。  
  
 Z オーダーでウィンドウをすべてが含まれる場合、 **WS_EX_TOPMOST**スタイル、と一緒に移動ウィンドウ、 **>/documents/report1.rdl」の wndTopMost**の最前面以外のすべてのウィンドウが、最上位の上部にある値が配置されます。 アプリケーションがなく、非アクティブなウィンドウをアクティブに、 **WS_EX_TOPMOST** bit で、ウィンドウは移動最前面以外のすべてのウィンドウの上が、一番上にあります。  
  
 場合`SetWindowPos`時に呼び出される、`pWndInsertAfter`パラメーターは**>/documents/report1.rdl」の wndBottom**と`CWnd`最上位のウィンドウは、ウィンドウが最上位の状態を失った ( **WS_EX_TOPMOST**がオフになって)、し、システムは、Z オーダーの下部にあるウィンドウを置きます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&120;](../../mfc/reference/codesnippet/cpp/cwnd-class_61.cpp)]  
  
##  <a name="a-namesetwindowrgna--cwndsetwindowrgn"></a><a name="setwindowrgn"></a>は  
 ウィンドウの領域を設定するには、このメンバー関数を呼び出します。  
  
```  
int SetWindowRgn(
    HRGN hRgn,  
    BOOL bRedraw);
```  
  
### <a name="parameters"></a>パラメーター  
 `hRgn`  
 領域へのハンドル。  
  
 `bRedraw`  
 場合**TRUE**、オペレーティング システムが、ウィンドウを再描画領域を設定した後、それ以外の場合、そうでないです。 通常、設定`bRedraw`に**TRUE**ウィンドウが表示されている場合。 場合に設定**TRUE**、システムは、送信、`WM_WINDOWPOSCHANGING`と`WM_WINDOWPOSCHANGED`メッセージ ウィンドウにします。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は&0; 以外の値です。 関数が失敗した場合は、0 を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのウィンドウ領域の座標では、ウィンドウのクライアント領域ではなく、ウィンドウの左上隅に対して相対的です。  
  
 呼び出しが成功した後に`SetWindowRgn`、オペレーティング システムを領域ハンドルによって指定された領域を所有している`hRgn`します。 オペレーティング システムが、領域のコピーを作成していない、ので行わないと、さらにこの領域ハンドルを持つ関数呼び出しおよびこの領域ハンドルを閉じないでください。  
  
##  <a name="a-namesetwindowtexta--cwndsetwindowtext"></a><a name="setwindowtext"></a>き  
 指定したテキストをウィンドウのタイトルを設定します。  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszString`  
 指す、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトまたは新しいタイトルまたはコントロールのテキストとして使用する null で終わる文字列。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ コントロールでは、コントロール内のテキストが設定されます。  
  
 この関数により、[によって](http://msdn.microsoft.com/library/windows/desktop/ms632644)メッセージをこのウィンドウに送信します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&121;](../../mfc/reference/codesnippet/cpp/cwnd-class_62.cpp)]  
  
##  <a name="a-nameshowcareta--cwndshowcaret"></a><a name="showcaret"></a>CWnd::ShowCaret  
 カーソルの現在位置の画面で、キャレットを示しています。  
  
```  
void ShowCaret();
```  
  
### <a name="remarks"></a>コメント  
 キャレットは、表示されると自動的に点滅します。  
  
 `ShowCaret`メンバー関数は、現在の図形なりいない非表示にされた&2; つまたは複数回連続してにキャレットをのみを表示します。 このウィンドウは、キャレットを所有していない、カレットは表示されません。  
  
 カレットを非表示は、累積されます。 場合、 [HideCaret](#hidecaret)メンバー関数が呼び出された&5; 回連続して、`ShowCaret`キャレットを表示する&5; 回を呼び出す必要があります。  
  
 キャレットは、共有リソースです。 キャレットは、ウィンドウが入力フォーカスがあるか、または、アクティブな場合のみ表示されます。  
  
### <a name="example"></a>例  
  例を参照してください[CWnd::CreateCaret](#createcaret)します。  
  
##  <a name="a-nameshowownedpopupsa--cwndshowownedpopups"></a><a name="showownedpopups"></a>CWnd::ShowOwnedPopups  
 このウィンドウによって所有されているすべてのポップアップ ウィンドウの表示と非表示を切り替えます。  
  
```  
void ShowOwnedPopups(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bShow`  
 ポップアップ ウィンドウを表示するか非表示になっているかどうかを指定します。 このパラメーターがある場合**TRUE**、すべての非表示のポップアップ ウィンドウが表示されます。 このパラメーターは場合**FALSE**、表示されているすべてのポップアップ ウィンドウは非表示にします。  
  
### <a name="example"></a>例  
  例を参照してください[CWnd::SetWindowPos](#setwindowpos)します。  
  
##  <a name="a-nameshowscrollbara--cwndshowscrollbar"></a><a name="showscrollbar"></a>CWnd::ShowScrollBar  
 スクロール バーの表示と非表示を切り替えます。  
  
```  
void ShowScrollBar(
    UINT nBar,  
    BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 スクロール バーが、コントロールまたはウィンドウの非クライアント領域の一部であるかどうかを指定します。 非クライアント領域の一部である場合`nBar`も水平、垂直にスクロール バーを配置するかどうかまたはその両方を示しています。 次のいずれかを指定する必要があります。  
  
- **SB_BOTH**ウィンドウの水平および垂直方向のスクロール バーを指定します。  
  
- **SB_HORZ**ウィンドウに水平スクロール バーことを指定します。  
  
- **SB_VERT**ウィンドウに垂直スクロール バーことを指定します。  
  
 `bShow`  
 Windows を示していますか、スクロール バーを非表示にするかどうかを指定します。 このパラメーターがある場合**TRUE**、スクロール バーが表示されます。 それ以外の場合、スクロール バーが非表示になっています。  
  
### <a name="remarks"></a>コメント  
 アプリケーションが呼び出さないで`ShowScrollBar`スクロール バーの通知メッセージの処理中に、スクロール バーを非表示にします。  
  
##  <a name="a-nameshowwindowa--cwndshowwindow"></a><a name="showwindow"></a>また  
 ウィンドウの表示/非表示状態を設定します。  
  
```  
BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCmdShow`  
 指定する方法、`CWnd`表示します。 次の値のいずれかを指定する必要があります。  
  
- **SW_HIDE**このウィンドウを非表示にし、別のウィンドウをアクティブ化を渡します。  
  
- **SW_MINIMIZE**ウィンドウを最小化し、システムの一覧の最上位ウィンドウを表示します。  
  
- **SW_RESTORE**にアクティブし、ウィンドウを表示します。 ウィンドウが最小化または最大化されている場合は、Windows に元のサイズと位置を復元します。  
  
- **SW_SHOW**ウィンドウをアクティブにし、現在のサイズと位置に表示されます。  
  
- **SW_SHOWMAXIMIZED**ウィンドウをアクティブにし、最大化されたウィンドウとして表示されます。  
  
- **このメンバーは**ウィンドウをアクティブにし、アイコンとして表示します。  
  
- **SW_SHOWMINNOACTIVE**ウィンドウをアイコンとして表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNA**現在の状態でウィンドウを表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNOACTIVATE**最新サイズと位置でウィンドウを表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNORMAL**にアクティブし、ウィンドウを表示します。 ウィンドウが最小化または最大化されている場合は、Windows に元のサイズと位置を復元します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが表示されていた場合は 0 以外。場合は 0、`CWnd`非表示であった。  
  
### <a name="remarks"></a>コメント  
 `ShowWindow`1 つのアプリケーションがメイン ウィンドウの&1; 回だけ呼び出す必要があります[CWinApp::m_nCmdShow](../../mfc/reference/cwinapp-class.md#m_ncmdshow)します。 後続の呼び出しに対して`ShowWindow`で指定されたものではなく上記の値のいずれかを使用する必要があります`CWinApp::m_nCmdShow`します。  
  
### <a name="example"></a>例  
  例を参照してください[CWnd::CalcWindowRect](#calcwindowrect)します。  
  
##  <a name="a-namesubclassdlgitema--cwndsubclassdlgitem"></a><a name="subclassdlgitem"></a>CWnd::SubclassDlgItem  
 このメンバー関数を呼び出して「動的サブクラス化」するダイアログ テンプレートから作成されたコントロールと、この添付`CWnd`オブジェクトです。  
  
```  
BOOL SubclassDlgItem(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コントロールの id。  
  
 `pParent`  
 コントロールの親 (通常はダイアログ ボックス) です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 Windows メッセージを経由してルーティングは、コントロールが動的にサブクラス化されたとき、`CWnd`のマップをメッセージし、メッセージのハンドラーを呼び出します、`CWnd`クラスが最初にします。 基本クラスに渡されるメッセージは、コントロールの既定のメッセージ ハンドラーに渡されます。  
  
 このメンバー関数は、Windows コントロールをアタッチ、`CWnd`オブジェクトおよびコントロールの置換**WndProc**と**プロシージャ。**関数です。 関数は、古いを格納**WndProc**によって返される場所で、`GetSuperWndProcAddr`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&122;](../../mfc/reference/codesnippet/cpp/cwnd-class_63.cpp)]  
  
##  <a name="a-namesubclasswindowa--cwndsubclasswindow"></a><a name="subclasswindow"></a>CWnd::SubclassWindow  
 このメンバー関数を呼び出して「サブクラスでは動的に」ウィンドウとこれにアタッチ`CWnd`オブジェクトです。  
  
```  
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 ウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウに動的にサブクラス化されたときに、windows メッセージを経由してルーティングは、`CWnd`のマップをメッセージし、メッセージのハンドラーを呼び出します、`CWnd`最初クラスがします。 基本クラスに渡されるメッセージは、ウィンドウの既定のメッセージ ハンドラーに渡されます。  
  
 このメンバー関数は、Windows コントロールをアタッチ、`CWnd`オブジェクトし、ウィンドウ**WndProc**と**プロシージャ。**関数です。 関数は、古いへのポインターを格納**WndProc**で、`CWnd`オブジェクトです。  
  
> [!NOTE]
>  ウィンドウ必要がありますまだするアタッチされていない、MFC オブジェクトにこの関数が呼び出されるとします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#123;](../../mfc/reference/codesnippet/cpp/cwnd-class_64.cpp)]  
  
##  <a name="a-nameunlockwindowupdatea--cwndunlockwindowupdate"></a><a name="unlockwindowupdate"></a>CWnd::UnlockWindowUpdate  
 ロックされているウィンドウのロックを解除するには、このメンバー関数を呼び出す`CWnd::LockWindowUpdate`します。  
  
```  
void UnlockWindowUpdate();
```  
  
### <a name="remarks"></a>コメント  
 使用して、一度に&1; つのウィンドウをロックできる`LockWindowUpdate`です。 参照してください[CWnd::LockWindowUpdate](#lockwindowupdate)または Win32 関数[LockWindowUpdate](http://msdn.microsoft.com/library/windows/desktop/dd145034)ウィンドウのロックの詳細。  
  
##  <a name="a-nameunsubclasswindowa--cwndunsubclasswindow"></a><a name="unsubclasswindow"></a>CWnd::UnsubclassWindow  
 設定するには、このメンバー関数を呼び出す**WndProc**元の値にバックアップし、デタッチによって識別されるウィンドウ`HWND`から、 **CWnd**オブジェクトです。  
  
```  
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>戻り値  
 非サブクラス化されたウィンドウのハンドル。  
  
### <a name="example"></a>例  
  例を参照してください[CWnd::SubclassWindow](#subclasswindow)します。  
  
##  <a name="a-nameupdatedataa--cwndupdatedata"></a><a name="updatedata"></a>:Updatedata  
 このメンバー関数 ダイアログ ボックス内のデータを初期化するためにまたはを呼び出して取得し、ダイアログのデータを確認します。  
  
```  
BOOL UpdateData(BOOL bSaveAndValidate = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bSaveAndValidate`  
 ダイアログ ボックスが初期化されているかどうかを示すフラグ ( **FALSE**) データを取得するか ( **TRUE**)。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。 場合*bSaveAndValidat*e は**TRUE**、し、戻り値が&0; 以外の場合、データの検証が成功します。  
  
### <a name="remarks"></a>コメント  
 フレームワークが自動的に呼び出します`UpdateData`と`bSaveAndValidate`設定**FALSE**の既定の実装で、モーダル ダイアログ ボックスを作成するときに[CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)します。 呼び出しは、ダイアログ ボックスが表示される前に発生します。 既定の実装[CDialog::OnOK](../../mfc/reference/cdialog-class.md#onok)でこのメンバー関数が呼び出さ`bSaveAndValidate`に設定**TRUE**データを取得し、成功した場合に、ダイアログ ボックスを閉じます。 (キャンセル ボタンがダイアログ ボックスでクリックすると、 ダイアログ ボックスが閉じてデータを取得することがなく。)  
  
##  <a name="a-nameupdatedialogcontrolsa--cwndupdatedialogcontrols"></a><a name="updatedialogcontrols"></a>ダイアログ  
 ダイアログ ボックスまたはウィンドウを使用するには、その他のコントロールやダイアログ ボタンの状態を更新するには、このメンバー関数を呼び出す、 [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4)コールバック機構です。  
  
```  
void UpdateDialogControls(
    CCmdTarget* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTarget`  
 アプリケーションのメイン フレーム ウィンドウを参照し、更新メッセージのルーティングに使用される*します。*  
  
 `bDisableIfNoHndler`  
 更新ハンドラーを持たないコントロールが無効として自動的に表示されるかどうかを示すフラグです。  
  
### <a name="remarks"></a>コメント  
 子コントロールには、ハンドラーがない場合、`bDisableIfNoHndler`は**TRUE**、子コントロールは無効になります。  
  
 フレームワークと記述このメンバー関数でダイアログ バーやツールバーのコントロールのアプリケーションの一部としてアイドル処理します。  
  
##  <a name="a-nameupdatelayeredwindowa--cwndupdatelayeredwindow"></a><a name="updatelayeredwindow"></a>CWnd::UpdateLayeredWindow  
 レイヤード ウィンドウの位置、サイズ、形状、内容、および透明度を更新します。  
  
```  
BOOL UpdateLayeredWindow(
    CDC* pDCDst,  
    POINT* pptDst,  
    SIZE* psize,  
    CDC* pDCSrc,  
    POINT* pptSrc,  
    COLORREF crKey,  
    BLENDFUNCTION* pblend,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDCDst`  
 画面のデバイス コンテキストへのポインター。 パレット カラーの一致ウィンドウの内容が更新されたときに使用されます。 場合`pDCDst`は**NULL**既定のパレットが使用されます。  
  
 If `pDCSrc` is **NULL**, `pDCDst` must be **NULL**.  
  
 `pptDst`  
 ポインター、**ポイント**レイヤード ウィンドウの画面上の新しい位置を指定する構造体。 現在の位置を変更しない場合`pptDst`できる**NULL**します。  
  
 *psize*  
 ポインター、**サイズ**レイヤード ウィンドウの新しいサイズを指定する構造体。 ウィンドウのサイズを変更しない場合*psize*できる**NULL**します。  
  
 If `pDCSrc` is **NULL**, *psize* must be **NULL**.  
  
 `pDCSrc`  
 レイヤード ウィンドウを定義する画面の DC へのポインター。 図形と、ウィンドウの表示のコンテキストを変更しない場合`pDCSrc`できる**NULL**します。  
  
 `pptSrc`  
 ポインター、**ポイント**をデバイス コンテキストで、レイヤーの場所を指定します。  
  
 If `pDCSrc` is **NULL**, `pptSrc` should be **NULL**.  
  
 `crKey`  
 ポインター、 **COLORREF**レイヤード ウィンドウの作成時に使用される透明色キーを指定する値。 この色のウィンドウで描画されたすべてのピクセルは透明になります。 生成する、 **COLORREF**、RGB マクロを使用します。  
  
 *pblend*  
 ポインター、 [BLENDFUNCTION](http://msdn.microsoft.com/library/windows/desktop/dd183393)レイヤード ウィンドウの作成時に使用される透明度の値を指定する構造体。  
  
 `dwFlags`  
 実行するアクションを指定します。 このパラメーターには、次の値の&1; つ以上を指定できます。 使用可能な値の一覧は、次を参照してください。 [UpdateLayeredWindow](http://msdn.microsoft.com/library/windows/desktop/ms633556)します。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[UpdateLayeredWindow](http://msdn.microsoft.com/library/windows/desktop/ms633556)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameupdatewindowa--cwndupdatewindow"></a><a name="updatewindow"></a>CWnd::UpdateWindow  
 送信することによってクライアント領域を更新、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージ更新領域が空でない場合。  
  
```  
void UpdateWindow();
```  
  
### <a name="remarks"></a>コメント  
 `UpdateWindow`メンバー関数は、`WM_PAINT`アプリケーション キューをバイパスして、直接メッセージです。 更新領域が空である場合`WM_PAINT`は送信されません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&124;](../../mfc/reference/codesnippet/cpp/cwnd-class_65.cpp)]  
  
##  <a name="a-namevalidaterecta--cwndvalidaterect"></a><a name="validaterect"></a>CWnd::ValidateRect  
 四角形領域から削除して、更新プログラム ウィンドウの指定した四角形内のクライアント領域を検証します。  
  
```  
void ValidateRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)更新領域から削除する四角形のクライアント座標を格納しています。 場合`lpRect`は**NULL**、ウィンドウ全体を検証します。  
  
### <a name="remarks"></a>コメント  
 [BeginPaint](#beginpaint)メンバー関数は、クライアント領域全体を自動的に検証します。 どちらも、`ValidateRect`も[ValidateRgn](#validatergn)更新領域の一部は、前に検証する必要がある場合、メンバー関数を呼び出す必要があります[WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)次が生成されます。  
  
 Windows は引き続きに生成`WM_PAINT`メッセージまで、現在の更新領域を検証します。  
  
##  <a name="a-namevalidatergna--cwndvalidatergn"></a><a name="validatergn"></a>CWnd::ValidateRgn  
 ウィンドウの現在の更新領域から領域を削除することによって指定された領域内のクライアント領域を検証します。  
  
```  
void ValidateRgn(CRgn* pRgn);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 ポインター、 [CRgn](../../mfc/reference/crgn-class.md)更新領域から削除する領域を定義する領域を識別するオブジェクト。 このパラメーターは場合**NULL**、クライアント領域全体を削除します。  
  
### <a name="remarks"></a>コメント  
 指定された領域必要があるされている以前領域関数を使って。 領域の座標は、クライアント座標であると見なされます。  
  
 [BeginPaint](#beginpaint)メンバー関数は、クライアント領域全体を自動的に検証します。 どちらも、 [ValidateRect](#validaterect)も`ValidateRgn`更新領域の一部は、次の前に検証する必要がある場合、メンバー関数を呼び出す必要があります[WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージが生成されます。  
  
##  <a name="a-namewindowfrompointa--cwndwindowfrompoint"></a><a name="windowfrompoint"></a>CWnd::WindowFromPoint  
 指定したポイントを含むウィンドウを取得します。`point`画面上の点の画面座標を指定する必要があります。  
  
```  
static CWnd* PASCAL WindowFromPoint(POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 指定する[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトまたは[ポイント](../../mfc/reference/point-structure1.md)チェックされる位置を定義するデータ構造です。  
  
### <a name="return-value"></a>戻り値  
 ポイントにあるウィンドウ オブジェクトへのポインター。 **NULL**特定の時点でウィンドウが存在しない場合。 返されたポインターは、一時的なとを後で使用しない格納されている必要があります。  
  
### <a name="remarks"></a>コメント  
 `WindowFromPoint`ポイントが、ウィンドウ内にある場合でも、非表示または無効になっているウィンドウを取得しません。 アプリケーションを使用する必要があります、[行いたいとき](#childwindowfrompoint)検索の制限のないメンバー関数。  
  
##  <a name="a-namewindowproca--cwndwindowproc"></a><a name="windowproc"></a>CWnd::WindowProc  
 Windows の手順を示します ( `WindowProc`) の`CWnd`オブジェクトです。  
  
```  
virtual LRESULT WindowProc(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 Windows メッセージを処理するを指定します。  
  
 `wParam`  
 メッセージの処理で使用される追加情報を提供します。 パラメーターの値は、メッセージに依存します。  
  
 `lParam`  
 メッセージの処理で使用される追加情報を提供します。 パラメーターの値は、メッセージに依存します。  
  
### <a name="return-value"></a>戻り値  
 戻り値は、メッセージに依存します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのメッセージ マップを経由してメッセージをディスパッチします。  
  
##  <a name="a-namewinhelpa--cwndwinhelp"></a><a name="winhelp"></a>CWnd::WinHelp  
 WinHelp アプリケーションを起動します。  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwData`  
 追加のデータを指定します。 使用される値の値に応じて異なります、`nCmd`パラメーター。  
  
 `nCmd`  
 要求されるヘルプの種類を指定します。 指定できる値とへの影響の一覧については、`dwData`パラメーターを参照してください、 [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267)で Windows の機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 参照してください[cwinapp::winhelp](../../mfc/reference/cwinapp-class.md#winhelp)の詳細。  
  
##  <a name="a-nameregistertouchwindowa--cwndregistertouchwindow"></a><a name="registertouchwindow"></a>CWnd::RegisterTouchWindow  
 登録するか、Windows タッチ サポートの登録を解除します。  
  
```  
BOOL RegisterTouchWindow(
    BOOL bRegister = TRUE,  
    ULONG ulFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegister`  
 `TRUE`レジスタを示す Windows タッチ サポートします。`FALSE`それ以外の場合。  
  
 `ulFlags`  
 省略可能な変更を指定するビット フラグのセット。 このフィールドは、0 または 1 つの次の値を含めることがあります: TWF_FINETOUCH、TWF_WANTPALM です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameresizedynamiclayouta--cwndresizedynamiclayout"></a><a name="resizedynamiclayout"></a>CWnd::ResizeDynamicLayout  
 ウィンドウで動的レイアウトが有効な場合、子ウィンドウのレイアウトを調整するためにウィンドウのサイズが変更されると、フレームワークによって呼び出されます。  
  
```  
virtual void ResizeDynamicLayout();
```  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)

