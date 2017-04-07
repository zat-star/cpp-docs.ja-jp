---
title: "CMFCColorBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorBar
- AFXCOLORBAR/CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::ContextToSize
- AFXCOLORBAR/CMFCColorBar::CreateControl
- AFXCOLORBAR/CMFCColorBar::Create
- AFXCOLORBAR/CMFCColorBar::EnableAutomaticButton
- AFXCOLORBAR/CMFCColorBar::EnableOtherButton
- AFXCOLORBAR/CMFCColorBar::GetColor
- AFXCOLORBAR/CMFCColorBar::GetCommandID
- AFXCOLORBAR/CMFCColorBar::GetHighlightedColor
- AFXCOLORBAR/CMFCColorBar::GetHorzMargin
- AFXCOLORBAR/CMFCColorBar::GetVertMargin
- AFXCOLORBAR/CMFCColorBar::IsTearOff
- AFXCOLORBAR/CMFCColorBar::SetColor
- AFXCOLORBAR/CMFCColorBar::SetColorName
- AFXCOLORBAR/CMFCColorBar::SetCommandID
- AFXCOLORBAR/CMFCColorBar::SetDocumentColors
- AFXCOLORBAR/CMFCColorBar::SetHorzMargin
- AFXCOLORBAR/CMFCColorBar::SetVertMargin
- AFXCOLORBAR/CMFCColorBar::AdjustLocations
- AFXCOLORBAR/CMFCColorBar::AllowChangeTextLabels
- AFXCOLORBAR/CMFCColorBar::AllowShowOnList
- AFXCOLORBAR/CMFCColorBar::CalcSize
- AFXCOLORBAR/CMFCColorBar::CreatePalette
- AFXCOLORBAR/CMFCColorBar::GetColorGridSize
- AFXCOLORBAR/CMFCColorBar::GetExtraHeight
- AFXCOLORBAR/CMFCColorBar::InitColors
- AFXCOLORBAR/CMFCColorBar::OnKey
- AFXCOLORBAR/CMFCColorBar::OnSendCommand
- AFXCOLORBAR/CMFCColorBar::OnUpdateCmdUI
- AFXCOLORBAR/CMFCColorBar::OpenColorDialog
- AFXCOLORBAR/CMFCColorBar::Rebuild
- AFXCOLORBAR/CMFCColorBar::SelectPalette
- AFXCOLORBAR/CMFCColorBar::SetPropList
- AFXCOLORBAR/CMFCColorBar::ShowCommandMessageString
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorBar class
- CMFCColorBar::m_ColorAutomatic data member
- CMFCColorBar::m_bInternal data member
- CMFCColorBar::m_bIsEnabled data member
- CMFCColorBar::m_nNumColumnsVert data member
- CMFCColorBar::m_nVertMargin data member
- CMFCColorBar::m_strDocColors data member
- CMFCColorBar::m_BoxSize data member
- CMFCColorBar::m_pParentBtn data member
- CMFCColorBar::m_bIsTearOff data member
- CMFCColorBar::m_nHorzOffset data member
- CMFCColorBar::m_pParentRibbonBtn data member
- CMFCColorBar::m_nNumRowsHorz data member
- CMFCColorBar::m_bStdColorDlg data member
- CMFCColorBar::m_strAutoColor data member
- CMFCColorBar::m_ColorNames data member
- CMFCColorBar::m_strOtherColor data member
- CMFCColorBar::m_lstDocColors data member
- CMFCColorBar::m_pWndPropList data member
- CMFCColorBar::m_ColorSelected data member
- CMFCColorBar::m_nCommandID data member
- CMFCColorBar::m_nHorzMargin data member
- CMFCColorBar::m_nRowHeight data member
- CMFCColorBar::m_Palette data member
- CMFCColorBar::m_colors data member
- CMFCColorBar::m_nVertOffset data member
- CMFCColorBar::m_nNumColumns data member
- CMFCColorBar::m_bShowDocColorsWhenDocked data member
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: bf4d431a3f3237587dc9f86be91f11b9b5016fe2
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorbar-class"></a>CMFCColorBar クラス
`CMFCColorBar`クラスは、ドキュメントやアプリケーションで色を選択できるドッキング コントロール バーを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|`CMFCColorBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorBar::ContextToSize](#contexttosize)|カラー バー コントロールのボタンを格納するために必要なし、そのボタンの位置を調整する垂直および水平方向の余白を計算します。|  
|[CMFCColorBar::CreateControl](#createcontrol)|カラー バー コントロール ウィンドウを作成し、それをアタッチ、`CMFCColorBar`オブジェクトを指定されたカラー パレットを格納するコントロールのサイズを変更します。|  
|[CMFCColorBar::Create](#create)|カラー バー コントロール ウィンドウを作成し、それをアタッチ、`CMFCColorBar`オブジェクトです。|  
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|自動のボタンの表示と非表示を切り替えます。|  
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|有効またはユーザーが他の色を選択できるダイアログ ボックスの表示を無効にします。|  
|[CMFCColorBar::GetColor](#getcolor)|現在選択されている色を取得します。|  
|[CMFCColorBar::GetCommandID](#getcommandid)|現在のカラー バー コントロールのコマンド ID を取得します。|  
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|色のボタンにフォーカスを示す色を取得します。たとえば、ボタンは*ホット*します。|  
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|水平右のマージンを取得します。|  
|[CMFCColorBar::GetVertMargin](#getvertmargin)|上部または下部にある色のセルとクライアント領域の境界間のスペースは、縦方向のマージンを取得します。|  
|[CMFCColorBar::IsTearOff](#istearoff)|現在のカラー バーがドッキング可能かどうかを示します。|  
|[CMFCColorBar::SetColor](#setcolor)|現在選択されている色を設定します。|  
|[CMFCColorBar::SetColorName](#setcolorname)|指定した色の新しい名前を設定します。|  
|[CMFCColorBar::SetCommandID](#setcommandid)|カラー バー コントロールの新しいコマンド ID を設定します。|  
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|現在のドキュメントで使用される色の一覧を設定します。|  
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|水平右のマージンを設定します。|  
|[CMFCColorBar::SetVertMargin](#setvertmargin)|上位または下位のカラー セルとクライアント領域の境界間のスペースは、縦方向のマージンを設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorBar::AdjustLocations](#adjustlocations)|カラー バー コントロールの色のボタンの位置を調整します。|  
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|色のボタンのテキスト ラベルを変更できるかどうかを示します。|  
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|カスタマイズのプロセス中に、カラー バーのコントロール オブジェクトがツールバーの一覧に表示できるかどうかを示します。|  
|[CMFCColorBar::CalcSize](#calcsize)|レイアウトの計算プロセスの一部として、フレームワークによって呼び出されます。|  
|[CMFCColorBar::CreatePalette](#createpalette)|色の配列の指定した色とパレットを初期化します。|  
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|カラー バー コントロールのグリッドの行と列の数を計算します。|  
|[CMFCColorBar::GetExtraHeight](#getextraheight)|現在のカラー バーがなどその他のユーザー インターフェイス要素を表示するために必要な追加の高さを計算、**他の**ボタンやドキュメントの色。|  
|[CMFCColorBar::InitColors](#initcolors)|指定したパレットまたはシステムの既定のパレットの色と色の配列を初期化します。|  
|[CMFCColorBar::OnKey](#onkey)|ユーザーがキーボード ボタンを押したときに、フレームワークによって呼び出されます。|  
|[CMFCColorBar::OnSendCommand](#onsendcommand)|ポップアップ コントロールの階層構造を閉じるために、フレームワークによって呼び出されます。|  
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|有効にするか、アイテムを表示する前に、カラー バー コントロールのユーザー インターフェイス項目を無効にするためにフレームワークによって呼び出されます。|  
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|色のダイアログ ボックスが開きます。|  
|[CMFCColorBar::Rebuild](#rebuild)|カラー バー コントロールを完全に再描画します。|  
|[CMFCColorBar::SelectPalette](#selectpalette)|現在のカラー バー コントロールの親ボタンのパレットを指定したデバイス コンテキストの論理パレットを設定します。|  
|[CMFCColorBar::SetPropList](#setproplist)|セット、`m_pWndPropList`プロパティ グリッド コントロールを指すポインターを指定するデータ メンバーを保護します。|  
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|ステータス バーにメッセージ行を更新するカラー バー コントロールを所有するフレーム ウィンドウを要求します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|`m_bInternal`|マウス イベントを処理するかどうかを指定するブール型フィールドです。 このフィールドはときに通常は、マウス イベントが処理される`TRUE`、カスタマイズ モードが`FALSE`です。|  
|`m_bIsEnabled`|コントロールが有効になっているかどうかを示すブール値。|  
|`m_bIsTearOff`|カラー バー コントロールがドッキングをサポートしているかどうかを示すブール値。|  
|`m_BoxSize`|A [CSize](../../atl-mfc-shared/reference/csize-class.md)カラー バーのグリッドでセルのサイズを指定するオブジェクト。|  
|`m_bShowDocColorsWhenDocked`|カラー バーがドッキングされているときに、ドキュメントの色を表示するかどうかを示すブール値。 詳細については、次を参照してください。 [CMFCColorBar::SetDocumentColors](#setdocumentcolors)します。|  
|`m_bStdColorDlg`|標準的なシステムの色 ダイアログ ボックスを表示するかどうかを示すブール値、または[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  ダイアログ ボックス。 詳細については、次を参照してください。 [CMFCColorBar::EnableOtherButton](#enableotherbutton)します。|  
|`m_ColorAutomatic`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)自動設定、現在の色を格納します。 詳細については、次を参照してください。 [CMFCColorBar::EnableOtherButton](#enableotherbutton)します。|  
|`m_ColorNames`|[メンバー](../../mfc/reference/cmap-class.md)名を持つ色の RGB のセットを関連付けるオブジェクト。|  
|`m_colors`|A [CArray](../../mfc/reference/carray-class.md)の[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)カラー バーのコントロールに表示される色を含む値。|  
|`m_ColorSelected`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)ユーザーがカラー バーのコントロールから現在選択されている色である値します。|  
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md)の[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)ドキュメントで現在使用されている色が含まれる値。|  
|`m_nCommandID`|色のボタンのコマンド ID は、符号なし整数。|  
|`m_nHorzMargin`|色のグリッドのカラー ボタンの間の水平方向の余白を表す整数。|  
|`m_nHorzOffset`|色のボタンの中央に水平方向のオフセットを表す整数。 この値は、テキストやイメージを色だけでなく、ボタンが表示される場合に有効です。|  
|`m_nNumColumns`|色のカラー バー コントロールのグリッドの列の数を表す整数。|  
|`m_nNumColumnsVert`|色の垂直方向のグリッド内の列の数を表す整数。|  
|`m_nNumRowsHorz`|色の水平方向のグリッドの列の数を表す整数。|  
|`m_nRowHeight`|色のグリッドのカラー ボタンの行の高さを表す整数。|  
|`m_nVertMargin`|色のグリッドのカラー ボタンの間の垂直方向の余白を表す整数。|  
|`m_nVertOffset`|色のボタンの中央に縦方向のオフセットを表す整数。 この値は、テキストやイメージを色だけでなく、ボタンが表示される場合に有効です。|  
|`m_Palette`|A [CPalette](../../mfc/reference/cpalette-class.md)のカラー バー コントロールで使用される色。|  
|`m_pParentBtn`|ポインター、 [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)現在のボタンの親であるオブジェクト。 色のボタンがツール バー コントロールの階層では、または、カラー プロパティのグリッド コントロールで、この値は重要です。|  
|`m_pParentRibbonBtn`|ポインター、 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)内の現在のボタンの親のボタンをリボンには、オブジェクトです。 色のボタンがツール バー コントロールの階層では、または、カラー プロパティのグリッド コントロールで、この値は重要です。|  
|`m_pWndPropList`|ポインター、 [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)オブジェクトです。|  
|`m_strAutoColor`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md)に表示されるテキストである、**自動** ボタンをクリックします。 詳細については、次を参照してください。 [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)します。|  
|`m_strDocColors`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md)ドキュメントの色のボタンに表示されるテキストであります。 詳細については、次を参照してください。 [CMFCColorBar::SetDocumentColors](#setdocumentcolors)します。|  
|`m_strOtherColor`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md)に表示されるテキストである、*他の* ボタンをクリックします。 詳細については、次を参照してください。 [CMFCColorBar::EnableOtherButton](#enableotherbutton)します。|  
  
## <a name="remarks"></a>コメント  
 通常、作成しないと、`CMFCColorBar`オブジェクトに直接します。 代わりに、 [CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)(メニューとツールバーで使用)、または[CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)を作成、`CMFCColorBar`オブジェクトです。  
  
 `CMFCColorBar`クラスには、次の機能が用意されています。  
  
-   ドキュメントの色の一覧が自動的に調整します。  
  
-   保存し、ドキュメントの状態と共に、その状態を復元します。  
  
-   「自動」のボタンを管理します。  
  
-   使用して、 [CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)コントロールをカスタムの色を選択します。  
  
-   「ティアオフ」状態をサポートしています (を使用して作成された場合、 [CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md))。  
  
 組み込むように、`CMFCColorBar`をアプリケーションに機能します。  
  
1.  標準のメニュー ボタンを作成し、ID が、たとえば ID_CHAR_COLOR を割り当てます。  
  
2.  フレーム ウィンドウ クラスに、オーバーライド、 [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu)メソッドと置換標準のメニュー ボタン、 [CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)オブジェクト (を呼び出して[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton))。  
  
3.  すべてのスタイルを設定および有効化し、の機能を無効にする、`CMFCColorBar`中に[CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)作成します。 `CMFCColorMenuButton`オブジェクトを動的に作成、 `CMFCColorBar` framework 呼び出し後、オブジェクト、`CreatePopupMenu`メソッドです。  
  
 フレームワークを使用して、ユーザーがカラー バー コントロールのボタンをクリックしたときに、`ON_COMMAND`マクロをカラー バー コントロールの親に通知します。 マクロでは、コマンド ID パラメーターは、手順 1 (この例では ID_CHAR_COLOR) のカラー バー コントロールのボタンに割り当てられている値です。 詳細については、次を参照してください。、 [CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)、 [CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)、 [CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)、 [CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)、および[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)クラスです。  
  
## <a name="example"></a>例  
 次の例では、多様なメソッドを使用してカラー バーを構成する方法、`CMFCColorBar`クラスです。 メソッドで、上下左右の余白を設定する、その他のボタンを有効にする、カラー バー コントロール ウィンドウを作成、および現在選択されている色を設定します。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls&#1;](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#2;](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
 [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcolorbar.h  
  
##  <a name="adjustlocations"></a>CMFCColorBar::AdjustLocations  
 カラー バー コントロールの色のボタンの位置を調整します。  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは時にフレームワークによって呼び出さ`WM_SIZE`メッセージ処理します。  
  
##  <a name="allowchangetextlabels"></a>CMFCColorBar::AllowChangeTextLabels  
 色のボタンのテキスト ラベルを変更できるかどうかを示します。  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE`。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは常`FALSE`、つまりテキスト ラベルを変更することはできません。 テキスト ラベルを変更を有効にするには、このメソッドをオーバーライドします。  
  
##  <a name="allowshowonlist"></a>CMFCColorBar::AllowShowOnList  
 カスタマイズのプロセス中に、カラー バーのコントロール オブジェクトがツールバーの一覧に表示できるかどうかを示します。  
  
```  
virtual BOOL AllowShowOnList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE`。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは常`TRUE`フレームワークのことを意味するカスタマイズのプロセス中にカラー バー コントロールを表示できます。 別の動作を実装するには、このメソッドをオーバーライドします。  
  
##  <a name="calcsize"></a>CMFCColorBar::CalcSize  
 レイアウトの計算プロセスの一部として、フレームワークによって呼び出されます。  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bVertDock`  
 `TRUE`カラー バー コントロールが垂直方向にドッキングされていることを指定するには`FALSE`をカラー バー コントロールが水平方向にドッキングされていることを指定します。  
  
### <a name="return-value"></a>戻り値  
 カラー バー コントロールのカラー ボタンの配列のサイズ。  
  
##  <a name="cmfccolorbar"></a>CMFCColorBar::CMFCColorBar  
 `CMFCColorBar` オブジェクトを構築します。  
  
```  
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    int nColumns,  
    int nRowsDockHorz,  
    int nColDockVert,  
    COLORREF colorAutomatic,  
    UINT nCommandID,  
    CMFCColorButton* pParentBtn);

 
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nCommandID,  
    CMFCRibbonColorButton* pParentRibbonBtn);

 
CMFCColorBar(
    CMFCColorBar& src,  
    UINT uiCommandID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `colors`  
 フレームワークがカラー バーのコントロールに表示される色の配列。  
  
 [入力] `color`  
 最初に選択した色です。  
  
 [入力] `lpszAutoColor`  
 テキスト ラベル、*自動*(既定) の色のボタン、または`NULL`です。  
  
 自動のボタンの標準のラベルは**自動**です。  
  
 [入力] `lpszOtherColor`  
 テキスト ラベル、*他の*ボタンを他の色を表示、または`NULL`です。  
  
 その他のボタンの標準のラベルは**他の色。**.  
  
 [入力] `lpszDocColors`  
 ドキュメントの色のボタンのテキスト ラベル。 ドキュメントのカラー パレットには、ドキュメントが現在使用されているすべての色が一覧表示します。  
  
 [入力] `lstDocColors`  
 ドキュメントが現在使用されている色の一覧。  
  
 [入力] `nColumns`  
 色の配列がある列の数。  
  
 [入力] `nRowsDockHorz`  
 カラー バーが水平方向にドッキングされている行の数。  
  
 [入力] `nColDockVert`  
 カラー バーが垂直方向にドッキングされている列の数。  
  
 [入力] `colorAutomatic`  
 クリックすると、自動的に適用される既定の色。  
  
 [入力] `nCommandID`  
 カラー バー コントロールのコマンド id。  
  
 [入力] `pParentBtn`  
 親ボタンへのポインター。  
  
 [入力] `src`  
 既存の`CMFCColorBar`新しいにコピーされるオブジェクト`CMFCColorBar`オブジェクトです。  
  
 [入力] `uiCommandID`  
 コマンド ID。  
  
##  <a name="contexttosize"></a>CMFCColorBar::ContextToSize  
 カラー バー コントロールのボタンを格納するために必要なこれらのボタンの位置を調整する垂直および水平方向の余白を計算します。  
  
```  
void ContextToSize(
    BOOL bSquareButtons = TRUE,   
    BOOL bCenterButtons = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `bSquareButtons`|`TRUE`カラー バー コントロールのボタンの図形が四角形であることを指定するにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。|  
|[入力] `bCenterButtons`|`TRUE`カラー バーのコントロール ボタンの表示コンテンツを中央揃えにするかを指定するにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。|  
  
### <a name="remarks"></a>コメント  
  
##  <a name="create"></a>CMFCColorBar::Create  
 カラー バー コントロール ウィンドウを作成し、それをアタッチ、`CMFCColorBar`オブジェクトです。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle,  
    UINT nID,  
    CPalette* pPalette=NULL,  
    int nColumns=0,  
    int nRowsDockHorz=0,  
    int nColDockVert=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。  
  
 [入力] `dwStyle`  
 ビットごとの組み合わせ (OR)[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。  
  
 [入力] `nID`  
 コマンド ID。  
  
 [入力] `pPalette`  
 カラー パレットへのポインター。 既定値は、`NULL` です。  
  
 [入力] `nColumns`  
 カラー バー コントロールの列の数。 既定値は 0 です。  
  
 [入力] `nRowsDockHorz`  
 水平方向にドッキングすると、カラー バー コントロールの行の数。 既定値は 0 です。  
  
 [入力] `nColDockVert`  
 垂直方向にドッキングすると、カラー バー コントロールの列の数。 既定値は 0 です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 構築する、`CMFCColorBar`オブジェクト、クラス コンス トラクターをこのメソッドを呼び出します。 `Create`メソッドは、Windows のコントロールを作成し、色の一覧を初期化します。  
  
##  <a name="createcontrol"></a>CMFCColorBar::CreateControl  
 カラー バー コントロール ウィンドウを作成し、それをアタッチ、 `CMFCColorBar` 、オブジェクトし、指定されたカラー パレットを格納するコントロール ウィンドウのサイズを変更します。  
  
```  
virtual BOOL CreateControl(
    CWnd* pParentWnd,  
    const CRect& rect,  
    UINT nID,  
    int nColumns=-1,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。 ことはできません`NULL`します。  
  
 [入力] `rect`  
 カラー バー コントロールを描画する場所を指定する外接する四角形。  
  
 [入力] `nID`  
 コントロールの id。  
  
 [入力] `nColumns`  
 カラー バー コントロールの列の最適な数です。 このメソッドは、指定されたカラー パレットに合わせて列数を変更します。 既定値は、-1 で、このパラメーターが指定されていないことを意味します。  
  
 [入力] `pPalette`  
 色のパレットへのポインターまたは`NULL`です。 このパラメーターは場合`NULL`、20 の色を指定した場合と、このメソッドは、カラー バー コントロールのサイズを計算します。 既定値は、`NULL` です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、 `rect`、 `nColumns`、および`pPalette`適切な数または行数とカラー バー コントロールと、呼び出しの列を計算するパラメーター、 [CMFCColorBar::Create](#create)メソッドです。  
  
##  <a name="createpalette"></a>CMFCColorBar::CreatePalette  
 色の配列の指定した色とパレットを初期化します。  
  
```  
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,   
    CPalette& palette);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `arColors`|色の配列。|  
|[入力] `palette`|色パレット。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合、`FALSE`です。  
  
##  <a name="enableautomaticbutton"></a>CMFCColorBar::EnableAutomaticButton  
 自動のボタンの表示と非表示を切り替えます。  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 テキスト ラベル、*自動*(既定) の色のボタン、または`NULL`です。  
  
 自動のボタンの標準のラベルは**自動**です。  
  
 [入力] `colorAutomatic`  
 クリックすると、自動的に適用される既定の色。  
  
 [入力] `bEnable`  
 `TRUE`自動ボタンを有効にするには`FALSE`自動ボタンを無効にします。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
 場合に、[自動] ボタンのテキスト ラベルが削除された、`lpszLabel`パラメーターは`NULL`または`bEnable`パラメーターは`FALSE`です。  
  
##  <a name="enableotherbutton"></a>CMFCColorBar::EnableOtherButton  
 有効またはユーザーが他の色を選択できるダイアログ ボックスの表示を無効にします。  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 テキスト ラベル、*他の*ボタンを他の色を表示、または`NULL`です。  
  
 このボタンは、標準のラベルは**他の色。**.  
  
 [入力] `bAltColorDlg`  
 `TRUE`表示する、 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  ダイアログ ボックス`FALSE`標準を表示する[CColorDialog](../../mfc/reference/ccolordialog-class.md)  ダイアログ ボックス。 既定値は `TRUE` です。  
  
 [入力] `bEnable`  
 `TRUE`ボタンを有効にするには`FALSE`ボタンを無効にします。 既定値は `TRUE` です。  
  
##  <a name="getcolor"></a>CMFCColorBar::GetColor  
 現在選択されている色を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されている色です。  
  
##  <a name="getcolorgridsize"></a>CMFCColorBar::GetColorGridSize  
 カラー バー コントロールのグリッドの行と列の数を計算します。  
  
```  
CSize GetColorGridSize(BOOL bVertDock) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `bVertDock`|`TRUE`垂直方向にドッキングされたカラー バー コントロールであるため、計算を実行するにはそれ以外の場合、水平方向にドッキングされたコントロールの計算を実行します。|  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト`cx`コンポーネントには、列と元の数が含まれている`cy`コンポーネントには、行の数が含まれています。  
  
##  <a name="getcommandid"></a>CMFCColorBar::GetCommandID  
 現在のカラー バー コントロールのコマンド ID を取得します。  
  
```  
UINT GetCommandID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コマンド id。  
  
### <a name="remarks"></a>コメント  
 フレームワークがコマンド ID を送信するユーザーは、新しい色を選択するときに、`WM_COMMAND`の親に通知するメッセージ、`CMFCColorBar`オブジェクトです。  
  
##  <a name="getextraheight"></a>CMFCColorBar::GetExtraHeight  
 現在のカラー バーがなど、その他のユーザー インターフェイス要素を表示するために必要な追加の高さを計算、**他の**ボタンやドキュメントの色。  
  
```  
int GetExtraHeight(int nNumColumns) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nNumColumns`|場合は、カラー バー コントロールには、ドキュメントの色、ドキュメントの色のグリッドに表示する列の数が含まれています。 それ以外の場合、この値は使用されません。|  
  
### <a name="return-value"></a>戻り値  
 必要な計算される追加の高さ。  
  
##  <a name="gethighlightedcolor"></a>CMFCColorBar::GetHighlightedColor  
 色のボタンにフォーカスを示す色を取得します。たとえば、ボタンは*ホット*します。  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gethorzmargin"></a>CMFCColorBar::GetHorzMargin  
 水平右のマージンを取得します。  
  
```  
int GetHorzMargin();
```  
  
### <a name="return-value"></a>戻り値  
 水平方向の余白。  
  
##  <a name="getvertmargin"></a>CMFCColorBar::GetVertMargin  
 上部または下部にある色のセルとクライアント領域の境界間のスペースは、縦方向のマージンを取得します。  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>戻り値  
 垂直方向の余白。  
  
##  <a name="initcolors"></a>CMFCColorBar::InitColors  
 指定したパレットの色、またはシステムの既定のパレットの色の配列を初期化します。  
  
```  
static int InitColors(
    CPalette* pPalette,   
    CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pPalette`|パレット オブジェクトへのポインターまたは`NULL`です。 このパラメーターは場合`NULL`、このメソッドは、オペレーティング システムの既定のパレットを使用します。|  
|[入力] `arColors`|色の配列。|  
  
### <a name="return-value"></a>戻り値  
 色の配列内の要素の数。  
  
##  <a name="istearoff"></a>CMFCColorBar::IsTearOff  
 現在のカラー バーがドッキング可能かどうかを示します。  
  
```  
BOOL IsTearOff() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`現在のカラー バー コントロールがドッキング可能の場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 カラー バー コントロールがドッキング可能な場合は、それは、コントロール バーから切り離してし、別の場所にドッキングされていることができます。  
  
##  <a name="onkey"></a>CMFCColorBar::OnKey  
 ユーザーがキーボード ボタンを押したときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nChar`  
 ユーザーが押したキーの仮想キー コードです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドは、指定したキーを処理する場合それ以外の場合、`FALSE`です。  
  
##  <a name="onsendcommand"></a>CMFCColorBar::OnSendCommand  
 ポップアップ コントロールの階層構造を閉じるために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pButton`|ツールバーにあるコントロールへのポインター。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合、`FALSE`です。  
  
##  <a name="onupdatecmdui"></a>CMFCColorBar::OnUpdateCmdUI  
 有効にするか、アイテムを表示する前に、カラー バー コントロールのユーザー インターフェイス項目を無効にするためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTarget`  
 更新するユーザー インターフェイス項目を含むウィンドウへのポインター。  
  
 [入力] `bDisableIfNoHndler`  
 `TRUE`場合もハンドラーは、ユーザー インターフェイス項目を無効にするのには、メッセージ マップで定義されています。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 かどうかが表示されることが有効になっていると、項目が知る必要があります、アプリケーションのユーザーには、ユーザー インターフェイスの項目がクリックすると、または無効にします。 コマンド メッセージのターゲット実装することでこの情報を提供する、`ON_UPDATE_COMMAND_UI`コマンド ハンドラーです。 このメソッドを使用すると、コマンドを処理できます。 詳細については、次を参照してください。 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)します。  
  
##  <a name="opencolordialog"></a>CMFCColorBar::OpenColorDialog  
 色のダイアログ ボックスが開きます。  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `colorDefault`  
 色のダイアログ ボックスが開いたときに、既定で選択されている色です。  
  
 [出力] `colorRes`  
 ユーザーが選択した色です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ユーザーが、色を選択した場合`FALSE`場合は、ユーザーが色のダイアログ ボックスをキャンセルします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="rebuild"></a>CMFCColorBar::Rebuild  
 カラー バー コントロールを完全に再描画します。  
  
```  
virtual void Rebuild();
```  
  
##  <a name="selectpalette"></a>CMFCColorBar::SelectPalette  
 現在のカラー バー コントロールの親ボタンのパレットを指定したデバイス コンテキストの論理パレットを設定します。  
  
```  
CPalette* SelectPalette(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pDC`|現在のカラー バー コントロールの親ボタンのデバイス コンテキストへのポインター。|  
  
### <a name="return-value"></a>戻り値  
 現在のカラー バー コントロールの親のボタンのパレットで置換されるパレットへのポインター。  
  
##  <a name="setcolor"></a>CMFCColorBar::SetColor  
 現在選択されている色を設定します。  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 RGB 色の値。  
  
##  <a name="setcolorname"></a>CMFCColorBar::SetColorName  
 指定した色の新しい名前を設定します。  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 色の RGB 値。  
  
 [入力] `strName`  
 指定した色の新しい名前。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、すべてのページで指定された色の名前を変更`CMFCColorBar`アプリケーション内のオブジェクト。  
  
##  <a name="setcommandid"></a>CMFCColorBar::SetCommandID  
 カラー バー コントロールの新しいコマンド ID を設定します。  
  
```  
void SetCommandID(UINT nCommandID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nCommandID`  
 コマンド id。  
  
### <a name="remarks"></a>コメント  
 カラー バー コントロールのコマンド ID を変更して、ID が変更されたコントロールの親ウィンドウを通知するため、このメソッドを呼び出します。  
  
##  <a name="setdocumentcolors"></a>CMFCColorBar::SetDocumentColors  
 現在のドキュメントで使用される色の一覧を設定します。  
  
```  
void SetDocumentColors(
    LPCTSTR lpszCaption,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    BOOL bShowWhenDocked=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszCaption`  
 カラー バー コントロールがドッキングされていないときに表示されるキャプション。  
  
 [入力] `lstDocColors`  
 現在のドキュメントの色を置換する色の一覧です。  
  
 [入力] `bShowWhenDocked`  
 `TRUE`カラー バー コントロールがドッキングしているときに、ドキュメントの色を表示するにはそれ以外の場合、`FALSE`です。 既定値は `FALSE` です。  
  
### <a name="remarks"></a>コメント  
 *色を文書化*は現在ドキュメントで使用される色。 フレームワークが自動的にドキュメントの色の一覧を保持しますが、このメソッドを使用してリストを変更することができます。  
  
##  <a name="sethorzmargin"></a>CMFCColorBar::SetHorzMargin  
 左または適切な色のセルに、クライアント領域の境界間の空白は、水平方向の余白を設定します。  
  
```  
void SetHorzMargin(int nHorzMargin);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nHorzMargin`  
 水平方向の余白 (ピクセル)。  
  
### <a name="remarks"></a>コメント  
 既定では、 [CMFCColorBar::CMFCColorBar](#cmfccolorbar)コンス トラクターは、4 ピクセルに横方向の余白を設定します。  
  
##  <a name="setproplist"></a>CMFCColorBar::SetPropList  
 セット、`m_pWndPropList`プロパティ グリッド コントロールを指すポインターを指定するデータ メンバーを保護します。  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pWndList`|プロパティ グリッド コントロール オブジェクトへのポインター。|  
  
##  <a name="setvertmargin"></a>CMFCColorBar::SetVertMargin  
 上位または下位のカラー セルとクライアント領域の境界間のスペースは、縦方向のマージンを設定します。  
  
```  
void SetVertMargin(int nVertMargin);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nVertMargin`  
 垂直方向の余白 (ピクセル)。  
  
### <a name="remarks"></a>コメント  
 既定では、 [CMFCColorBar::CMFCColorBar](#cmfccolorbar)コンス トラクターは、4 ピクセルに縦方向の余白を設定します。  
  
##  <a name="showcommandmessagestring"></a>CMFCColorBar::ShowCommandMessageString  
 ステータス バーにメッセージ行を更新するカラー バー コントロールを所有するフレーム ウィンドウを要求します。  
  
```  
virtual void ShowCommandMessageString(UINT uiCmdId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdId`  
 コマンド id。 (このパラメーターが無視されます)  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、`WM_SETMESSAGESTRING`メッセージ カラー バー コントロールの所有者にします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

