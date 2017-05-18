---
title: "CMFCButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCButton
- AFXBUTTON/CMFCButton
- AFXBUTTON/CMFCButton::CleanUp
- AFXBUTTON/CMFCButton::EnableFullTextTooltip
- AFXBUTTON/CMFCButton::EnableMenuFont
- AFXBUTTON/CMFCButton::EnableWindowsTheming
- AFXBUTTON/CMFCButton::GetToolTipCtrl
- AFXBUTTON/CMFCButton::IsAutoCheck
- AFXBUTTON/CMFCButton::IsAutorepeatCommandMode
- AFXBUTTON/CMFCButton::IsCheckBox
- AFXBUTTON/CMFCButton::IsChecked
- AFXBUTTON/CMFCButton::IsHighlighted
- AFXBUTTON/CMFCButton::IsPressed
- AFXBUTTON/CMFCButton::IsPushed
- AFXBUTTON/CMFCButton::IsRadioButton
- AFXBUTTON/CMFCButton::IsWindowsThemingEnabled
- AFXBUTTON/CMFCButton::SetAutorepeatMode
- AFXBUTTON/CMFCButton::SetCheckedImage
- AFXBUTTON/CMFCButton::SetFaceColor
- AFXBUTTON/CMFCButton::SetImage
- AFXBUTTON/CMFCButton::SetMouseCursor
- AFXBUTTON/CMFCButton::SetMouseCursorHand
- AFXBUTTON/CMFCButton::SetStdImage
- AFXBUTTON/CMFCButton::SetTextColor
- AFXBUTTON/CMFCButton::SetTextHotColor
- AFXBUTTON/CMFCButton::SetTooltip
- AFXBUTTON/CMFCButton::SizeToContent
- AFXBUTTON/CMFCButton::OnDraw
- AFXBUTTON/CMFCButton::OnDrawBorder
- AFXBUTTON/CMFCButton::OnDrawFocusRect
- AFXBUTTON/CMFCButton::OnDrawText
- AFXBUTTON/CMFCButton::OnFillBackground
- AFXBUTTON/CMFCButton::SelectFont
- AFXBUTTON/CMFCButton::m_bDrawFocus
- AFXBUTTON/CMFCButton::m_bHighlightChecked
- AFXBUTTON/CMFCButton::m_bRightImage
- AFXBUTTON/CMFCButton::m_bTransparent
- AFXBUTTON/CMFCButton::m_nAlignStyle
- AFXBUTTON/CMFCButton::m_nFlatStyle
dev_langs:
- C++
helpviewer_keywords:
- CMFCButton::CreateObject method
- CMFCButton::DrawItem method
- CMFCButton::PreTranslateMessage method
- CMFCButton constructor
- CMFCButton::OnDrawParentBackground method
- CMFCButton class
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
caps.latest.revision: 35
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 89cd722ac15a1d9ac6b6c815c837559e302f0e68
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcbutton-class"></a>CMFCButton クラス
`CMFCButton`クラスを追加する機能、 [CButton](../../mfc/reference/cbutton-class.md)ボタン テキストの配置、ボタンのテキストとイメージの組み合わせ、カーソルの選択、およびツールヒントの指定などのクラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCButton : public CButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCButton::CMFCButton`|既定のコンストラクター|  
|`CMFCButton::~CMFCButton`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCButton::CleanUp](#cleanup)|内部変数をリセットし、イメージ、ビットマップ、アイコンなどの割り当てられたリソースを解放します。|  
|`CMFCButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCButton::DrawItem`|オーナー描画ボタンの外観が変更されたときに、フレームワークによって呼び出されます。 (上書き[CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem))。|  
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|大きいツールヒント ウィンドウまたは小さいツールヒント ウィンドウ内のテキストの一部が切り捨てられたバージョンに、ツールヒントのテキスト全体を表示するかどうかを指定します。|  
|[CMFCButton::EnableMenuFont](#enablemenufont)|ボタン テキストのフォントは、アプリケーションのメニューのフォントと同じかどうかを指定します。|  
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|ボタンの境界線のスタイルが現在の Windows のテーマに対応しているかどうかを指定します。|  
|`CMFCButton::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|基になるツール ヒント コントロールへの参照を返します。|  
|[CMFCButton::IsAutoCheck](#isautocheck)|チェック ボックスまたはオプション ボタンが自動のボタンであるかどうかを示します。|  
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|ボタンが自動繰り返しモードに設定されているかどうかを示します。|  
|[CMFCButton::IsCheckBox](#ischeckbox)|ボタンがチェック ボックス ボタンであるかどうかを示します。|  
|[CMFCButton::IsChecked](#ischecked)|現在のボタンがオンになっているかどうかを示します。|  
|[CMFCButton::IsHighlighted](#ishighlighted)|ボタンが強調表示されているかどうかを示します。|  
|[CMFCButton::IsPressed](#ispressed)|ボタンがプッシュされ、強調表示されているかどうかを示します。|  
|[CMFCButton::IsPushed](#ispushed)|ボタンをクリックするかどうかを示します。|  
|[CMFCButton::IsRadioButton](#isradiobutton)|ボタンがラジオ ボタンであるかどうかを示します。|  
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|ボタンの境界線のスタイルが現在の Windows のテーマに対応しているかどうかを示します。|  
|`CMFCButton::OnDrawParentBackground`|指定領域にはボタンの親の背景を描画します。 (上書き[AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|  
|`CMFCButton::PreTranslateMessage`|ウィンドウのメッセージの変換にディスパッチされる前に、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 (上書き[CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage))。|  
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|ボタンを自動繰り返しモードに設定します。|  
|[CMFCButton::SetCheckedImage](#setcheckedimage)|チェック ボタンのイメージを設定します。|  
|[CMFCButton::SetFaceColor](#setfacecolor)|ボタンのテキストの背景色を設定します。|  
|[CMFCButton::SetImage](#setimage)|ボタンのイメージを設定します。|  
|[CMFCButton::SetMouseCursor](#setmousecursor)|カーソルのイメージを設定します。|  
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|手の形のイメージをするには、カーソルを設定します。|  
|[CMFCButton::SetStdImage](#setstdimage)|使用して、`CMenuImages`ボタンのイメージを設定するオブジェクト。|  
|[CMFCButton::SetTextColor](#settextcolor)|選択されていないボタンのボタンのテキストの色を設定します。|  
|[CMFCButton::SetTextHotColor](#settexthotcolor)|選択されているボタンのボタンのテキストの色を設定します。|  
|[CMFCButton::SetTooltip](#settooltip)|ボタン、ツールヒントに関連付けます。|  
|[CMFCButton::SizeToContent](#sizetocontent)|ボタンのテキストおよびイメージを格納するためのボタンのサイズを変更します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCButton::OnDraw](#ondraw)|ボタンを描画するためにフレームワークによって呼び出されます。|  
|[CMFCButton::OnDrawBorder](#ondrawborder)|ボタンの境界線を描画するためにフレームワークによって呼び出されます。|  
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|フォーカスされたボタンの四角形を描画するためにフレームワークによって呼び出されます。|  
|[CMFCButton::OnDrawText](#ondrawtext)|ボタンのテキストを描画するためにフレームワークによって呼び出されます。|  
|[CMFCButton::OnFillBackground](#onfillbackground)|ボタンのテキストの背景を描画するためにフレームワークによって呼び出されます。|  
|[CMFCButton::SelectFont](#selectfont)|指定したデバイス コンテキストに関連付けられているフォントを取得します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|ボタンの周囲のフォーカス四角形を描画するかどうかを示します。|  
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|上にカーソルを置くと、BS_CHECKBOX スタイル ボタンを強調表示するかどうかを示します。|  
|[CMFCButton::m_bRightImage](#m_brightimage)|ボタンの右側にあるイメージを表示するかどうかを示します。|  
|[CMFCButton::m_bTransparent](#m_btransparent)|ボタンは透過的であるかどうかを示します。|  
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|ボタンのテキストの配置を指定します。|  
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|ふちなし、フラット、セミコロンのフラットまたは 3D などのボタンのスタイルを指定します。|  
  
## <a name="remarks"></a>コメント  
 派生したその他の種類のボタンは、`CMFCButton`クラスなど、 [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md)ハイパーリンクをサポートするクラスと`CMFCColorButton`クラスは、カラー ピッカー ダイアログ ボックスをサポートしています。  
  
 スタイル、`CMFCButton`オブジェクトを指定できます*3D*、*フラット*、*半フラット*または*罫線なし*します。 ボタンのテキストは、左、上、またはボタンの中央に配置できます。 実行時に、テキスト、イメージ、またはテキストおよびイメージ ボタンを表示するかどうかを制御できます。 カーソルがボタン上に置いた場合に、特定のカーソルのイメージが表示されることを指定することもできます。  
  
 ボタン コントロールを作成、コード内で直接、またはを使用して、 **MFC クラス ウィザード**ツールとダイアログ ボックスのテンプレートです。 ボタン コントロールを直接作成する場合は、追加、`CMFCButton`アプリケーション、および、呼び出すコンス トラクターに変数と`Create`のメソッド、`CMFCButton`オブジェクトです。 使用する場合、 **MFC クラス ウィザード**、追加、`CButton`そのため、アプリケーション変数から変数の型を変更して`CButton`に`CMFCButton`します。  
  
 ダイアログ ボックスのアプリケーションでの通知メッセージを処理するためには、メッセージ マップ エントリと各通知のイベント ハンドラーを追加します。 送信された通知、`CMFCButton`オブジェクトは、によって送信されたものと同じ、`CButton`オブジェクトです。  
  
## <a name="example"></a>例  
 次の例では、多様なメソッドを使用して、ボタンのプロパティを構成する方法、`CMFCButton`クラスです。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls #&28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls #&31;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls&#32;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls #&33;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxbutton.h  
  
##  <a name="cleanup"></a>CMFCButton::CleanUp  
 内部変数をリセットし、イメージ、ビットマップ、アイコンなどの割り当てられたリソースを解放します。  
  
```  
virtual void CleanUp();
```  
  
##  <a name="enablefulltexttooltip"></a>CMFCButton::EnableFullTextTooltip  
 大きいツールヒント ウィンドウまたは小さいツールヒント ウィンドウ内のテキストの一部が切り捨てられたバージョンに、ツールヒントのテキスト全体を表示するかどうかを指定します。  
  
```  
void EnableFullTextTooltip(BOOL bOn=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bOn`  
 `TRUE`すべてのテキストを表示するには`FALSE`テキストを切り捨て表示します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablemenufont"></a>CMFCButton::EnableMenuFont  
 ボタン テキストのフォントは、アプリケーションのメニューのフォントと同じかどうかを指定します。  
  
```  
void EnableMenuFont(
    BOOL bOn=TRUE,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bOn`  
 `TRUE`ボタン テキストのフォントとしてアプリケーションのメニューのフォントを使用するには`FALSE`システム フォントを使用します。 既定値は、`TRUE` です。  
  
 [入力] `bRedraw`  
 `TRUE`画面をすぐに再描画するにはそれ以外の場合、`FALSE`です。 既定値は、`TRUE` です。  
  
### <a name="remarks"></a>コメント  
 ボタン テキストのフォントを指定するのにはこのメソッドを使用しない場合は、フォントを指定できます、 [cwnd::setfont](../../mfc/reference/cwnd-class.md#setfont)メソッドです。 フォントがまったく指定しない場合、フレームワークは、既定のフォントを設定します。  
  
##  <a name="enablewindowstheming"></a>CMFCButton::EnableWindowsTheming  
 ボタンの境界線のスタイルが現在の Windows のテーマに対応しているかどうかを指定します。  
  
```  
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`現在の Windows テーマを使用して、ボタンの境界線を描画するには`FALSE` Windows テーマを使用しないようにします。 既定値は、`TRUE` です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、アプリケーションから派生したすべてのボタン、影響、`CMFCButton`クラスです。  
  
##  <a name="gettooltipctrl"></a>CMFCButton::GetToolTipCtrl  
 基になるツール ヒント コントロールへの参照を返します。  
  
```  
CToolTipCtrl& GetToolTipCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 基になるツール ヒント コントロールへの参照。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isautocheck"></a>CMFCButton::IsAutoCheck  
 チェック ボックスまたはオプション ボタンが自動のボタンであるかどうかを示します。  
  
```  
BOOL IsAutoCheck() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ボタンにスタイルを BS_AUTOCHECKBOX か BS_AUTORADIOBUTTON です。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isautorepeatcommandmode"></a>CMFCButton::IsAutorepeatCommandMode  
 ボタンが自動繰り返しモードに設定されているかどうかを示します。  
  
```  
BOOL IsAutorepeatCommandMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンが 自動繰り返しモードに設定されている場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCButton::SetAutorepeatMode](#setautorepeatmode)ボタンを自動繰り返しモードに設定します。  
  
##  <a name="ischeckbox"></a>CMFCButton::IsCheckBox  
 ボタンがチェック ボックス ボタンであるかどうかを示します。  
  
```  
BOOL IsCheckBox() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、ボタンに BS_CHECKBOX または BS_AUTOCHECKBOX のいずれかのスタイルそれ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ischecked"></a>CMFCButton::IsChecked  
 現在のボタンがオンになっているかどうかを示します。  
  
```  
BOOL IsChecked() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`現在のボタンがチェックされている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、さまざまな種類のボタンがオンになっていることを示すためにさまざまな方法を使用します。 たとえば、ラジオ ボタンがオンになってドットが含まれている場合含まれている場合は、チェック ボックスをオンにします、 **X**です。  
  
##  <a name="ishighlighted"></a>CMFCButton::IsHighlighted  
 ボタンが強調表示されているかどうかを示します。  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合は、ボタンが強調表示されます。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 ボタンの上でマウス ボタンが強調表示されます。  
  
##  <a name="ispressed"></a>CMFCButton::IsPressed  
 ボタンがプッシュされ、強調表示されているかどうかを示します。  
  
```  
BOOL IsPressed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、ボタンが押されたとします。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ispushed"></a>CMFCButton::IsPushed  
 ボタンをクリックするかどうかを示します。  
  
```  
BOOL IsPushed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンが押されている場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isradiobutton"></a>CMFCButton::IsRadioButton  
 ボタンがラジオ ボタンであるかどうかを示します。  
  
```  
BOOL IsRadioButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタン スタイルは BS_RADIOBUTTON または BS_AUTORADIOBUTTON; は、TRUE を返します。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="iswindowsthemingenabled"></a>CMFCButton::IsWindowsThemingEnabled  
 ボタンの境界線のスタイルが現在の Windows のテーマに対応しているかどうかを示します。  
  
```  
static BOOL IsWindowsThemingEnabled();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ボタンの境界線のスタイルが現在の Windows のテーマに対応する場合それ以外の場合、`FALSE`です。  
  
##  <a name="m_bdrawfocus"></a>CMFCButton::m_bDrawFocus  
 ボタンの周囲のフォーカス四角形を描画するかどうかを示します。  
  
```  
BOOL m_bDrawFocus;  
```  
  
### <a name="remarks"></a>コメント  
 設定、`m_bDrawFocus`メンバー`TRUE`フレームワークは、ボタンのテキストを囲むフォーカス四角形を描画し、ボタンがフォーカスを受け取った場合のイメージを指定します。  
  
 `CMFCButton`コンス トラクターにこのメンバーは初期化`TRUE`します。  
  
##  <a name="m_bhighlightchecked"></a>CMFCButton::m_bHighlightChecked  
 上にカーソルを置くと、BS_CHECKBOX スタイル ボタンを強調表示するかどうかを示します。  
  
```  
BOOL m_bHighlightChecked;  
```  
  
### <a name="remarks"></a>コメント  
 設定、`m_bHighlightChecked`メンバー`TRUE`上にマウスを重ねると、フレームワークが BS_CHECKBOX スタイル ボタンをハイライトことを指定します。  
  
##  <a name="m_brightimage"></a>CMFCButton::m_bRightImage  
 ボタンの右側にあるイメージを表示するかどうかを示します。  
  
```  
BOOL m_bRightImage;  
```  
  
### <a name="remarks"></a>コメント  
 設定、`m_bRightImage`メンバー`TRUE`にフレームワークが、ボタンのテキスト ラベルの右側に、ボタンの画像を表示するよう指定します。  
  
##  <a name="m_btransparent"></a>CMFCButton::m_bTransparent  
 ボタンは透過的であるかどうかを示します。  
  
```  
BOOL m_bTransparent;  
```  
  
### <a name="remarks"></a>コメント  
 設定、`m_bTransparent`メンバー`TRUE`いるフレームワークは透明にするボタンを指定します。 `CMFCButton`コンス トラクターにこのメンバーは初期化`FALSE`します。  
  
##  <a name="m_nalignstyle"></a>CMFCButton::m_nAlignStyle  
 ボタンのテキストの配置を指定します。  
  
```  
AlignStyle m_nAlignStyle;  
```  
  
### <a name="remarks"></a>コメント  
 次のいずれかの`CMFCButton::AlignStyle`ボタンのテキストの配置を指定する列挙値。  
  
|値|説明|  
|-----------|-----------------|  
|ALIGN_CENTER|(既定値)ボタンのテキスト、ボタンの中央に揃えて配置します。|  
|ALIGN_LEFT|ボタンのテキスト、ボタンの左側に揃えて配置します。|  
|ALIGN_RIGHT|ボタンのテキスト、ボタンの右側に揃えて配置します。|  
  
 `CMFCButton`コンス トラクターが ALIGN_CENTER にこのメンバーを初期化します。  
  
##  <a name="m_nflatstyle"></a>CMFCButton::m_nFlatStyle  
 ふちなし、フラット、セミコロンのフラットまたは 3D などのボタンのスタイルを指定します。  
  
```  
FlatStyle  m_nFlatStyle;  
```  
  
### <a name="remarks"></a>コメント  
 次の表に、`CMFCButton::m_nFlatStyle`ボタンの外観を指定する列挙値。  
  
|値|説明|  
|-----------|-----------------|  
|BUTTONSTYLE_3D|(既定値)高、3 次元の辺に、ボタンが表示されます。 ボタンがクリックされたときに、深くインデントに押される、ボタンが表示されます。|  
|BUTTONSTYLE_FLAT|マウスは、ボタンの上一時停止せずとボタンが、2 次元を高さはありません。 ボタンの上にマウスを置いたときに、低、3 次元の辺に、ボタンが表示されます。 ボタンがクリックされたときに、簡易インデントに押される、ボタンが表示されます。|  
|BUTTONSTYLE_SEMIFLAT|低、3 次元の辺に、ボタンが表示されます。 ボタンがクリックされたときに、深くインデントに押される、ボタンが表示されます。|  
|BUTTONSTYLE_NOBORDERS|ボタンは、サイド発生したいないし、2 次元を常に表示します。 ボタンは、クリックしてされたときに押す、インデントには表示されません。|  
  
 `CMFCButton`コンス トラクターにこのメンバーは初期化`BUTTONSTYLE_3D`します。  
  
### <a name="example"></a>例  
 次の例では、値を設定する方法、`m_nFlatStyle`内のメンバー変数、`CMFCButton`クラスです。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls #&28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls #&29;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]  
  
##  <a name="ondraw"></a>CMFCButton::OnDraw  
 ボタンを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 ボタンに外接する四角形への参照。  
  
 [入力] `uiState`  
 現在のボタンの状態。 詳細については、次を参照してください。、`itemState`のメンバー、 [DRAWITEMSTRUCT 構造体](../../mfc/reference/drawitemstruct-structure.md)トピックです。  
  
### <a name="remarks"></a>コメント  
 独自のコードを使用して、ボタンを描画するには、このメソッドをオーバーライドします。  
  
##  <a name="ondrawborder"></a>CMFCButton::OnDrawBorder  
 ボタンの境界線を描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rectClient`  
 ボタンに外接する四角形への参照。  
  
 [入力] `uiState`  
 現在のボタンの状態。 詳細については、次を参照してください。、`itemState`のメンバー、 [DRAWITEMSTRUCT 構造体](../../mfc/reference/drawitemstruct-structure.md)トピックです。  
  
### <a name="remarks"></a>コメント  
 独自のコードを使用して境界線を描画するには、このメソッドをオーバーライドします。  
  
##  <a name="ondrawfocusrect"></a>CMFCButton::OnDrawFocusRect  
 フォーカスされたボタンの四角形を描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rectClient`  
 ボタンに外接する四角形への参照。  
  
### <a name="remarks"></a>コメント  
 フォーカスされた四角形を描画する独自のコードを使用するには、このメソッドをオーバーライドします。  
  
##  <a name="ondrawtext"></a>CMFCButton::OnDrawText  
 ボタンのテキストを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    const CRect& rect,  
    const CString& strText,  
    UINT uiDTFlags,  
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 ボタンに外接する四角形への参照。  
  
 [入力] `strText`  
 描画するテキスト。  
  
 [入力] `uiDTFlags`  
 テキストの書式設定する方法を指定するフラグ。 詳細については、次を参照してください。、`nFormat`のパラメーター、 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)メソッドです。  
  
 [入力] `uiState`  
 (予約済み)  
  
### <a name="remarks"></a>コメント  
 独自のコードを使用して、ボタンのテキストを描画するには、このメソッドをオーバーライドします。  
  
##  <a name="onfillbackground"></a>CMFCButton::OnFillBackground  
 ボタンのテキストの背景を描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rectClient`  
 ボタンに外接する四角形への参照。  
  
### <a name="remarks"></a>コメント  
 独自のコードを使用して、ボタンの背景を描画するには、このメソッドをオーバーライドします。  
  
##  <a name="selectfont"></a>CMFCButton::SelectFont  
 指定したデバイス コンテキストに関連付けられているフォントを取得します。  
  
```  
virtual CFont* SelectFont(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 独自のコードを使用して、フォントを取得するには、このメソッドをオーバーライドします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setautorepeatmode"></a>CMFCButton::SetAutorepeatMode  
 ボタンを自動繰り返しモードに設定します。  
  
```  
void SetAutorepeatMode(int nTimeDelay=500);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTimeDelay`  
 親ウィンドウに送信されたメッセージの間の間隔を指定する負でない数値。 間隔はミリ秒単位で計測し、その既定値は 500 ミリ秒です。 自動繰り返しはメッセージ モードを無効に&0; を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、常に、ボタンが離されるまでに、それらの親ウィンドウに、WM_COMMAND メッセージを送信するボタンまたは`nTimeDelay`パラメーターが&0; に設定します。  
  
##  <a name="setcheckedimage"></a>CMFCButton::SetCheckedImage  
 チェック ボタンのイメージを設定します。  
  
```  
void SetCheckedImage(
    HICON hIcon,  
    BOOL bAutoDestroy=TRUE,  
    HICON hIconHot=NULL,  
    HICON hIconDisabled=NULL,  
    BOOL bAlphaBlend=FALSE);

 
void SetCheckedImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy=TRUE,  
    HBITMAP hBitmapHot=NULL,  
    BOOL bMap3dColors=TRUE,  
    HBITMAP hBitmapDisabled=NULL);

 
void SetCheckedImage(
    UINT uiBmpResId,  
    UINT uiBmpHotResId=0,  
    UINT uiBmpDsblResID=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hIcon`  
 ビットマップと、新しいイメージのマスクに含まれているアイコンへのハンドルします。  
  
 [入力] `bAutoDestroy`  
 `TRUE`ビットマップ リソースを自動的に破棄することを指定するにはそれ以外の場合、`FALSE`です。 既定値は、`TRUE` です。  
  
 [入力] `hIconHot`  
 選択した状態のイメージが含まれるアイコンへのハンドルします。  
  
 [入力] `hBitmap`  
 選択されていない状態のイメージを含むビットマップへのハンドルします。  
  
 [入力] `hBitmapHot`  
 選択した状態のイメージを含むビットマップへのハンドルします。  
  
 [入力] `bMap3dColors`  
 ボタンの背景の透明色を指定します。ボタンの面は、です。 `TRUE`カラー値 RGB (192、192, 192) を使用するには`FALSE`によって定義された色の値を使用する`AFX_GLOBAL_DATA::clrBtnFace`です。  
  
 [入力] `uiBmpResId`  
 選択されていないイメージのリソース ID。  
  
 [入力] `uiBmpHotResId`  
 選択した画像のリソース ID です。  
  
 [入力] `hIconDisabled`  
 無効なイメージのアイコンへのハンドルします。  
  
 [入力] `hBitmapDisabled`  
 無効なイメージを含むビットマップへのハンドルします。  
  
 [入力] `uiBmpDsblResID`  
 無効になっているビットマップのリソース ID です。  
  
 [入力] `bAlphaBlend`  
 `TRUE`アルファ チャネルを使用する唯一の 32 ビット イメージを使用するには`FALSE`、アルファ チャネル イメージのみを使用しないようにします。 既定値は、`FALSE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setfacecolor"></a>CMFCButton::SetFaceColor  
 ボタンのテキストの背景色を設定します。  
  
```  
void SetFaceColor(
    COLORREF crFace,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `crFace`  
 RGB 色の値。  
  
 [入力] `bRedraw`  
 `TRUE`画面をすぐに再描画するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、ボタンの背景 (フェイス) の新しい塗りつぶしの色を定義します。 バック グラウンド入力ときに、 [CMFCButton::m_bTransparent](#m_btransparent)メンバー変数が`TRUE`です。  
  
##  <a name="setimage"></a>CMFCButton::SetImage  
 ボタンのイメージを設定します。  
  
```  
void SetImage(
    HICON hIcon,  
    BOOL bAutoDestroy=TRUE,  
    HICON hIconHot=NULL,  
    HICON hIconDisabled=NULL,  
    BOOL bAlphaBlend=FALSE);

 
void SetImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy=TRUE,  
    HBITMAP hBitmapHot=NULL,  
    BOOL bMap3dColors=TRUE,  
    HBITMAP hBitmapDisabled=NULL);

 
void SetImage(
    UINT uiBmpResId,  
    UINT uiBmpHotResId=0,  
    UINT uiBmpDsblResID=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hIcon`  
 ビットマップと、新しいイメージのマスクに含まれているアイコンへのハンドルします。  
  
 [入力] `bAutoDestroy`  
 `TRUE`ビットマップ リソースを自動的に破棄することを指定するにはそれ以外の場合、`FALSE`です。 既定値は、`TRUE` です。  
  
 [入力] `hIconHot`  
 選択した状態のイメージが含まれるアイコンへのハンドルします。  
  
 [入力] `hBitmap`  
 選択されていない状態のイメージを含むビットマップへのハンドルします。  
  
 [入力] `hBitmapHot`  
 選択した状態のイメージを含むビットマップへのハンドルします。  
  
 [入力] `uiBmpResId`  
 選択されていないイメージのリソース ID。  
  
 [入力] `uiBmpHotResId`  
 選択した画像のリソース ID です。  
  
 [入力] `bMap3dColors`  
 ボタンの背景の透明色を指定します。ボタンの面は、です。 `TRUE`カラー値 RGB (192、192, 192) を使用するには`FALSE`によって定義された色の値を使用する`AFX_GLOBAL_DATA::clrBtnFace`です。  
  
 [入力] `hIconDisabled`  
 無効なイメージのアイコンへのハンドルします。  
  
 [入力] `hBitmapDisabled`  
 無効なイメージを含むビットマップへのハンドルします。  
  
 [入力] `uiBmpDsblResID`  
 無効になっているビットマップのリソース ID です。  
  
 [入力] `bAlphaBlend`  
 `TRUE`アルファ チャネルを使用する唯一の 32 ビット イメージを使用するには`FALSE`、アルファ チャネル イメージのみを使用しないようにします。 既定値は、`FALSE` です。  
  
### <a name="remarks"></a>コメント  
  
### <a name="example"></a>例  
 次の例では、さまざまなバージョンの使用、`SetImage`メソッドで、`CMFCButton`クラスです。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls #&28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls #&31;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
  
##  <a name="setmousecursor"></a>CMFCButton::SetMouseCursor  
 カーソルのイメージを設定します。  
  
```  
void SetMouseCursor(HCURSOR hcursor);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hcursor`  
 カーソルのハンドル。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタンで手形カーソルなど、カーソルのイメージを関連付けます。 カーソルは、アプリケーション リソースから読み込まれます。  
  
### <a name="example"></a>例  
 次の例では、使用して、`SetMouseCursor`メソッドで、`CMFCButton`クラスです。 内のコード例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls #&28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls #&30;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]  
  
##  <a name="setmousecursorhand"></a>CMFCButton::SetMouseCursorHand  
 手の形のイメージをするには、カーソルを設定します。  
  
```  
void SetMouseCursorHand();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタンに手の形のカーソルのイメージを関連付けます。 カーソルは、アプリケーション リソースから読み込まれます。  
  
##  <a name="setstdimage"></a>CMFCButton::SetStdImage  
 使用して、`CMenuImages`ボタンのイメージを設定するオブジェクト。  
  
```  
void SetStdImage(
    CMenuImages::IMAGES_IDS id,  
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,  
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `id`  
 定義されているボタン イメージの識別子の&1; つ、`CMenuImage::IMAGES_IDS`列挙します。 イメージの値は、矢印、pin、ラジオ ボタンなどのイメージを指定します。  
  
 [入力] `state`  
 定義されているボタン イメージの状態識別子の&1; つ、`CMenuImages::IMAGE_STATE`列挙します。 イメージの状態では、黒、灰色、明るい灰色で、白、濃い灰色などのボタンの色を指定します。 既定値は `CMenuImages::ImageBlack` です。  
  
 [入力] `idDisabled`  
 定義されているボタン イメージの識別子の&1; つ、`CMenuImage::IMAGES_IDS`列挙します。 イメージは、ボタンは無効になっていることを示します。 既定値は最初のボタンの画像 ( `CMenuImages::IdArrowDown`)。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="settextcolor"></a>CMFCButton::SetTextColor  
 選択されていないボタンのボタンのテキストの色を設定します。  
  
```  
void SetTextColor(COLORREF clrText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `clrText`  
 RGB 色の値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="settexthotcolor"></a>CMFCButton::SetTextHotColor  
 選択されているボタンのボタンのテキストの色を設定します。  
  
```  
void SetTextHotColor(COLORREF clrTextHot);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `clrTextHot`  
 RGB 色の値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="settooltip"></a>CMFCButton::SetTooltip  
 ボタン、ツールヒントに関連付けます。  
  
```  
void SetTooltip(LPCTSTR lpszToolTipText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszToolTipText`  
 ツールヒントのテキストへのポインター。 ツール ヒントを無効にするのには NULL を指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sizetocontent"></a>CMFCButton::SizeToContent  
 ボタンのテキストおよびイメージを格納するためのボタンのサイズを変更します。  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCalcOnly`  
 `TRUE`ボタンの新しいサイズを変更できませんを計算します。`FALSE`ボタンのサイズを変更します。 既定値は、`FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 A`CSize`ボタンの新しいサイズを格納しているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは、10 ピクセルの左右の余白と 5 ピクセルの上下の余白を含む新しいサイズを計算します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCLinkCtrl クラス](../../mfc/reference/cmfclinkctrl-class.md)   
 [CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)   
 [CMFCMenuButton クラス](../../mfc/reference/cmfcmenubutton-class.md)

