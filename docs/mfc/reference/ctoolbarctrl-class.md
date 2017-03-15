---
title: "CToolBarCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class
- Windows common controls [C++], CToolBarCtrl
- toolbar controls [MFC], CToolBarCtrl class
- tool tips [C++], notifications
ms.assetid: 8f2f8ad2-05d7-4975-8715-3f2eed795248
caps.latest.revision: 22
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
ms.openlocfilehash: 2d3ec23d6147299d9a615e9edb0d3f90680bbfac
ms.lasthandoff: 02/24/2017

---
# <a name="ctoolbarctrl-class"></a>CToolBarCtrl クラス
Windows ツール バー コモン コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CToolBarCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CToolBarCtrl::CToolBarCtrl](#ctoolbarctrl)|`CToolBarCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CToolBarCtrl::AddBitmap](#addbitmap)|ツール バー コントロールの使用できるボタン イメージの一覧に&1; つまたは複数のビットマップ ボタンのイメージを追加します。|  
|[CToolBarCtrl::AddButtons](#addbuttons)|ツール バー コントロールを&1; つまたは複数のボタンを追加します。|  
|[CToolBarCtrl::AddString](#addstring)|リソース ID を文字列のツールバーの内部リストとして渡される、新しい文字列を追加します。|  
|[CToolBarCtrl::AddStrings](#addstrings)|新しい文字列または文字列のツールバーの内部リストに、null で終わる文字列のバッファーへのポインターとして渡された文字列を追加します。|  
|[CToolBarCtrl::AutoSize](#autosize)|ツール バー コントロールのサイズを変更します。|  
|[CToolBarCtrl::ChangeBitmap](#changebitmap)|現在のツール バー コントロールのボタンのビットマップを変更します。|  
|[CToolBarCtrl::CheckButton](#checkbutton)|確認またはツール バー コントロールの指定されたボタンをクリアします。|  
|[CToolBarCtrl::CommandToIndex](#commandtoindex)|指定されたコマンド id に関連付けられたボタンの&0; から始まるインデックスを取得します。|  
|[CToolBarCtrl::Create](#create)|ツール バー コントロールを作成し、それをアタッチ、`CToolBarCtrl`オブジェクトです。|  
|[するに](#createex)|指定した Windows 拡張スタイルを使用してツール バー コントロールを作成し、結び付けます、`CToolBarCtrl`オブジェクトです。|  
|[CToolBarCtrl::Customize](#customize)|ツールバーのカスタマイズ ダイアログ ボックスが表示されます。|  
|[CToolBarCtrl::DeleteButton](#deletebutton)|ツール バー コントロールからボタンを削除します。|  
|[CToolBarCtrl::EnableButton](#enablebutton)|有効またはツール バー コントロールの指定したボタンを無効にします。|  
|[CToolBarCtrl::GetAnchorHighlight](#getanchorhighlight)|アンカーの強調表示をツールバーの設定を取得します。|  
|[CToolBarCtrl::GetBitmap](#getbitmap)|ツールバーのボタンに関連付けられているビットマップのインデックスを取得します。|  
|[CToolBarCtrl::GetBitmapFlags](#getbitmapflags)|ツールバーのビットマップに関連付けられているフラグを取得します。|  
|[CToolBarCtrl::GetButton](#getbutton)|ツール バー コントロールの指定したボタンに関する情報を取得します。|  
|[CToolBarCtrl::GetButtonCount](#getbuttoncount)|ツール バー コントロールの現在のボタンの数を取得します。|  
|[CToolBarCtrl::GetButtonInfo](#getbuttoninfo)|ツールバーのボタンの情報を取得します。|  
|[CToolBarCtrl::GetButtonSize](#getbuttonsize)|現在の幅 (ピクセル単位) のツール バー ボタンの高さを取得します。|  
|[CToolBarCtrl::GetColorScheme](#getcolorscheme)|現在のツール バー コントロールの画面の配色を取得します。|  
|[CToolBarCtrl::GetDisabledImageList](#getdisabledimagelist)|ツール バー コントロールはボタンを無効になっている表示を使用しているイメージ一覧を取得します。|  
|[CToolBarCtrl::GetDropTarget](#getdroptarget)|取得、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)ツールバー コントロールのインターフェイスです。|  
|[CToolBarCtrl::GetExtendedStyle](#getextendedstyle)|ツール バー コントロールの拡張スタイルを取得します。|  
|[CToolBarCtrl::GetHotImageList](#gethotimagelist)|「ホット」ボタンを表示するツール バー コントロールを使用しているイメージ一覧を取得します。 マウス ポインターが上が強調表示されているホット ボタンが表示されます。|  
|[CToolBarCtrl::GetHotItem](#gethotitem)|ツールバーのホット アイテムのインデックスを取得します。|  
|[CToolBarCtrl::GetImageList](#getimagelist)|ツール バー コントロールを使用して既定の状態でボタンを表示するイメージ リストを取得します。|  
|[CToolBarCtrl::GetInsertMark](#getinsertmark)|ツールバーの現在の挿入マークを取得します。|  
|[CToolBarCtrl::GetInsertMarkColor](#getinsertmarkcolor)|ツールバーの挿入マークの描画に使用する色を取得します。|  
|[CToolBarCtrl::GetItemRect](#getitemrect)|ツール バー コントロールのボタンの外接する四角形を取得します。|  
|[CToolBarCtrl::GetMaxSize](#getmaxsize)|すべての表示可能なボタンとツールバーの区切り記号の合計サイズを取得します。|  
|[CToolBarCtrl::GetMaxTextRows](#getmaxtextrows)|ツール バー ボタンに表示されるテキスト行の最大数を取得します。|  
|[CToolBarCtrl::GetMetrics](#getmetrics)|ツール バー コントロールのメトリックを取得します。|  
|[CToolBarCtrl::GetPadding](#getpadding)|現在のツール バー コントロールの水平および垂直方向の余白を取得します。|  
|[CToolBarCtrl::GetPressedImageList](#getpressedimagelist)|現在のツール バー コントロールが押された状態でボタンを表すために使用されるイメージのリストを取得します。|  
|[CToolBarCtrl::GetRect](#getrect)|指定されたツール バー ボタンの外接する四角形を取得します。|  
|[CToolBarCtrl::GetRows](#getrows)|現在、ツールバーに表示されるボタンの行の数を取得します。|  
|[CToolBarCtrl::GetState](#getstate)|か有効になっている、押された、またはチェックなどのツール バー コントロールの指定したボタンの状態に関する情報を取得します。|  
|[CToolBarCtrl::GetString](#getstring)|ツールバーの文字列を取得します。|  
|[CToolBarCtrl::GetStyle](#getstyle)|ツール バー コントロールの使用中のスタイルを取得します。|  
|[CToolBarCtrl::GetToolTips](#gettooltips)|ツール バー コントロールに関連付けられている場合は、ツール ヒント コントロールのハンドルを取得します。|  
|[CToolBarCtrl::HideButton](#hidebutton)|ツール バー コントロールの指定ボタンを表示または非表示にします。|  
|[CToolBarCtrl::HitTest](#hittest)|ツール バー コントロールでの点のある場所を決定します。|  
|[CToolBarCtrl::Indeterminate](#indeterminate)|設定またはツール バー コントロールの指定したボタンの中間の状態 (灰色) をクリアします。|  
|[CToolBarCtrl::InsertButton](#insertbutton)|ツール バー コントロールにボタンを挿入します。|  
|[CToolBarCtrl::InsertMarkHitTest](#insertmarkhittest)|ツールバーでのポイントの挿入マーク情報を取得します。|  
|[CToolBarCtrl::IsButtonChecked](#isbuttonchecked)|ツール バー コントロールの指定したボタンがオンになっているかどうかを指示します。|  
|[CToolBarCtrl::IsButtonEnabled](#isbuttonenabled)|ツール バー コントロールの指定したボタンが有効になっているかどうかを指示します。|  
|[CToolBarCtrl::IsButtonHidden](#isbuttonhidden)|ツール バー コントロールの指定したボタンが非表示になっているかどうかを指示します。|  
|[CToolBarCtrl::IsButtonHighlighted](#isbuttonhighlighted)|ツール バー ボタンの強調表示状態を確認します。|  
|[CToolBarCtrl::IsButtonIndeterminate](#isbuttonindeterminate)|ツール バー コントロールの指定したボタンの状態が中間 (灰色) であるかどうかを示します。|  
|[CToolBarCtrl::IsButtonPressed](#isbuttonpressed)|ツール バー コントロールの指定したボタンが押されたかどうかを指示します。|  
|[CToolBarCtrl::LoadImages](#loadimages)|ツール バー コントロールのイメージ リストにビットマップを読み込みます。|  
|[CToolBarCtrl::MapAccelerator](#mapaccelerator)|ツールバーのボタンにアクセラレータ文字をマップします。|  
|[CToolBarCtrl::MarkButton](#markbutton)|ツール バー コントロールの指定したボタンの強調表示状態を設定します。|  
|[CToolBarCtrl::MoveButton](#movebutton)|ボタンを別の&1; つのインデックスに移動します。|  
|[CToolBarCtrl::PressButton](#pressbutton)|押すか、ツール バー コントロールの指定したボタンを解放します。|  
|[CToolBarCtrl::ReplaceBitmap](#replacebitmap)|新しいビットマップでは、現在のツール バー コントロールの既存のビットマップを置き換えます。|  
|[CToolBarCtrl::RestoreState](#restorestate)|ツール バー コントロールの状態に戻します。|  
|[CToolBarCtrl::SaveState](#savestate)|ツール バー コントロールの状態を保存します。|  
|[CToolBarCtrl::SetAnchorHighlight](#setanchorhighlight)|アンカーの強調表示をツールバーの設定を設定します。|  
|[CToolBarCtrl::SetBitmapSize](#setbitmapsize)|ツール バー コントロールに追加するビットマップ イメージのサイズを設定します。|  
|[CToolBarCtrl::SetButtonInfo](#setbuttoninfo)|ツールバーでは、既存のボタンの情報を設定します。|  
|[CToolBarCtrl::SetButtonSize](#setbuttonsize)|ツール バー コントロールを追加するボタンのサイズを設定します。|  
|[CToolBarCtrl::SetButtonStructSize](#setbuttonstructsize)|サイズを指定、`TBBUTTON`構造体。|  
|[CToolBarCtrl::SetButtonWidth](#setbuttonwidth)|ツール バー コントロールの最小値と最大のボタンの幅を設定します。|  
|[CToolBarCtrl::SetCmdID](#setcmdid)|指定したボタンが押されると、オーナー ウィンドウに送信するコマンドの識別子を設定します。|  
|[CToolBarCtrl::SetColorScheme](#setcolorscheme)|現在のツール バー コントロールの画面の配色を設定します。|  
|[CToolBarCtrl::SetDisabledImageList](#setdisabledimagelist)|ツール バー コントロールを使用するイメージ リストをボタンの表示を無効に設定します。|  
|[CToolBarCtrl::SetDrawTextFlags](#setdrawtextflags)|Win32 関数でフラグを設定[DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498)、これは、フラグを設定する方法に従って書式設定された指定の四角形内のテキストの描画に使用します。|  
|[CToolBarCtrl::SetExtendedStyle](#setextendedstyle)|ツール バー コントロールの拡張スタイルを設定します。|  
|[CToolBarCtrl::SetHotImageList](#sethotimagelist)|「ホット」ボタンを表示するツール バー コントロールを使用するイメージのリストを設定します。|  
|[CToolBarCtrl::SetHotItem](#sethotitem)|ツールバーのホット アイテムを設定します。|  
|[CToolBarCtrl::SetImageList](#setimagelist)|既定の状態にあるボタンを表示するツールバーを使用するイメージのリストを設定します。|  
|[CToolBarCtrl::SetIndent](#setindent)|ツール バー コントロールの最初のボタンでインデントを設定します。|  
|[CToolBarCtrl::SetInsertMark](#setinsertmark)|ツールバーの現在の挿入マークを設定します。|  
|[CToolBarCtrl::SetInsertMarkColor](#setinsertmarkcolor)|ツールバーの挿入マークの描画に使用する色を設定します。|  
|[CToolBarCtrl::SetMaxTextRows](#setmaxtextrows)|ツール バー ボタンに表示されるテキスト行の最大数を設定します。|  
|[CToolBarCtrl::SetMetrics](#setmetrics)|ツール バー コントロールのメトリックを設定します。|  
|[CToolBarCtrl::SetOwner](#setowner)|ツール バー コントロールから通知メッセージを受信するウィンドウを設定します。|  
|[CToolBarCtrl::SetPadding](#setpadding)|現在のツール バー コントロールの水平および垂直方向の余白を設定します。|  
|[CToolBarCtrl::SetPressedImageList](#setpressedimagelist)|現在のツール バー コントロールが押された状態でボタンを表すために使用されるイメージのリストを設定します。|  
|[CToolBarCtrl::SetRows](#setrows)|ツールバーに表示されるボタンの行の数を設定します。|  
|[CToolBarCtrl::SetState](#setstate)|ツール バー コントロールの指定したボタンの状態を設定します。|  
|[CToolBarCtrl::SetStyle](#setstyle)|ツール バー コントロールのスタイルを設定します。|  
|[CToolBarCtrl::SetToolTips](#settooltips)|Toolbar コントロールのツール ヒント コントロールを関連付けます。|  
|[CToolBarCtrl::SetWindowTheme](#setwindowtheme)|ツール バー コントロールの視覚スタイルを設定します。|  
  
## <a name="remarks"></a>コメント  
 このコントロール (つまり、`CToolBarCtrl`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。  
  
 Windows のツール バー コモン コントロールは、1 つまたは複数のボタンのある四角形の子ウィンドウです。 これらのボタンには、ビットマップ、文字列、またはその両方を表示できます。 ボタンを選択すると、ツールバーのオーナー ウィンドウにコマンドのメッセージを送信します。 ツールバーのボタン、通常、アプリケーションのメニュー内の項目に対応します。ユーザーがアプリケーションのコマンドにアクセスするための直接的な手段になります。  
  
 `CToolBarCtrl`オブジェクトにいくつかの重要な内部データ構造を含める: ボタン画像のビットマップの一覧やイメージ リスト、ボタン ラベルの文字列のリストの一覧`TBBUTTON`イメージを関連付けるか、またはスタイルの位置の文字列の構造は、状態、およびコマンド ボタンの ID。 各データ構造体の要素は&0; から始まるインデックスで呼ばれます。 使用する前に、`CToolBarCtrl`オブジェクトに、これらのデータ構造を設定する必要があります。 文字列のリストは、ボタンのラベルに対してのみ使用できます。ツールバーから文字列を取得することはできません。  
  
 使用する、`CToolBarCtrl`オブジェクトは通常これらの手順を行います。  
  
1.  構築、`CToolBarCtrl`オブジェクトです。  
  
2.  呼び出す[作成](#create)Windows ツール バー コモン コントロールを作成しをアタッチする、`CToolBarCtrl`オブジェクトです。 などのスタイルを使用して、ツールバーのスタイルを示す**バーオブジェクト**透明なツールバーのまたは**TBSTYLE_DROPDOWN**ドロップダウン スタイルのボタンをサポートするツールバーです。  
  
3.  ツールバーのボタンを表示する方法を識別します。  
  
    -   ボタンのビットマップ イメージを使用してを呼び出して、ツールバーにボタンのビットマップを追加します。[表示](#addbitmap)します。  
  
    -   ボタンのイメージの一覧から表示される画像を使用するには、呼び出すことによって、イメージのリストを指定[SetImageList](#setimagelist)、 [SetHotImageList](#sethotimagelist)、または[SetDisabledImageList](#setdisabledimagelist)します。  
  
    -   文字列のラベルをボタンの使用を呼び出して、ツールバーに、文字列を追加します。 [AddString](#addstring)や[AddStrings](#addstrings)します。  
  
4.  呼び出して、ツールバーにボタンの構造を追加[AddButtons](#addbuttons)します。  
  
5.  オーナー ウィンドウがない場合、ツール バー ボタンのツール ヒントを表示する場合、 `CFrameWnd`、処理する必要があります、 **TTN_NEEDTEXT**ツールバーのオーナー ウィンドウにメッセージが表示」の説明に従って[ツール ヒントの通知の処理](../../mfc/handling-tool-tip-notifications.md)します。 ツールバーの親ウィンドウがから派生している`CFrameWnd`、ツール ヒントに表示されるから余分な作業なし`CFrameWnd`既定ハンドラーを提供します。  
  
6.  ツールバーをカスタマイズすることができるようにする場合は、」の説明に従って、オーナー ウィンドウのカスタマイズの通知メッセージを処理[カスタマイズ通知の処理](../../mfc/handling-customization-notifications.md)します。  
  
 使用する[SaveState](#savestate)ツール バー コントロールの現在の状態をレジストリに保存して[RestoreState](#restorestate)レジストリに格納されていた情報に基づいて状態を復元します。 アプリケーションへのツールバーの状態を保存するだけでなくアプリケーションでは、ユーザーは、ユーザーが後でがツールバーを元の状態に復元する場合に、ツールバーのカスタマイズを開始する前に、状態が通常格納されます。  
  
## <a name="support-for-internet-explorer-version-40-and-later"></a>Internet Explorer のバージョン 4.0 以降のサポート  
 Internet Explorer 4.0 以降のバージョンで導入された機能をサポートするためには、MFC は、ツール バー コントロールのイメージ リストのサポートおよび透過的でフラット スタイルを提供します。  
  
 透明なツールバーで、クライアント、ツールバーの下を表示できます。 透明なツールバーを作成するには、両方を使用**TBSTYLE_FLAT**と**バーオブジェクト**スタイル。 透明なツールバー機能のホット トラッキングです。つまり、ツールバーのホット ボタンにマウス ポインターを移動、ボタンの外観が変わります。 作成したツールバーだけ**TBSTYLE_FLAT**スタイルには、透明ではないボタンにが含まれます。  
  
 イメージ リストのサポートは、既定の動作、ホット イメージ、および無効なイメージのより柔軟に制御を使用します。 使用[GetImageList](#getimagelist)、 [GetHotImageList](#gethotimagelist)、および[GetDisabledImageList](#getdisabledimagelist)の状態に従ってイメージを操作する透過的なツールバーを使用します。  
  
 使用する方法について`CToolBarCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CToolBarCtrl](../../mfc/using-ctoolbarctrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolBarCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="a-nameaddbitmapa--ctoolbarctrladdbitmap"></a><a name="addbitmap"></a>CToolBarCtrl::AddBitmap  
 ツール バー コントロールに格納されているボタンのイメージの一覧に&1; つまたは複数のボタンのイメージを追加します。  
  
```  
int AddBitmap(
    int nNumButtons,  
    UINT nBitmapID);

 
int AddBitmap(
    int nNumButtons,  
    CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNumButtons`  
 ビットマップでボタンのイメージの数。  
  
 `nBitmapID`  
 ボタン イメージを追加するイメージを含むビットマップのリソース識別子。  
  
 `pBitmap`  
 ポインター、`CBitmap`ボタン イメージを追加するイメージを格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、最初の新しいイメージの 0 から始まるインデックスそれ以外の場合 – 1 です。  
  
### <a name="remarks"></a>コメント  
 Windows API を使用して[CreateMappedBitmap](http://msdn.microsoft.com/library/windows/desktop/bb787467)にビットマップをツールバーに追加する前に色をマップします。 ポインターを渡す場合、 **CBitMap**オブジェクト、ツールバーを破棄した後、ビットマップがするまで破棄されないことを確認する必要があります。  
  
##  <a name="a-nameaddbuttonsa--ctoolbarctrladdbuttons"></a><a name="addbuttons"></a>CToolBarCtrl::AddButtons  
 ツール バー コントロールを&1; つまたは複数のボタンを追加します。  
  
```  
BOOL AddButtons(
    int nNumButtons,  
    LPTBBUTTON lpButtons);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNumButtons`  
 追加するボタンの数。  
  
 `lpButtons`  
 配列のアドレス`TBBUTTON`を追加するボタンに関する情報を格納する構造体。 指定されたボタンと同じ配列の要素数がある`nNumButtons`です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 `lpButtons`ポインターの配列を指して`TBBUTTON`構造体。 各`TBBUTTON`構造体には、ボタンのスタイル、イメージや文字列、コマンド ID の状態、およびユーザー定義データを追加するボタンが関連付けられます。  
  
 `typedef struct _TBBUTTON {`  
  
 `int iBitmap;// zero-based index of button image`  
  
 `int idCommand;  // command to be sent when button pressed`  
  
 `BYTE fsState;   // button state--see below`  
  
 `BYTE fsStyle;   // button style--see below`  
  
 `DWORD dwData;   // application-defined value`  
  
 `int iString;// zero-based index of button label string`  
  
 `} TBBUTTON;`  
  
 メンバーは次のとおりです。  
  
 **iBitmap**  
 ボタンのイメージは、このボタンのイメージの&0; から始まるインデックス。  
  
 **idCommand**  
 ボタンに関連付けられているコマンドの識別子です。 この識別子は送信、 **WM_COMMAND**メッセージが表示される、ボタンを選択します。 場合、 **fsStyle**メンバーには、`TBSTYLE_SEP`値では、このメンバーは&0; にする必要があります。  
  
 **fsState**  
 状態フラグ ボタンをクリックします。 次の値の組み合わせを指定できます。  
  
- `TBSTATE_CHECKED`ボタンには、**スタイル**のスタイルを設定して、押されました。  
  
- `TBSTATE_ENABLED`ボタンは、ユーザー入力を受け付けます。 この状態がないボタンは、ユーザー入力が受け付けられません、淡色表示にします。  
  
- `TBSTATE_HIDDEN`ボタンは表示されず、ユーザー入力を受け取ることはできません。  
  
- `TBSTATE_INDETERMINATE`ボタンは淡色表示にします。  
  
- `TBSTATE_PRESSED`ボタンが押されました。  
  
- `TBSTATE_WRAP`行の区切りには、ボタンが次に示します。 ボタンが必要、`TBSTATE_ENABLED`状態です。  
  
 **fsStyle**  
 ボタンのスタイル。 次の値の組み合わせを指定できます。  
  
- `TBSTYLE_BUTTON`標準プッシュ ボタンを作成します。  
  
- `TBSTYLE_CHECK`ユーザーがクリックするたびに押された状態と押されていない状態の状態を切り替えるボタンを作成します。 ボタンには、押された状態にあるときに、別の背景色です。  
  
- `TBSTYLE_CHECKGROUP`グループ内の別のボタンが押されるまで押されたままにするチェック マーク ボタンを作成します。  
  
- `TBSTYLE_GROUP`グループ内の別のボタンが押されるまで押されたままにする ボタンを作成します。  
  
- `TBSTYLE_SEP`小さなボタン グループにギャップを提供する、区切り記号を作成します。 ボタンをクリックし、このスタイルでは、ユーザー入力を受信しません。  
  
 `dwData`  
 ユーザー定義データ。  
  
 **iString**  
 ボタンのラベル、このボタンの文字列がない場合は-1 を使用する文字列の&0; から始まるインデックス。  
  
 イメージと文字列のインデックス位置を指定する必要がある必要がありますが以前に追加されて、ツール バー コントロールのリストを使用して[表示](#addbitmap)、 [AddString](#addstring)、または[AddStrings](#addstrings)します。  
  
##  <a name="a-nameaddstringa--ctoolbarctrladdstring"></a><a name="addstring"></a>CToolBarCtrl::AddString  
 リソース ID を文字列のツールバーの内部リストとして渡される、新しい文字列を追加します。  
  
```  
int AddString(UINT nStringID);
```  
  
### <a name="parameters"></a>パラメーター  
 *nStringID*  
 ツール バー コントロールの文字列のリストに追加する文字列リソースのリソース識別子。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、追加する最初の新しい文字列の&0; から始まるインデックスそれ以外の場合 –&1; です。  
  
##  <a name="a-nameaddstringsa--ctoolbarctrladdstrings"></a><a name="addstrings"></a>CToolBarCtrl::AddStrings  
 ツール バー コントロールで利用できる文字列の一覧に新しい文字列を追加します。  
  
```  
int AddStrings(LPCTSTR lpszStrings);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszStrings*  
 ツールバーの文字列のリストに追加する&1; つまたは複数の null で終わる文字列を格納するバッファーのアドレスです。 最後の文字列は、2 つの null 文字で終了する必要があります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、追加する最初の新しい文字列の&0; から始まるインデックスそれ以外の場合 –&1; です。  
  
### <a name="remarks"></a>コメント  
 バッファー内の文字列は、null 文字で区切る必要があります。 最後の文字列が&2; つの null 終端文字を持つことを確認する必要があります。 定数文字列を正しく書式設定には、としてそれを記述する場合があります。  
  
 [!code-cpp[NVC_MFCControlLadenDialog #&72;](../../mfc/codesnippet/cpp/ctoolbarctrl-class_1.cpp)]  
  
 または  
  
 [!code-cpp[NVC_MFCControlLadenDialog #&73;](../../mfc/codesnippet/cpp/ctoolbarctrl-class_2.cpp)]  
  
 渡さないでください、`CString`に&1; つ以上の null 文字があることはできませんので、この関数へのオブジェクト、`CString`です。  
  
##  <a name="a-nameautosizea--ctoolbarctrlautosize"></a><a name="autosize"></a>CToolBarCtrl::AutoSize  
 全体のツール バー コントロールのサイズを変更します。  
  
```  
void AutoSize();
```  
  
### <a name="remarks"></a>コメント  
 親ウィンドウのサイズが変更されたとき、または (ときにボタンやビットマップのサイズの設定や、文字列を追加する)、ツールバーのサイズが変更されたときに、この関数を呼び出す必要があります。  
  
##  <a name="a-namechangebitmapa--ctoolbarctrlchangebitmap"></a><a name="changebitmap"></a>CToolBarCtrl::ChangeBitmap  
 現在のツール バー コントロールのボタンのビットマップを変更します。  
  
```  
BOOL ChangeBitmap(
    int idButton,   
    int iBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `idButton`|新しいビットマップを受け取るには、ボタンのコマンド id。|  
|[入力] `iBitmap`|現在のツール バー コントロールのイメージ リスト内のイメージの&0; から始まるインデックス。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドが成功した場合は、指定したボタンで、指定されたイメージが表示されます。  
  
 このメソッドは、送信、 [TB_CHANGEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787301)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例のビットマップを変更する、**ファイルの保存の**のビットマップ ボタン、**に関する** ボタンをクリックします。  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_3.cpp)]  
  
##  <a name="a-namecheckbuttona--ctoolbarctrlcheckbutton"></a><a name="checkbutton"></a>CToolBarCtrl::CheckButton  
 確認またはツール バー コントロールの指定されたボタンをクリアします。  
  
```  
BOOL CheckButton(
    int nID,  
    BOOL bCheck = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コマンドをオンまたはオフするボタンの id。  
  
 *bCheck*  
 **TRUE** 、ボタンをオンにする**FALSE**をオフにします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 ボタンがオンになって、押されたように表示されます。 1 つ以上のボタンの状態を変更する場合は、通話を検討してください。 [SetState](#setstate)代わりにします。  
  
##  <a name="a-namecommandtoindexa--ctoolbarctrlcommandtoindex"></a><a name="commandtoindex"></a>CToolBarCtrl::CommandToIndex  
 指定されたコマンド id に関連付けられたボタンの&0; から始まるインデックスを取得します。  
  
```  
UINT CommandToIndex(UINT nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 検索するインデックスを持つボタン コマンド ID とします。  
  
### <a name="return-value"></a>戻り値  
 コマンド ID に関連付けられたボタンの&0; から始まるインデックス  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecreatea--ctoolbarctrlcreate"></a><a name="create"></a>CToolBarCtrl::Create  
 ツール バー コントロールを作成し、それをアタッチ、`CToolBarCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 ツール バー コントロールのスタイルを指定します。 ツールバーには、 **WS_CHILD**スタイル。 下にある説明に従ってツールバー ウィンドウおよび スタイルのウィンドウの任意の組み合わせを指定するさらに、**解説**します。  
  
 `rect`  
 ツール バー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 `pParentWnd`  
 ツール バー コントロールの親ウィンドウを指定します。 ことはできません**NULL**します。  
  
 `nID`  
 ツール バー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、`CToolBarCtrl`で&2; つの手順を実行します。 最初に、コンス トラクターを呼び出すし、し、呼び出す**作成**、ツール バー コントロールを作成およびそれにアタッチする、`CToolBarCtrl`オブジェクトです。 ツール バー コントロールに次のウィンドウ スタイルを適用します。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
 参照してください[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]ウィンドウ スタイルの詳細についてです。  
  
 必要に応じての組み合わせを適用[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 コントロールまたはボタン自体にツール バーのスタイルの組み合わせを適用します。 スタイルは、トピックに記載されて[ツール バー コントロールとボタンのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760439)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 拡張スタイルを使用するのには、呼び出す[拡張](#setextendedstyle)を呼び出した後**作成**します。 拡張ウィンドウ スタイルを使用してツールバーを作成するには、呼び出す[するに](#createex)の代わりに**作成**します。  
  
 ツール バー コントロールは、サイズとツールバー、ウィンドウの位置に自動的に設定します。 高さは、ツールバーのボタンの高さに基づきます。 幅は、親ウィンドウのクライアント領域の幅と同じです。 `CCS_TOP`と`CCS_BOTTOM`スタイルでは、クライアント領域の上下に沿ったツールバーが配置されているかどうかを判断します。 ツールバーには既定で、`CCS_TOP`スタイル。  
  
##  <a name="a-namecreateexa--ctoolbarctrlcreateex"></a><a name="createex"></a>するに  
 コントロール (子ウィンドウ) を作成し、関連付けます、`CToolBarCtrl`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーター [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwStyle`  
 ツール バー コントロールのスタイルを指定します。 ツールバーには、 **WS_CHILD**スタイル。 」の説明に従って、ツールバーのウィンドウおよび スタイルのウィンドウの任意の組み合わせを指定するさらに、**解説**の[作成](#create)します。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに[作成](#create)、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。 **CreateEx**で指定された拡張ウィンドウ スタイルを使用してコントロールが作成され`dwExStyle`します。 拡張を使用してコントロールに固有のスタイル セット[拡張](#setextendedstyle)します。 などを使用して`CreateEx`としてこのようなスタイルを設定する**WS_EX_CONTEXTHELP**を使用して、`SetExtendedStyle`としてこのようなスタイルを設定する**TBSTYLE_EX_DRAWDDARROWS**します。 詳細については、「スタイルを参照してください。[ツールバー拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760430)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namectoolbarctrla--ctoolbarctrlctoolbarctrl"></a><a name="ctoolbarctrl"></a>CToolBarCtrl::CToolBarCtrl  
 `CToolBarCtrl` オブジェクトを構築します。  
  
```  
CToolBarCtrl();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[作成](#create)ツールバーを使用できるようにします。  
  
##  <a name="a-namecustomizea--ctoolbarctrlcustomize"></a><a name="customize"></a>CToolBarCtrl::Customize  
 ツールバーのカスタマイズ ダイアログ ボックスが表示されます。  
  
```  
void Customize();
```  
  
### <a name="remarks"></a>コメント  
 このダイアログ ボックスで、ユーザーを追加して、ボタンを削除して、ツールバーをカスタマイズします。 カスタマイズをサポートするために、ツールバーの親ウィンドウ必要があります、カスタマイズ通知メッセージを処理」の説明に従って[カスタマイズ通知の処理](../../mfc/handling-customization-notifications.md)します。 ツールバーの必要がありますも作成されていると、`CCS_ADJUSTABLE`スタイル、」の説明に従って[CToolBarCtrl::Create](#create)します。  
  
 詳細については、サポート技術情報記事 Q241850 を参照してください: [prb]: カスタマイズ ダイアログ表示を呼び出すに CToolBarCtrl::Customize は保持されません。  
  
##  <a name="a-namedeletebuttona--ctoolbarctrldeletebutton"></a><a name="deletebutton"></a>CToolBarCtrl::DeleteButton  
 ツール バー コントロールからボタンを削除します。  
  
```  
BOOL DeleteButton(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 削除するボタンの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameenablebuttona--ctoolbarctrlenablebutton"></a><a name="enablebutton"></a>CToolBarCtrl::EnableButton  
 有効またはツール バー コントロールの指定したボタンを無効にします。  
  
```  
BOOL EnableButton(
    int nID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コマンドを有効または無効にする ボタンの id。  
  
 `bEnable`  
 **TRUE**ボタンを有効にするには**FALSE**ボタンを無効にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 ボタンが有効にすると、押されたおよびチェックすることができます。 1 つ以上のボタンの状態を変更する場合は、通話を検討してください。 [SetState](#setstate)代わりにします。  
  
##  <a name="a-namegetanchorhighlighta--ctoolbarctrlgetanchorhighlight"></a><a name="getanchorhighlight"></a>CToolBarCtrl::GetAnchorHighlight  
 アンカーの強調表示をツールバーの設定を取得します。  
  
```  
BOOL GetAnchorHighlight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ゼロ以外の場合は、アンカーの強調表示が有効です。 0 の場合、アンカーの強調表示は無効です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETANCHORHIGHLIGHT](http://msdn.microsoft.com/library/windows/desktop/bb787313)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetbitmapa--ctoolbarctrlgetbitmap"></a><a name="getbitmap"></a>CToolBarCtrl::GetBitmap  
 ツールバーのボタンに関連付けられているビットマップのインデックスを取得します。  
  
```  
int GetBitmap(int nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ビットマップのインデックスを取得するボタンのコマンド id。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、ビットマップのインデックスを返します。  
  
### <a name="remarks"></a>コメント  
 機能を実装[TB_GETBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787315)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetbitmapflagsa--ctoolbarctrlgetbitmapflags"></a><a name="getbitmapflags"></a>CToolBarCtrl::GetBitmapFlags  
 ツールバーのビットマップのフラグを取得します。  
  
```  
UINT GetBitmapFlags() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **UINT**を持つ、 **TBBF_LARGE**表示では、大きいツール バー ビットマップをクリアそれ以外の場合サポートできる場合にフラグが設定されます。  
  
### <a name="remarks"></a>コメント  
 ツールバーを作成した後は、ツールバーのビットマップを追加する前に、それを呼び出す必要があります。 戻り値は、ディスプレイに大きいビットマップがサポートしているかどうかどうかを示します。 それらを使用して、呼び出しを選択して、表示は、大規模なビットマップをサポートしている場合[SetBitmapSize](#setbitmapsize)と[いて](#setbuttonsize)を使用して、大規模なビットマップを追加する前に[表示](#addbitmap)します。  
  
##  <a name="a-namegetbuttona--ctoolbarctrlgetbutton"></a><a name="getbutton"></a>CToolBarCtrl::GetButton  
 ツール バー コントロールの指定したボタンに関する情報を取得します。  
  
```  
BOOL GetButton(
    int nIndex,  
    LPTBBUTTON lpButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 情報を取得するためのボタンの&0; から始まるインデックス。  
  
 `lpButton`  
 アドレス、`TBBUTTON`構造体をボタンの情報のコピーを取得します。 参照してください[CToolBarCtrl::AddButtons](#addbuttons)については、`TBBUTTON`構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
##  <a name="a-namegetbuttoncounta--ctoolbarctrlgetbuttoncount"></a><a name="getbuttoncount"></a>CToolBarCtrl::GetButtonCount  
 ツール バー コントロールの現在のボタンの数を取得します。  
  
```  
int GetButtonCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンの数。  
  
##  <a name="a-namegetbuttoninfoa--ctoolbarctrlgetbuttoninfo"></a><a name="getbuttoninfo"></a>CToolBarCtrl::GetButtonInfo  
 ツールバーのボタンの情報を取得します。  
  
```  
int GetButtonInfo(
    int nID,  
    TBBUTTONINFO* ptbbi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ボタンの識別子です。  
  
 `ptbbi`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb760478)ボタンの情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、ボタンの&0; から始まるインデックスそれ以外の場合は-1。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb787321)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetbuttonsizea--ctoolbarctrlgetbuttonsize"></a><a name="getbuttonsize"></a>CToolBarCtrl::GetButtonSize  
 ツール バー ボタンのサイズを取得します。  
  
```  
DWORD GetButtonSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`それぞれ LOWORD と HIWORD、幅と高さの値を表す値。  
  
##  <a name="a-namegetbuttontexta--ctoolbarctrlgetbuttontext"></a><a name="getbuttontext"></a>CToolBarCtrl::GetButtonText  
 現在のツール バー コントロールの指定したボタンの表示テキストを取得します。  
  
```  
CString GetButtonText(int idButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `idButton`|表示テキストを取得するボタンの識別子。|  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/using-cstring.md)指定したボタンの表示テキストを格納しています。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TB_GETBUTTONTEXT](http://msdn.microsoft.com/library/windows/desktop/bb787325) Windows SDK で説明されているメッセージです。  
  
##  <a name="a-namegetcolorschemea--ctoolbarctrlgetcolorscheme"></a><a name="getcolorscheme"></a>CToolBarCtrl::GetColorScheme  
 現在のツール バー コントロールの画面の配色を取得します。  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpColorScheme) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `lpColorScheme`|ポインター、 [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502)カラー スキーム情報を受け取る構造体。 このメソッドが戻るとき、強調表示色と影の色 ツール バー コントロールの構造を説明します。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TB_GETCOLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb787327)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetdisabledimagelista--ctoolbarctrlgetdisabledimagelist"></a><a name="getdisabledimagelist"></a>CToolBarCtrl::GetDisabledImageList  
 ツール バー コントロールはボタンを無効になっている表示を使用しているイメージ一覧を取得します。  
  
```  
CImageList* GetDisabledImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクト、または**NULL**無効なイメージ リストが設定されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETDISABLEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787329)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 MFC 実装の`GetDisabledImageList`を使用して、`CImageList`イメージ リストへのハンドルではなく、ツール バー コントロールのボタンを含むオブジェクトのイメージです。  
  
##  <a name="a-namegetdroptargeta--ctoolbarctrlgetdroptarget"></a><a name="getdroptarget"></a>CToolBarCtrl::GetDropTarget  
 取得、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)ツールバー コントロールのインターフェイスです。  
  
```  
HRESULT GetDropTarget(IDropTarget** ppDropTarget) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ppDropTarget`  
 ポインター、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)インターフェイス ポインター。 エラーが発生する場合、 **NULL**ポインターがこのアドレスに格納します。  
  
### <a name="return-value"></a>戻り値  
 返します。、`HRESULT`操作の成功または失敗を示す値。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787343)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetextendedstylea--ctoolbarctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CToolBarCtrl::GetExtendedStyle  
 ツール バー コントロールの拡張スタイルを取得します。  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`ツール バー コントロールの使用されている拡張スタイルを表します。 スタイルの一覧は、次を参照してください。[ツールバー拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760430)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb787331)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegethotimagelista--ctoolbarctrlgethotimagelist"></a><a name="gethotimagelist"></a>CToolBarCtrl::GetHotImageList  
 「ホット」ボタンを表示するツール バー コントロールを使用しているイメージ一覧を取得します。 マウス ポインターが上が強調表示されているホット ボタンが表示されます。  
  
```  
CImageList* GetHotImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクト、または**NULL**無効なイメージ リストが設定されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETHOTIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787334)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 マウス ポインターが上が強調表示されているホット ボタンが表示されます。  
  
##  <a name="a-namegethotitema--ctoolbarctrlgethotitem"></a><a name="gethotitem"></a>CToolBarCtrl::GetHotItem  
 ツールバーのホット アイテムのインデックスを取得します。  
  
```  
int GetHotItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツールバーのホット アイテムの&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETHOTITEM](http://msdn.microsoft.com/library/windows/desktop/bb787336)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetimagelista--ctoolbarctrlgetimagelist"></a><a name="getimagelist"></a>CToolBarCtrl::GetImageList  
 ツール バー コントロールを使用して既定の状態でボタンを表示するイメージ リストを取得します。  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクト、または**NULL**イメージ リストが設定されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787337)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetinsertmarka--ctoolbarctrlgetinsertmark"></a><a name="getinsertmark"></a>CToolBarCtrl::GetInsertMark  
 ツールバーの現在の挿入マークを取得します。  
  
```  
void GetInsertMark(TBINSERTMARK* ptbim) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ptbim`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb760480)挿入マークを受け取る。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb787338)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetinsertmarkcolora--ctoolbarctrlgetinsertmarkcolor"></a><a name="getinsertmarkcolor"></a>CToolBarCtrl::GetInsertMarkColor  
 ツールバーの挿入マークの描画に使用する色を取得します。  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**挿入マークの現在の色を表す値。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb787339)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetitemrecta--ctoolbarctrlgetitemrect"></a><a name="getitemrect"></a>CToolBarCtrl::GetItemRect  
 ツール バー コントロールのボタンの外接する四角形を取得します。  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 情報を取得するためのボタンの&0; から始まるインデックス。  
  
 `lpRect`  
 アドレス、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)外接する四角形の座標を受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 この関数に設定されている状態のボタンの外接する四角形を取得していない`TBSTATE_HIDDEN`します。  
  
##  <a name="a-namegetmaxsizea--ctoolbarctrlgetmaxsize"></a><a name="getmaxsize"></a>CToolBarCtrl::GetMaxSize  
 すべての表示可能なボタンとツールバーの区切り記号の合計サイズを取得します。  
  
```  
BOOL GetMaxSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pSize`  
 ポインター、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)の項目のサイズを受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETMAXSIZE](http://msdn.microsoft.com/library/windows/desktop/bb787341)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetmaxtextrowsa--ctoolbarctrlgetmaxtextrows"></a><a name="getmaxtextrows"></a>CToolBarCtrl::GetMaxTextRows  
 ツール バー ボタンに表示されるテキスト行の最大数を取得します。  
  
```  
int GetMaxTextRows() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツール バー ボタンに表示されているテキスト行の最大数。  
  
##  <a name="a-namegetmetricsa--ctoolbarctrlgetmetrics"></a><a name="getmetrics"></a>CToolBarCtrl::GetMetrics  
 メトリックを取得、`CToolBarCtrl`オブジェクトです。  
  
```  
void GetMetrics(LPTBMETRICS ptbm) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ptbm`  
 ポインター、 [TBMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb760482)の構造、`CToolBarCtrl`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [TB_GETMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb787342) 」の説明に従って、メッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetpaddinga--ctoolbarctrlgetpadding"></a><a name="getpadding"></a>CToolBarCtrl::GetPadding  
 現在のツール バー コントロールの水平および垂直方向の余白を取得します。  
  
```  
BOOL GetPadding(
    int* pnHorzPadding,   
    int* pnVertPadding) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `pnHorzPadding`|ツール バー コントロールの水平方向の余白をピクセル単位で受信する整数。|  
|[出力] `pnVertPadding`|ツール バー コントロールの垂直方向の余白をピクセル単位で受信する整数。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TB_GETPADDING](http://msdn.microsoft.com/library/windows/desktop/bb787344)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetpressedimagelista--ctoolbarctrlgetpressedimagelist"></a><a name="getpressedimagelist"></a>CToolBarCtrl::GetPressedImageList  
 現在のツール バー コントロールが押された状態でボタンを表すために使用されるイメージのリストを取得します。  
  
```  
CImageList* GetPressedImageList();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)現在のコントロールのイメージ リストを格納または`NULL`このようなイメージ リストが設定されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TB_GETPRESSEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787345)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetrecta--ctoolbarctrlgetrect"></a><a name="getrect"></a>CToolBarCtrl::GetRect  
 指定されたツール バー ボタンの外接する四角形を取得します。  
  
```  
BOOL GetRect(
    int nID,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ボタンの識別子です。  
  
 `lpRect`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形の情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**成功した場合は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb787346)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetrowsa--ctoolbarctrlgetrows"></a><a name="getrows"></a>CToolBarCtrl::GetRows  
 ツール バー コントロールで現在表示されているボタンの行の数を取得します。  
  
```  
int GetRows() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在、ツールバーに表示するボタンの行の数。  
  
### <a name="remarks"></a>コメント  
 して行の数は常に&1; つで、ツールバーが作成された場合を除き、`TBSTYLE_WRAPABLE`スタイル。  
  
##  <a name="a-namegetstatea--ctoolbarctrlgetstate"></a><a name="getstate"></a>CToolBarCtrl::GetState  
 か有効になっている、押された、またはチェックなどのツール バー コントロールの指定したボタンの状態に関する情報を取得します。  
  
```  
int GetState(int nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 情報を取得するためのボタンのコマンド id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合、ボタンの状態情報または – 1 それ以外の場合。 ボタンの状態情報に示されている値の組み合わせが可能[CToolBarCtrl::AddButtons](#addbuttons)します。  
  
### <a name="remarks"></a>コメント  
 この関数は、複数の&1; つのボタンの状態を取得する場合に特に便利です。 1 つの状態をだけ取得するには、次のメンバー関数のいずれかを使用: [IsButtonEnabled](#isbuttonenabled)、 [IsButtonChecked](#isbuttonchecked)、 [IsButtonPressed](#isbuttonpressed)、[に](#isbuttonhidden)、または[IsButtonIndeterminate](#isbuttonindeterminate)します。 ただし、`GetState`メンバー関数は、検出する唯一の方法、`TBSTATE_WRAP`状態のボタンをクリックします。  
  
##  <a name="a-namegetstringa--ctoolbarctrlgetstring"></a><a name="getstring"></a>CToolBarCtrl::GetString  
 ツールバーの文字列を取得します。  
  
```  
int GetString(
    int nString,  
    LPTSTR lpstrString,  
    int cchMaxLen) const;  
  
int GetString(
    int nString,  
    CString& str) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nString*  
 文字列のインデックス。  
  
 *lpstrString*  
 文字列を返すために使用されるバッファーへのポインター。  
  
 *cchMaxLen*  
 バッファーのバイト単位の長さです。  
  
 `str`  
 文字列。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、文字列の長さ以外の場合は-1。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_GETSTRING](http://msdn.microsoft.com/library/windows/desktop/bb787349)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetstylea--ctoolbarctrlgetstyle"></a><a name="getstyle"></a>CToolBarCtrl::GetStyle  
 Toolbar コントロールに現在適用されているスタイルを取得します。  
  
```  
DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`の組み合わせを含む[ツール バー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760439)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegettooltipsa--ctoolbarctrlgettooltips"></a><a name="gettooltips"></a>CToolBarCtrl::GetToolTips  
 ツール バー コントロールに関連付けられている場合は、ツール ヒント コントロールのハンドルを取得します。  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)このツールバーに関連付けられているオブジェクトまたは**NULL**ツールバーに関連付けられているツール ヒント コントロールがあるない場合。  
  
### <a name="remarks"></a>コメント  
 通常、ツール バー コントロールは、作成し、独自のツール ヒント コントロールの維持、ために、ほとんどのプログラムは、この関数を呼び出す必要ありません。  
  
##  <a name="a-namehittesta--ctoolbarctrlhittest"></a><a name="hittest"></a>CToolBarCtrl::HitTest  
 ツール バー コントロールでの点のある場所を決定します。  
  
```  
int HitTest(LPPOINT ppt) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ppt`  
 ポインター、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)でヒット テストの x 座標を格納する構造体、 **x**メンバーと y 座標、ヒットのテスト、 **y**メンバーです。 座標は、ツールバーのクライアント領域を基準とは。  
  
### <a name="return-value"></a>戻り値  
 ツールバーにある点の位置を示す整数値。 値が&0; または正の値の場合は、この戻り値は、ポイントにある区切り記号以外の項目の&0; から始まるインデックスです。  
  
 戻り値が負の場合は、ポイントはボタン内に配置されていません。 戻り値の絶対値は、区切り記号アイテムまたは最も近いの区切り記号以外の項目のインデックスです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb787360)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namehidebuttona--ctoolbarctrlhidebutton"></a><a name="hidebutton"></a>CToolBarCtrl::HideButton  
 ツール バー コントロールの指定ボタンを表示または非表示にします。  
  
```  
BOOL HideButton(
    int nID,  
    BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コマンドを表示または非表示 ボタンの id。  
  
 `bHide`  
 **TRUE** 、ボタンを非表示にする**FALSE**を表示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 1 つ以上のボタンの状態を変更する場合は、通話を検討してください。 [SetState](#setstate)代わりにします。  
  
##  <a name="a-nameindeterminatea--ctoolbarctrlindeterminate"></a><a name="indeterminate"></a>CToolBarCtrl::Indeterminate  
 設定またはツール バー コントロールの指定したボタンの中間状態をクリアします。  
  
```  
BOOL Indeterminate(
    int nID,  
    BOOL bIndeterminate = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 不確定な状態を設定、またはクリアするボタンのコマンド id。  
  
 *bIndeterminate*  
 **TRUE**指定したボタンの不確定な状態を設定する**FALSE**をオフにします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 不確定なボタンが表示されるグレーで表示されるなど、ワード プロセッサの方法、ツールバーの [太字] ボタンが選択されているテキストに太字と標準の両方の文字が含まれている場合になります。 1 つ以上のボタンの状態を変更する場合は、通話を検討してください。 [SetState](#setstate)代わりにします。  
  
##  <a name="a-nameinsertbuttona--ctoolbarctrlinsertbutton"></a><a name="insertbutton"></a>CToolBarCtrl::InsertButton  
 ツール バー コントロールにボタンを挿入します。  
  
```  
BOOL InsertButton(
    int nIndex,  
    LPTBBUTTON lpButton);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ボタンの&0; から始まるインデックス。 この関数は、このボタンの左側にある新しいボタンを挿入します。  
  
 `lpButton`  
 アドレス、`TBBUTTON`を挿入するボタンについての情報を含む構造体。 参照してください[CToolBarCtrl::AddButtons](#addbuttons)の詳細については、`TBBUTTON`構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 イメージと文字列のインデックス位置を指定する必要がある必要がありますが以前に追加されて、ツール バー コントロールのリストを使用して[表示](#addbitmap)、 [AddString](#addstring)、または[AddStrings](#addstrings)します。  
  
##  <a name="a-nameinsertmarkhittesta--ctoolbarctrlinsertmarkhittest"></a><a name="insertmarkhittest"></a>CToolBarCtrl::InsertMarkHitTest  
 ツールバーでのポイントの挿入マーク情報を取得します。  
  
```  
BOOL InsertMarkHitTest(
    LPPOINT ppt,  
    LPTBINSERTMARK ptbim) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ppt`  
 ポインター、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)ツールバーのクライアント領域を基準と、ヒット テストを格納する構造体を調整します。  
  
 `ptbim`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb760480)挿入マーク情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_INSERTMARKHITTEST](http://msdn.microsoft.com/library/windows/desktop/bb787367)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameisbuttoncheckeda--ctoolbarctrlisbuttonchecked"></a><a name="isbuttonchecked"></a>CToolBarCtrl::IsButtonChecked  
 ツール バー コントロールの指定したボタンがオンになっているかどうかを決定します。  
  
```  
BOOL IsButtonChecked(int nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ツールバーのボタンのコマンド id。  
  
### <a name="return-value"></a>戻り値  
 ボタンがチェックされている場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 通話を検討してください[GetState](#getstate)を&1; つ以上のボタンの状態を取得する場合。  
  
##  <a name="a-nameisbuttonenableda--ctoolbarctrlisbuttonenabled"></a><a name="isbuttonenabled"></a>CToolBarCtrl::IsButtonEnabled  
 ツール バー コントロールの指定したボタンが有効になっているかどうかを判断します。  
  
```  
BOOL IsButtonEnabled(int nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ツールバーのボタンのコマンド id。  
  
### <a name="return-value"></a>戻り値  
 ボタンが有効な場合は&0; 以外それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 通話を検討してください[GetState](#getstate)を&1; つ以上のボタンの状態を取得する場合。  
  
##  <a name="a-nameisbuttonhiddena--ctoolbarctrlisbuttonhidden"></a><a name="isbuttonhidden"></a>CToolBarCtrl::IsButtonHidden  
 ツール バー コントロールの指定したボタンが非表示になっているかどうかを決定します。  
  
```  
BOOL IsButtonHidden(int nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ツールバーのボタンのコマンド id。  
  
### <a name="return-value"></a>戻り値  
 ボタンが非表示の場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 通話を検討してください[GetState](#getstate)を&1; つ以上のボタンの状態を取得する場合。  
  
##  <a name="a-nameisbuttonhighlighteda--ctoolbarctrlisbuttonhighlighted"></a><a name="isbuttonhighlighted"></a>CToolBarCtrl::IsButtonHighlighted  
 ツール バー ボタンの強調表示状態を確認します。  
  
```  
BOOL IsButtonHighlighted(int nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 ツール バー ボタンのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 正の整数、ボタンが強調表示されている場合、ボタンが強調表示されていない場合は 0 または-1 の場合のエラーが発生します。  
  
##  <a name="a-nameisbuttonindeterminatea--ctoolbarctrlisbuttonindeterminate"></a><a name="isbuttonindeterminate"></a>CToolBarCtrl::IsButtonIndeterminate  
 ツール バー コントロールの指定したボタンが不確定であるかどうかを判断します。  
  
```  
BOOL IsButtonIndeterminate(int nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 ツールバーのボタンのコマンド id。  
  
### <a name="return-value"></a>戻り値  
 正の整数、ボタンは、中間、または-1 の場合、エラーが発生した場合はボタンは不確定である場合がある場合&0; します。  
  
### <a name="remarks"></a>コメント  
 不確定なボタンが表示される選択できない場合など、ワード プロセッサの方法、ツールバーの [太字] ボタンが選択したテキストに太字と標準の両方の文字が含まれている場合に検索します。 通話を検討してください[GetState](#getstate)を&1; つ以上のボタンの状態を取得する場合。  
  
##  <a name="a-nameisbuttonpresseda--ctoolbarctrlisbuttonpressed"></a><a name="isbuttonpressed"></a>CToolBarCtrl::IsButtonPressed  
 ツール バー コントロールの指定したボタンが押されたかどうかを決定します。  
  
```  
BOOL IsButtonPressed(int nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ツールバーのボタンのコマンド id。  
  
### <a name="return-value"></a>戻り値  
 ボタンが押された場合、それ以外の場合&0;&0; 以外の値。  
  
### <a name="remarks"></a>コメント  
 通話を検討してください[GetState](#getstate)を&1; つ以上のボタンの状態を取得する場合。  
  
##  <a name="a-nameloadimagesa--ctoolbarctrlloadimages"></a><a name="loadimages"></a>CToolBarCtrl::LoadImages  
 ツール バー コントロールのイメージ リストにビットマップを読み込みます。  
  
```  
void LoadImages(
    int iBitmapID,  
    HINSTANCE hinst);
```  
  
### <a name="parameters"></a>パラメーター  
 *iBitmapID*  
 読み込まれるイメージを含むビットマップの ID。 指定したビットマップ リソースを指定するビットマップ リソースの ID にこのパラメーターを設定し、設定`hInst`に**NULL**します。 ビットマップ リソースは、1 つのイメージとしてイメージ リストに追加されます。 標準のシステム定義のビットマップを追加するには、設定*hinst*に**HINST_COMMCTRL**し、このパラメーターを次の Id のいずれかに設定します。  
  
|ビットマップの ID|説明|  
|---------------|-----------------|  
|IDB_HIST_LARGE_COLOR|ラージ サイズのエクスプ ローラーのビットマップ|  
|IDB_HIST_SMALL_COLOR|Small の規模のエクスプ ローラー ビットマップ|  
|IDB_STD_LARGE_COLOR|ラージ サイズの標準のビットマップ|  
|IDB_STD_SMALL_COLOR|小さいサイズの標準のビットマップ|  
|IDB_VIEW_LARGE_COLOR|ラージ サイズのビューのビットマップ|  
|IDB_VIEW_SMALL_COLOR|小さなサイズで表示ビットマップ|  
  
 *hinst*  
 呼び出し元のアプリケーションのプログラム インスタンス ハンドル。 このパラメーターを指定できます**HINST_COMMCTRL**標準イメージの一覧を読み込めません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_LOADIMAGES](http://msdn.microsoft.com/library/windows/desktop/bb787381)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namemapacceleratora--ctoolbarctrlmapaccelerator"></a><a name="mapaccelerator"></a>CToolBarCtrl::MapAccelerator  
 ツールバーのボタンにアクセラレータ文字をマップします。  
  
```  
BOOL MapAccelerator(
    TCHAR chAccel,  
    UINT* pIDBtn);
```  
  
### <a name="parameters"></a>パラメーター  
 `chAccel`  
 マップするアクセラレータ文字です。 この文字は、ボタンのテキストに下線が引かれた同じの文字です。  
  
 *pIDBtn*  
 ポインター、 **UINT**で指定されたアクセラレータに対応するボタンのコマンド識別子を受け取る`chAccel`します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_MAPACCELERATOR](http://msdn.microsoft.com/library/windows/desktop/bb787383)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namemarkbuttona--ctoolbarctrlmarkbutton"></a><a name="markbutton"></a>CToolBarCtrl::MarkButton  
 ツール バー コントロールの指定したボタンの強調表示状態を設定します。  
  
```  
BOOL MarkButton(
    int nID,  
    BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ボタンの識別子です。  
  
 `fHighlight`  
 強調表示状態の設定を指定します。 既定では、 **TRUE**します。 場合に設定**FALSE**ボタンは既定の状態に設定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_MARKBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787385)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namemovebuttona--ctoolbarctrlmovebutton"></a><a name="movebutton"></a>CToolBarCtrl::MoveButton  
 ボタンを別の&1; つのインデックスに移動します。  
  
```  
BOOL MoveButton(
    UINT nOldPos,  
    UINT nNewPos);
```  
  
### <a name="parameters"></a>パラメーター  
 *nOldPos*  
 移動するボタンの&0; から始まるインデックス。  
  
 *nNewPos*  
 ボタンの移動先の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_MOVEBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787387)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namepressbuttona--ctoolbarctrlpressbutton"></a><a name="pressbutton"></a>CToolBarCtrl::PressButton  
 押すか、ツール バー コントロールの指定したボタンを解放します。  
  
```  
BOOL PressButton(int nID, BOOL bPress = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 コマンド キーを押すか、解放したボタンの id。  
  
 [入力] `bPress`  
 `true`指定したボタンを押す`false`を指定したボタンを解放します。 既定値は `true` です。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は `true`。それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 1 つ以上のボタンの状態を変更する場合は、通話を検討してください。 [SetState](#setstate)代わりにします。  
  
 このメソッドは、送信、 [TB_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787389)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namereplacebitmapa--ctoolbarctrlreplacebitmap"></a><a name="replacebitmap"></a>CToolBarCtrl::ReplaceBitmap  
 新しいビットマップでは、現在のツール バー コントロールの既存のビットマップを置き換えます。  
  
```  
BOOL ReplaceBitmap(LPTBREPLACEBITMAP pReplaceBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pReplaceBitmap`|ポインター、 [TBREPLACEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb760484)置換されるビットマップと、新しいビットマップを記述する構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TB_REPLACEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787391)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、別のビットマップで、標準ツールバーのビットマップを置き換えます。  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_4.cpp)]  
  
##  <a name="a-namerestorestatea--ctoolbarctrlrestorestate"></a><a name="restorestate"></a>CToolBarCtrl::RestoreState  
 パラメーターで指定されたレジストリの場所からツール バー コントロールの状態を復元します。  
  
```  
void RestoreState(
    HKEY hKeyRoot,  
    LPCTSTR lpszSubKey,  
    LPCTSTR lpszValueName);
```  
  
### <a name="parameters"></a>パラメーター  
 `hKeyRoot`  
 レジストリまたは定義済みの予約されたハンドル値を次のいずれかで現在開いているキーを識別します。  
  
- **HKEY_CLASSES_ROOT**  
  
- **HKEY_CURRENT_USER**  
  
- **HKEY_LOCAL_MACHINE**  
  
- **HKEY_USERS**  
  
 `lpszSubKey`  
 値が関連付けられているサブキーの名前を含む null で終わる文字列へのポインター。 このパラメーターには、null または空の文字列へのポインターを指定できます。 パラメーターがある場合**NULL**、によって識別されるキーに値を追加するは、`hKeyRoot`パラメーター。  
  
 `lpszValueName`  
 取得する値の名前を含む文字列へのポインター。 この名前の値がキーに存在しない関数により、キーに追加します。  
  
##  <a name="a-namesavestatea--ctoolbarctrlsavestate"></a><a name="savestate"></a>CToolBarCtrl::SaveState  
 パラメーターで指定されたレジストリの場所には、ツール バー コントロールの状態を保存します。  
  
```  
void SaveState(
    HKEY hKeyRoot,  
    LPCTSTR lpszSubKey,  
    LPCTSTR lpszValueName);
```  
  
### <a name="parameters"></a>パラメーター  
 `hKeyRoot`  
 レジストリまたは定義済みの予約されたハンドル値を次のいずれかで現在開いているキーを識別します。  
  
- **HKEY_CLASSES_ROOT**  
  
- **HKEY_CURRENT_USER**  
  
- **HKEY_LOCAL_MACHINE**  
  
- **HKEY_USERS**  
  
 `lpszSubKey`  
 値が関連付けられているサブキーの名前を含む null で終わる文字列へのポインター。 このパラメーターには、null または空の文字列へのポインターを指定できます。 パラメーターがある場合**NULL**、によって識別されるキーに値を追加するは、`hKeyRoot`パラメーター。  
  
 `lpszValueName`  
 設定する値の名前を含む文字列へのポインター。 この名前の値がキーに存在しない関数により、キーに追加します。  
  
##  <a name="a-namesetanchorhighlighta--ctoolbarctrlsetanchorhighlight"></a><a name="setanchorhighlight"></a>CToolBarCtrl::SetAnchorHighlight  
 アンカーの強調表示をツールバーの設定を設定します。  
  
```  
BOOL SetAnchorHighlight(BOOL fAnchor = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `fAnchor`  
 アンカーの強調表示を有効になっているまたは無効になっているかどうかを指定します。 この値が&0; 以外の場合は、アンカーの強調表示が有効になります。 この値が&0; の場合は、アンカーの強調表示が無効になります  
  
### <a name="return-value"></a>戻り値  
 以前のアンカー設定します。 強調表示が有効な場合はこの値は&0; 以外の値です。 強調表示が有効でない場合、この値は&0; です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Win32 メッセージの動作を実装して[TB_SETANCHORHIGHLIGHT](http://msdn.microsoft.com/library/windows/desktop/bb787396)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetbitmapsizea--ctoolbarctrlsetbitmapsize"></a><a name="setbitmapsize"></a>CToolBarCtrl::SetBitmapSize  
 ツール バー コントロールに追加する実際のビットマップ イメージのサイズを設定します。  
  
```  
BOOL SetBitmapSize(CSize size);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 幅とビットマップ イメージのピクセル単位の高さ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、ビットマップをツールバーに追加する前にのみ呼び出す必要があります。 アプリケーションがビットマップのサイズを明示的に設定されていない場合の既定値は 15、16 ピクセルです。  
  
##  <a name="a-namesetbuttoninfoa--ctoolbarctrlsetbuttoninfo"></a><a name="setbuttoninfo"></a>CToolBarCtrl::SetButtonInfo  
 ツールバーでは、既存のボタンの情報を設定します。  
  
```  
BOOL SetButtonInfo(
    int nID,  
    TBBUTTONINFO* ptbbi);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ボタンの識別子です。  
  
 `ptbbi`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb760478)ボタンの情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、Win32 メッセージの動作を実装して[TB_SETBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb787413)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetbuttonsizea--ctoolbarctrlsetbuttonsize"></a><a name="setbuttonsize"></a>CToolBarCtrl::SetButtonSize  
 ツール バー コントロールのボタンのサイズを設定します。  
  
```  
BOOL SetButtonSize(CSize size);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 幅と高さ (ピクセル単位)、ボタンの。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 ボタンのサイズは、ビットマップのサイズを囲むとしてサイズ以上で常にあります。 この関数は、ビットマップをツールバーに追加する前にのみ呼び出す必要があります。 アプリケーションが、ボタンのサイズを明示的に設定されていない場合の既定値は 24 で 22 ピクセルです。  
  
### <a name="example"></a>例  
  例を参照してください[CToolBar::GetToolBarCtrl](../../mfc/reference/ctoolbar-class.md#gettoolbarctrl)します。  
  
##  <a name="a-namesetbuttonstructsizea--ctoolbarctrlsetbuttonstructsize"></a><a name="setbuttonstructsize"></a>CToolBarCtrl::SetButtonStructSize  
 サイズを指定、`TBBUTTON`構造体。  
  
```  
void SetButtonStructSize(int nSize);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSize`  
 サイズ (バイト単位) の`TBBUTTON`構造体。  
  
### <a name="remarks"></a>コメント  
 余分なデータを格納する必要がある場合、`TBBUTTON`構造から新しい構造体か、派生でした`TBBUTTON`、メンバーを追加するか、必要を含む新しい構造の作成、`TBBUTTON`構造体を最初のメンバーです。 ツール バー コントロールの新しい構造体のサイズを確認するには、この関数を呼び出すとします。  
  
 参照してください[CToolBarCtrl::AddButtons](#addbuttons)の詳細については、`TBBUTTON`構造体。  
  
##  <a name="a-namesetbuttonwidtha--ctoolbarctrlsetbuttonwidth"></a><a name="setbuttonwidth"></a>CToolBarCtrl::SetButtonWidth  
 ツール バー コントロールの最小値と最大のボタンの幅を設定します。  
  
```  
BOOL SetButtonWidth(
    int cxMin,  
    int cxMax);
```  
  
### <a name="parameters"></a>パラメーター  
 `cxMin`  
 ボタンの最小の幅 (ピクセル単位)。 ツール バー ボタンは、この値よりも限定的にできなくなります。  
  
 *cxMax*  
 最大化ボタンの幅 (ピクセル単位)。 ボタンのテキストが広すぎる場合は、コントロールは、省略記号に表示します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_SETBUTTONWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb787417)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetcmdida--ctoolbarctrlsetcmdid"></a><a name="setcmdid"></a>CToolBarCtrl::SetCmdID  
 指定したボタンが押されると、オーナー ウィンドウに送信されるコマンドの識別子を設定します。  
  
```  
BOOL SetCmdID(
    int nIndex,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 コマンド ID を設定するボタンの&0; から始まるインデックス。  
  
 `nID`  
 選択したボタンに設定するコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は&0; 以外を返します。それ以外の場合&0; を返します。  
  
##  <a name="a-namesetcolorschemea--ctoolbarctrlsetcolorscheme"></a><a name="setcolorscheme"></a>CToolBarCtrl::SetColorScheme  
 現在のツール バー コントロールの画面の配色を設定します。  
  
```  
void SetColorScheme(const COLORSCHEME* lpColorScheme);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `lpColorScheme`|ポインター、 [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502)の強調表示色とツール バー コントロールの影の色を表す構造体。|  
  
### <a name="remarks"></a>コメント  
 このメソッドには影響がない場合、[!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]ビジュアル テーマを設定します。  
  
 このメソッドは、送信、 [TB_SETCOLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb787421)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例では、現在のツール バー コントロールの画面の配色を設定します。 コード例には、赤の各ツール ボタンの左と上のエッジと右や下端が青。 ユーザーがボタンを押したときにボタンの赤い端が青に変わりし、青い端が赤色にします。  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_5.cpp)]  
  
##  <a name="a-namesetdisabledimagelista--ctoolbarctrlsetdisabledimagelist"></a><a name="setdisabledimagelist"></a>CToolBarCtrl::SetDisabledImageList  
 ツール バー コントロールを使用するイメージ リストをボタンの表示を無効に設定します。  
  
```  
CImageList* SetDisabledImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImageList`  
 ポインター、`CImageList`ボタン イメージの表示を無効にするツール バー コントロールで使用するイメージを含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)ボタン イメージの表示を無効にするツール バー コントロールで使用していたオブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_SETDISABLEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787423)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 MFC 実装の`SetDisabledImageList`を使用して、`CImageList`イメージ リストへのハンドルではなく、ツール バー コントロールの無効にされたボタンを含むオブジェクトのイメージです。  
  
##  <a name="a-namesetdrawtextflagsa--ctoolbarctrlsetdrawtextflags"></a><a name="setdrawtextflags"></a>CToolBarCtrl::SetDrawTextFlags  
 Win32 関数でフラグを設定[DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498)、これは、フラグを設定する方法に従って書式設定された指定の四角形内のテキストの描画に使用します。  
  
```  
DWORD SetDrawTextFlags(
    DWORD dwMask,  
    DWORD dwDTFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMask`  
 1 つ以上の Win32 関数で指定された、dt _ フラグの組み合わせ[DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498)、ビットでこれを示す`dwDTFlags`テキストを描画するときに使用されます。  
  
 `dwDTFlags`  
 1 つ以上の Win32 関数で指定された、dt _ フラグの組み合わせ`DrawText`ボタンのテキストの描画方法を示します。 この値は`DrawText`ボタンのテキストを描画するタイミングです。  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`フラグの描画前のテキストを格納します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_SETDRAWTEXTFLAGS](http://msdn.microsoft.com/library/windows/desktop/bb787425)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このメンバー関数は、Win32 関数でフラグを設定`DrawText`フラグを設定する方法に従って書式設定された、指定された四角形にテキストを描画します。  
  
##  <a name="a-namesetextendedstylea--ctoolbarctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CToolBarCtrl::SetExtendedStyle  
 ツール バー コントロールの拡張スタイルを設定します。  
  
```  
DWORD SetExtendedStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 新しい拡張スタイルを指定する値。 このパラメーターは、ツールバーの拡張スタイルの組み合わせを指定できます。  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`拡張スタイルを表す前です。 スタイルの一覧は、次を参照してください。[ツールバー拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760430)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb787427)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesethotimagelista--ctoolbarctrlsethotimagelist"></a><a name="sethotimagelist"></a>CToolBarCtrl::SetHotImageList  
 「ホット」ボタンを表示するツール バー コントロールを使用するイメージのリストを設定します。  
  
```  
CImageList* SetHotImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImageList`  
 ポインター、`CImageList`ホット ボタンの画像を表示するツール バー コントロールで使用されるイメージを含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)ホット ボタンの画像を表示するツール バー コントロールで使用されていたオブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_SETHOTIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787429)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 MFC 実装の`SetHotImageList`を使用して、`CImageList`イメージ リストへのハンドルではなく、ツール バー コントロールのホット ボタンを含むオブジェクトのイメージです。 ポインターが上にあるときに強調表示されているホット ボタンが表示されます。  
  
##  <a name="a-namesethotitema--ctoolbarctrlsethotitem"></a><a name="sethotitem"></a>CToolBarCtrl::SetHotItem  
 ツールバーのホット アイテムを設定します。  
  
```  
int SetHotItem(int nHot);
```  
  
### <a name="parameters"></a>パラメーター  
 *nHot*  
 ホット行われる項目の&0; から始まるインデックス番号。 この値が-1 の場合は、項目はどれもホットになりません。  
  
### <a name="return-value"></a>戻り値  
 前のホット アイテムまたはホット アイテムがなかった場合は-1 のインデックス。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_SETHOTITEM](http://msdn.microsoft.com/library/windows/desktop/bb787431)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetimagelista--ctoolbarctrlsetimagelist"></a><a name="setimagelist"></a>CToolBarCtrl::SetImageList  
 既定の状態にあるボタンを表示するツールバーを使用するイメージのリストを設定します。  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImageList`  
 ポインター、`CImageList`を既定の状態でボタンのイメージを表示するツール バー コントロールで使用されるイメージを含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)ツール バー コントロールでは既定の状態でボタン イメージの表示を使用していたオブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787433)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 MFC 実装の`SetImageList`を使用して、`CImageList`イメージ リストへのハンドルではなく、ツール バー コントロールのボタンを含むオブジェクトのイメージです。  
  
##  <a name="a-namesetindenta--ctoolbarctrlsetindent"></a><a name="setindent"></a>CToolBarCtrl::SetIndent  
 ツール バー コントロールの最初のボタンでインデントを設定します。  
  
```  
BOOL SetIndent(int iIndent);
```  
  
### <a name="parameters"></a>パラメーター  
 *iIndent*  
 インデント幅をピクセル単位で指定する値。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
##  <a name="a-namesetinsertmarka--ctoolbarctrlsetinsertmark"></a><a name="setinsertmark"></a>CToolBarCtrl::SetInsertMark  
 ツールバーの現在の挿入マークを設定します。  
  
```  
void SetInsertMark(TBINSERTMARK* ptbim);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptbim`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb760480)挿入マークを格納する構造体。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb787437)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetinsertmarkcolora--ctoolbarctrlsetinsertmarkcolor"></a><a name="setinsertmarkcolor"></a>CToolBarCtrl::SetInsertMarkColor  
 ツールバーの挿入マークの描画に使用する色を設定します。  
  
```  
COLORREF SetInsertMarkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `clrNew`  
 A **COLORREF**新しい挿入マークの色を表す値。  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**前の挿入マークの色を表す値。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TB_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb787439)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetmaxtextrowsa--ctoolbarctrlsetmaxtextrows"></a><a name="setmaxtextrows"></a>CToolBarCtrl::SetMaxTextRows  
 ツール バー ボタンに表示されるテキスト行の最大数を設定します。  
  
```  
BOOL SetMaxTextRows(int iMaxRows);
```  
  
### <a name="parameters"></a>パラメーター  
 *iMaxRows*  
 設定する行の最大数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
##  <a name="a-namesetmetricsa--ctoolbarctrlsetmetrics"></a><a name="setmetrics"></a>CToolBarCtrl::SetMetrics  
 メトリックを設定、`CToolBarCtrl`オブジェクトです。  
  
```  
void SetMetrics(LPTBMETRICS ptbm);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptbm`  
 ポインター、 [TBMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb760482)の構造、`CToolBarCtrl`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [TB_SETMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb787446) 」の説明に従って、メッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetownera--ctoolbarctrlsetowner"></a><a name="setowner"></a>CToolBarCtrl::SetOwner  
 ツール バー コントロールのオーナー ウィンドウを設定します。  
  
```  
void SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ポインター、`CWnd`または`CWnd`-ツール バー コントロールの新しいオーナー ウィンドウとなるオブジェクトを派生します。  
  
### <a name="remarks"></a>コメント  
 オーナー ウィンドウには、ウィンドウ、ツールバーから通知を受け取るですが。  
  
##  <a name="a-namesetpaddinga--ctoolbarctrlsetpadding"></a><a name="setpadding"></a>CToolBarCtrl::SetPadding  
 現在のツール バー コントロールの水平および垂直方向の余白を設定します。  
  
```  
DWORD SetPadding(
    int nHorzPadding,   
    int nVertPadding);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nHorzPadding`|ツール バー コントロールの水平方向の余白をピクセル単位で指定します。|  
|[入力] `nVertPadding`|ツール バー コントロールの垂直方向の余白をピクセル単位で指定します。|  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`下位ワードに以前の水平方向の埋め込み値、および上位ワードには、以前の垂直方向の埋め込み値が含まれています。 余白の値はピクセル単位で測定されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TB_SETPADDING](http://msdn.microsoft.com/library/windows/desktop/bb787448)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例では、現在のツール バー コントロールの水平および垂直方向の余白を 20 ピクセルに設定します。  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1&4;](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_6.cpp)]  
  
##  <a name="a-namesetpressedimagelista--ctoolbarctrlsetpressedimagelist"></a><a name="setpressedimagelist"></a>CToolBarCtrl::SetPressedImageList  
 現在のツール バー コントロールが押された状態でボタンを表すために使用されるイメージのリストを設定します。  
  
```  
CImagelist* SetPressedImageList(
    int iImageID,   
    CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iImageID`|イメージ リストの&0; から始まるインデックス。 イメージ リストの&1; つだけを使用する場合は、このパラメーターを&0; に設定します。|  
|[入力] `pImageList`|ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)新しいイメージのリストを格納します。|  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)現在のコントロールの前のイメージ リストを格納または`NULL`このようなイメージ リストが設定されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TB_SETPRESSEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787453)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例では、既定のイメージ リストと同じである圧縮されたイメージのリストを設定します。  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_7.cpp)]  
  
##  <a name="a-namesetrowsa--ctoolbarctrlsetrows"></a><a name="setrows"></a>CToolBarCtrl::SetRows  
 要求された行数をそれ自体のサイズを変更するツール バー コントロールを確認します。  
  
```  
void SetRows(
    int nRows,  
    BOOL bLarger,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nRows`  
 要求の行の数。  
  
 `bLarger`  
 要求された行数をツールバーのサイズを変更できない場合に、複数の行または行を減らしてを使用するかどうかを通知します。  
  
 `lpRect`  
 指す、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ツールバーの新しい外接する四角形を受け取る。  
  
### <a name="remarks"></a>コメント  
 場合は、要求された行数にサイズ変更できない、ツールバー、自体のサイズを調整するか次大きくまたは次小さい有効なサイズの値に応じて`bLarger`します。 場合`bLarger`は**TRUE**、新しい行の数は、要求された数より大きくなります。 場合`bLarger`は**FALSE**、新しい行の数は、要求された数より小さくなります。  
  
 指定された数の行は、同じ数の (おそらく、最後の行を除く) のボタンがあるすべての行になるように、ボタンを整列できる場合、ツールバーの有効なです。 たとえば、4 つのボタンを含むツールバーでしたはサイズ変更&3; 行に最後の&2; つの行が小さい値を指定する必要がありますので。 場合に&4; つの行を得られる場合は&3; つの行にサイズを変更しようとすると、`bLarger`が**TRUE**場合&2; つの行と`bLarger`が**FALSE**します。  
  
 ツールバーに区切り記号がある場合は、指定された数の行に有効な場合の規則はさらに複雑です。 レイアウトは、(1 つ目の前に区切り記号でボタン) と、グループ内の最後のボタンのボタン グループは分割されない複数行に、グループが&1; つの行に収まらない場合を除きになるように計算されます。  
  
 グループが&1; つの行に収まらない場合は、大規模なグループが終了した行に収まる場合でも、次の行で、次のグループが開始されます。 このルールの目的より顕著に表れますが大規模なグループ間の分離を行うにです。 結果として得られる垂直区切り記号が行としてカウントされます。  
  
 なお、`SetRows`メンバー関数は、ツールバーのサイズは最小のレイアウトを選択して常にします。 使用して、ツールバーの作成、`TBSTYLE_WRAPABLE`スタイルおよびコントロールのサイズを変更しは特定のコントロールの幅を上記で説明したメソッドを適用するだけです。  
  
 この関数は、ツールバーを使用して作成に対してのみ呼び出すことが、`TBSTYLE_WRAPABLE`スタイル。  
  
##  <a name="a-namesetstatea--ctoolbarctrlsetstate"></a><a name="setstate"></a>CToolBarCtrl::SetState  
 ツール バー コントロールの指定したボタンの状態を設定します。  
  
```  
BOOL SetState(
    int nID,  
    UINT nState);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ボタンのコマンド id。  
  
 `nState`  
 状態フラグ。 ボタンの状態で表示されている値の組み合わせであることができます[CToolBarCtrl::AddButtons](#addbuttons)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、1 つ以上のボタンの状態を設定する場合に特に便利です。 だけ&1; つの状態を設定するには、次のメンバー関数のいずれかを使用します。 [EnableButton](#enablebutton)、[切り替わるよう](#checkbutton)、[に](#hidebutton)、[不定](#indeterminate)、または[PressButton](#pressbutton)します。  
  
##  <a name="a-namesetstylea--ctoolbarctrlsetstyle"></a><a name="setstyle"></a>CToolBarCtrl::SetStyle  
 ツール バー コントロールのスタイルを設定します。  
  
```  
void SetStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 A`DWORD`の組み合わせを含む[ツール バー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760439)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesettooltipsa--ctoolbarctrlsettooltips"></a><a name="settooltips"></a>CToolBarCtrl::SetToolTips  
 ツール バー コントロールとツール ヒント コントロールを関連付けます。  
  
```  
void SetToolTips(CToolTipCtrl* pTip);
```  
  
### <a name="parameters"></a>パラメーター  
 *pTip*  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)オブジェクトです。  
  
##  <a name="a-namesetwindowthemea--ctoolbarctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CToolBarCtrl::SetWindowTheme  
 Visual スタイルを設定、`CToolBarCtrl`オブジェクトです。  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszSubAppName`  
 設定するツールバーの表示スタイルを含む Unicode 文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [TB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb787465) 」の説明に従って、メッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC サンプル MFCIE](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBar クラス](../../mfc/reference/ctoolbar-class.md)

