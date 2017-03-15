---
title: "CSliderCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSliderCtrl
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CSliderCtrl
- slider controls, CSliderCtrl class
- CSliderCtrl class, common controls
- CSliderCtrl class
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
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
ms.openlocfilehash: 0d024c7d6670ff3b7a94b9657151e7bf1958d5f1
ms.lasthandoff: 02/24/2017

---
# <a name="csliderctrl-class"></a>CSliderCtrl クラス
Windows コモン スライダー コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|`CSliderCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](#clearsel)|スライダー コントロールの現在の選択をクリアします。|  
|[CSliderCtrl::ClearTics](#cleartics)|スライダー コントロールから現在の目盛りを削除します。|  
|[CSliderCtrl::Create](#create)|スライダー コントロールを作成し、それをアタッチ、`CSliderCtrl`オブジェクトです。|  
|[CSliderCtrl::CreateEx](#createex)|指定された Windows 拡張スタイルでスライダー コントロールを作成し、結び付けます、`CSliderCtrl`オブジェクトです。|  
|[CSliderCtrl::GetBuddy](#getbuddy)|指定の場所にスライダー コントロールの関連ウィンドウへのハンドルを取得します。|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|スライダー コントロールのチャネルのサイズを取得します。|  
|[CSliderCtrl::GetLineSize](#getlinesize)|スライダー コントロールの行のサイズを取得します。|  
|[CSliderCtrl::GetNumTics](#getnumtics)|スライダー コントロールの目盛りの数を取得します。|  
|[CSliderCtrl::GetPageSize](#getpagesize)|スライダー コントロールのページ サイズを取得します。|  
|[CSliderCtrl::GetPos](#getpos)|スライダーの現在位置を取得します。|  
|[CSliderCtrl::GetRange](#getrange)|スライダーの最小値と最大の位置を取得します。|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|スライダーの最大の位置を取得します。|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|スライダーの最小の位置を取得します。|  
|[CSliderCtrl::GetSelection](#getselection)|現在の選択範囲を取得します。|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|現在のトラック バー コントロールのスライダーの長さを取得します。|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|スライダー コントロールのつまみのサイズを取得します。|  
|[CSliderCtrl::GetTic](#gettic)|指定された目盛りの位置を取得します。|  
|[CSliderCtrl::GetTicArray](#getticarray)|スライダー コントロールの目盛りの位置の配列を取得します。|  
|[CSliderCtrl::GetTicPos](#getticpos)|クライアント座標で指定された目盛りの位置を取得します。|  
|[CSliderCtrl::GetToolTips](#gettooltips)|存在する場合は、スライダー コントロールに割り当てられているツールヒント コントロールへのハンドルを取得します。|  
|[CSliderCtrl::SetBuddy](#setbuddy)|スライダー コントロールの関連ウィンドウとして、ウィンドウを割り当てます。|  
|[CSliderCtrl::SetLineSize](#setlinesize)|スライダー コントロールの行のサイズを設定します。|  
|[CSliderCtrl::SetPageSize](#setpagesize)|スライダー コントロールのページ サイズを設定します。|  
|[CSliderCtrl::SetPos](#setpos)|スライダーの現在位置を設定します。|  
|[CSliderCtrl::SetRange](#setrange)|スライダーの最小値と最大の位置を設定します。|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|スライダーの最大の位置を設定します。|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|スライダーの最小の位置を設定します。|  
|[CSliderCtrl::SetSelection](#setselection)|現在の選択範囲を設定します。|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|現在のトラック バー コントロールのスライダーの長さを設定します。|  
|[CSliderCtrl::SetTic](#settic)|指定された目盛りの位置を設定します。|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|スライダー コントロールの増分ごとに目盛りの間隔を設定します。|  
|[CSliderCtrl::SetTipSide](#settipside)|Trackbar コントロールで使用されるツール ヒント コントロールを位置。|  
|[CSliderCtrl::SetToolTips](#settooltips)|スライダー コントロールにツールヒント コントロールを割り当てます。|  
  
## <a name="remarks"></a>コメント  
 「つまみ」(trackbar とも呼ばれます) は、スライダーと省略可能な目盛りを含むウィンドウ。 ユーザーは、マウスまたは方向キーを使用して、スライダーを移動したとき、コントロールは、変更を示す通知メッセージを送信します。  
  
 スライダー コントロールは、ユーザーが範囲内の不連続値または一連の連続するいくつかの値を選択する場合に便利です。 たとえば、特定の目盛りをスライダーを移動して、キーボードのリピート間隔を設定するのにユーザーを許可するように、スライダー コントロールを使用できます。  
  
 このコントロール (つまり、`CSliderCtrl`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。  
  
 スライダーは、作成するときに指定した単位で移動します。 たとえば、スライダーが&5; つの範囲を持つことを指定する場合、スライダー&6; つの位置: スライダー コントロールと各インクリメントの範囲内の&1; つの位置の左側に位置します。 通常、これらの各位置は目盛りによって識別されます。  
  
 コンス トラクターを使用して、スライダーを作成して、**作成**のメンバー関数`CSliderCtrl`します。 スライダー コントロールを作成した後にメンバー関数を使用することができます`CSliderCtrl`多くのプロパティを変更します。 可能な変更には、スライダーの最小値と最大の位置を設定、目盛りを描画、選択範囲の設定、スライダーの位置が含まれます。  
  
 使用する方法について`CSliderCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CSliderCtrl](../../mfc/using-csliderctrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="a-nameclearsela--csliderctrlclearsel"></a><a name="clearsel"></a>CSliderCtrl::ClearSel  
 スライダー コントロールの現在の選択をクリアします。  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRedraw`  
 フラグを再描画します。 このパラメーターは、する場合**TRUE**スライダーを再描画すると、選択がクリアされた後、それ以外の場合、スライダーが再描画されません。  
  
##  <a name="a-nameclearticsa--csliderctrlcleartics"></a><a name="cleartics"></a>CSliderCtrl::ClearTics  
 スライダー コントロールから現在の目盛りを削除します。  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRedraw`  
 フラグを再描画します。 このパラメーターは、する場合**TRUE**目盛りがクリアされた後、スライダーが再描画される。 それ以外の場合、スライダーが再描画されません。  
  
##  <a name="a-namecreatea--csliderctrlcreate"></a><a name="create"></a>CSliderCtrl::Create  
 スライダー コントロールを作成し、それをアタッチ、`CSliderCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 スライダー コントロールのスタイルを指定します。 任意の組み合わせを適用[スライダー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)に記述されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]コントロールにします。  
  
 `rect`  
 スライダー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 `pParentWnd`  
 通常、スライダー コントロールの親ウィンドウを指定する`CDialog`です。 ことはできません**NULL**します。  
  
 `nID`  
 スライダー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、`CSliderCtrl`で&2; つの手順を実行します。 最初に、コンス トラクターを呼び出すし、し、呼び出す**作成**、スライダー コントロールを作成およびそれにアタッチする、`CSliderCtrl`オブジェクトです。  
  
 設定される値に応じて`dwStyle`、スライダー コントロールが水平または垂直の方向を持つことができます。 いずれかの側では、目盛りが持てる側、またはどちらもします。 連続した値の範囲を指定することにも使用できます。  
  
 スライダー コントロールに拡張ウィンドウ スタイルを適用するには、呼び出す[CreateEx](#createex)の代わりに**作成**します。  
  
##  <a name="a-namecreateexa--csliderctrlcreateex"></a><a name="createex"></a>CSliderCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けます、`CSliderCtrl`オブジェクトです。  
  
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
 スライダー コントロールのスタイルを指定します。 任意の組み合わせを適用[スライダー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)に記述されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]コントロールにします。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに[作成](#create)、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="a-namecsliderctrla--csliderctrlcsliderctrl"></a><a name="csliderctrl"></a>CSliderCtrl::CSliderCtrl  
 `CSliderCtrl` オブジェクトを構築します。  
  
```  
CSliderCtrl();
```  
  
##  <a name="a-namegetbuddya--csliderctrlgetbuddy"></a><a name="getbuddy"></a>CSliderCtrl::GetBuddy  
 指定の場所にスライダー コントロールの関連ウィンドウへのハンドルを取得します。  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `fLocation`  
 2 つの関連ウィンドウ ハンドルを取得するを示すブール値。 次のいずれかの値になります。  
  
- **TRUE**スライダーの左側にある関連ウィンドウ ハンドルを取得します。 スライダー コントロールを使用している場合、`TBS_VERT`スタイル、スライダーの上にある関連メッセージを取得します。  
  
- **FALSE**スライダーの右側にある関連ウィンドウ ハンドルを取得します。 スライダー コントロールを使用している場合、`TBS_VERT`スタイル、スライダーを下にある関連メッセージを取得します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)で指定された位置にある関連ウィンドウにあるオブジェクトを`fLocation`、または**NULL**関連ウィンドウがその場所に存在しない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TBM_GETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760178)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 スライダー コントロールのスタイルについては、次を参照してください。 [Trackbar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetchannelrecta--csliderctrlgetchannelrect"></a><a name="getchannelrect"></a>CSliderCtrl::GetChannelRect  
 スライダー コントロールのチャネルの外接する四角形の位置とサイズを取得します。  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lprc`  
 ポインター、 [CRect](../../atl-mfc-shared/reference/crect-class.md)サイズと、チャネルの位置を含むオブジェクトの外接する四角形、関数が返す場合。  
  
### <a name="remarks"></a>コメント  
 チャネルは、スライダーが移動すると、範囲を選択すると、強調表示を含む領域です。  
  
##  <a name="a-namegetlinesizea--csliderctrlgetlinesize"></a><a name="getlinesize"></a>CSliderCtrl::GetLineSize  
 スライダー コントロールの行のサイズを取得します。  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールの行のサイズ。  
  
### <a name="remarks"></a>コメント  
 行サイズに影響をどの程度スライダーが移動、 **TB_LINEUP**と**TB_LINEDOWN**通知します。 行サイズの既定の設定は 1 です。  
  
##  <a name="a-namegetnumticsa--csliderctrlgetnumtics"></a><a name="getnumtics"></a>CSliderCtrl::GetNumTics  
 スライダー コントロールの目盛りの数を取得します。  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールの目盛りの数。  
  
##  <a name="a-namegetpagesizea--csliderctrlgetpagesize"></a><a name="getpagesize"></a>CSliderCtrl::GetPageSize  
 スライダー コントロールのページのサイズを取得します。  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールのページのサイズ。  
  
### <a name="remarks"></a>コメント  
 ページ サイズに影響をどの程度スライダーが移動、 **TB_PAGEUP**と**TB_PAGEDOWN**通知します。  
  
##  <a name="a-namegetposa--csliderctrlgetpos"></a><a name="getpos"></a>CSliderCtrl::GetPos  
 スライダー コントロールのスライダーの現在位置を取得します。  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在位置を返します。  
  
##  <a name="a-namegetrangea--csliderctrlgetrange"></a><a name="getrange"></a>CSliderCtrl::GetRange  
 スライダー コントロールのスライダーの最大値と最小の位置を取得します。  
  
```  
void GetRange(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nMin`  
 最小の位置を受け取る整数への参照。  
  
 `nMax`  
 最大の位置を受け取る整数への参照。  
  
### <a name="remarks"></a>コメント  
 この関数にによって参照される整数型に値をコピーする`nMin`と`nMax`です。  
  
##  <a name="a-namegetrangemaxa--csliderctrlgetrangemax"></a><a name="getrangemax"></a>CSliderCtrl::GetRangeMax  
 スライダー コントロールのスライダーの最大の位置を取得します。  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールの最大の位置。  
  
##  <a name="a-namegetrangemina--csliderctrlgetrangemin"></a><a name="getrangemin"></a>CSliderCtrl::GetRangeMin  
 スライダー コントロールのスライダーの最小の位置を取得します。  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールの最小の位置。  
  
##  <a name="a-namegetselectiona--csliderctrlgetselection"></a><a name="getselection"></a>CSliderCtrl::GetSelection  
 スライダー コントロールの現在の選択範囲の開始と終了位置を取得します。  
  
```  
void GetSelection(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nMin`  
 現在の選択範囲の開始位置を受け取る整数への参照。  
  
 `nMax`  
 現在の選択範囲の終了位置を受け取る整数への参照。  
  
##  <a name="a-namegetthumblengtha--csliderctrlgetthumblength"></a><a name="getthumblength"></a>CSliderCtrl::GetThumbLength  
 現在のトラック バー コントロールのスライダーの長さを取得します。  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、スライダーの長さ。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TBM_GETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760201)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetthumbrecta--csliderctrlgetthumbrect"></a><a name="getthumbrect"></a>CSliderCtrl::GetThumbRect  
 スライダー コントロールのスライダー (つまみ) に外接する四角形の位置とサイズを取得します。  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lprc`  
 ポインター、`CRect`関数が返す場合は、スライダーの外接する四角形を格納しているオブジェクト。  
  
##  <a name="a-namegettica--csliderctrlgettic"></a><a name="gettic"></a>CSliderCtrl::GetTic  
 スライダー コントロールの目盛りの位置を取得します。  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nTic`  
 チェック マークを識別する&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定された目盛りまたは場合は、1 の位置`nTic`有効なインデックスが指定されていません。  
  
##  <a name="a-namegetticarraya--csliderctrlgetticarray"></a><a name="getticarray"></a>CSliderCtrl::GetTicArray  
 スライダー コントロールの目盛りの位置を格納する配列のアドレスを取得します。  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールの目盛りの位置を格納する配列のアドレスです。  
  
##  <a name="a-namegetticposa--csliderctrlgetticpos"></a><a name="getticpos"></a>CSliderCtrl::GetTicPos  
 ティックのスライダー コントロール内の物理の現在位置を取得します。  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nTic`  
 チェック マークを識別する&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定された目盛りまたは 1 の場合のクライアント座標で物理的な位置。`nTic`有効なインデックスが指定されていません。  
  
##  <a name="a-namegettooltipsa--csliderctrlgettooltips"></a><a name="gettooltips"></a>CSliderCtrl::GetToolTips  
 存在する場合は、スライダー コントロールに割り当てられているツールヒント コントロールへのハンドルを取得します。  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)オブジェクト、または**NULL**ツール ヒントが使用されていない場合。 スライダー コントロールを使用しない場合、 **TBS_TOOLTIPS**スタイル、戻り値は、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TBM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760209)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このメンバー関数が返す注、`CToolTipCtrl`コントロールへのハンドルではなくオブジェクトです。  
  
 スライダー コントロールのスタイルについては、次を参照してください。 [Trackbar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetbuddya--csliderctrlsetbuddy"></a><a name="setbuddy"></a>CSliderCtrl::SetBuddy  
 スライダー コントロールの関連ウィンドウとして、ウィンドウを割り当てます。  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndBuddy`  
 ポインター、`CWnd`スライダー コントロールのメンバーとして設定されるオブジェクト。  
  
 `fLocation`  
 関連ウィンドウを表示する位置を指定する値。 この値は、次のいずれかになります。  
  
- **TRUE** trackbar コントロールで使用する場合、トラック バーの左側に表示されます、`TBS_HORZ`スタイル。 トラック バーを使用している場合、`TBS_VERT`スタイルを trackbar コントロールの上に表示されます。  
  
- **FALSE** trackbar コントロールで使用する場合、トラック バーの右側に表示されます、`TBS_HORZ`スタイル。 トラック バーを使用している場合、`TBS_VERT`スタイルを trackbar コントロールの下に表示されます。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)その場所にあるスライダー コントロールに割り当てられているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TBM_SETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760213)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このメンバー関数へのポインターを使用して`CWnd`戻り値とパラメーターの両方のウィンドウ ハンドルではなく、オブジェクトです。  
  
 スライダー コントロールのスタイルについては、次を参照してください。 [Trackbar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetlinesizea--csliderctrlsetlinesize"></a><a name="setlinesize"></a>CSliderCtrl::SetLineSize  
 スライダー コントロールの行のサイズを設定します。  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSize`  
 スライダー コントロールの新しい行のサイズ。  
  
### <a name="return-value"></a>戻り値  
 前の行サイズ。  
  
### <a name="remarks"></a>コメント  
 行サイズに影響をどの程度スライダーが移動、 **TB_LINEUP**と**TB_LINEDOWN**通知します。  
  
##  <a name="a-namesetpagesizea--csliderctrlsetpagesize"></a><a name="setpagesize"></a>CSliderCtrl::SetPageSize  
 スライダー コントロールのページのサイズを設定します。  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSize`  
 スライダー コントロールの新しいページ サイズ。  
  
### <a name="return-value"></a>戻り値  
 前のページ サイズ。  
  
### <a name="remarks"></a>コメント  
 ページ サイズに影響をどの程度スライダーが移動、 **TB_PAGEUP**と**TB_PAGEDOWN**通知します。  
  
##  <a name="a-namesetposa--csliderctrlsetpos"></a><a name="setpos"></a>CSliderCtrl::SetPos  
 スライダー コントロールのスライダーの現在位置を設定します。  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 新しいスライダー位置を指定します。  
  
##  <a name="a-namesetrangea--csliderctrlsetrange"></a><a name="setrange"></a>CSliderCtrl::SetRange  
 スライダー コントロールのスライダーの範囲 (最小と最大の位置) を設定します。  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMin`  
 スライダーの最小の位置。  
  
 `nMax`  
 最大のスライダーの位置。  
  
 `bRedraw`  
 再描画フラグ。 このパラメーターは、する場合**TRUE**スライダーが再描画される範囲を設定した後、それ以外の場合、スライダーが再描画されません。  
  
##  <a name="a-namesetrangemaxa--csliderctrlsetrangemax"></a><a name="setrangemax"></a>CSliderCtrl::SetRangeMax  
 スライダー コントロールのスライダーの範囲の上限を設定します。  
  
```  
void SetRangeMax(
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMax`  
 最大のスライダーの位置。  
  
 `bRedraw`  
 再描画フラグ。 このパラメーターは、する場合**TRUE**スライダーが再描画される範囲を設定した後、それ以外の場合、スライダーが再描画されません。  
  
##  <a name="a-namesetrangemina--csliderctrlsetrangemin"></a><a name="setrangemin"></a>CSliderCtrl::SetRangeMin  
 スライダー コントロールのスライダーの最小の範囲を設定します。  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMin`  
 スライダーの最小の位置。  
  
 `bRedraw`  
 再描画フラグ。 このパラメーターは、する場合**TRUE**スライダーが再描画される範囲を設定した後、それ以外の場合、スライダーが再描画されません。  
  
##  <a name="a-namesetselectiona--csliderctrlsetselection"></a><a name="setselection"></a>CSliderCtrl::SetSelection  
 スライダー コントロールの現在の選択範囲の開始と終了位置を設定します。  
  
```  
void SetSelection(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMin`  
 スライダーの位置を開始しています。  
  
 `nMax`  
 スライダーの位置を終了しています。  
  
##  <a name="a-namesetthumblengtha--csliderctrlsetthumblength"></a><a name="setthumblength"></a>CSliderCtrl::SetThumbLength  
 現在のトラック バー コントロールのスライダーの長さを設定します。  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nLength`|ピクセル単位で、スライダーの長さです。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、トラック バー コントロールに設定されている必要があります[TBS_FIXEDLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760147)スタイル。  
  
 このメソッドは、送信、 [TBM_SETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760234)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_sliderCtrl`つまり、現在のトラック バー コントロールのアクセスに使用します。 変数にも定義`thumbLength`つまり、トラック バー コントロールのつまみのコンポーネントの既定の長さを格納するために使用します。 これらの変数は、次の例で使用されます。  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、トラック バー コントロールのつまみのコンポーネントを既定の長さ&2; 回に設定します。  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="a-namesettica--csliderctrlsettic"></a><a name="settic"></a>CSliderCtrl::SetTic  
 スライダー コントロールの目盛りの位置を設定します。  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>パラメーター  
 `nTic`  
 目盛りの位置。 このパラメーターは、正の値を指定する必要があります。  
  
### <a name="return-value"></a>戻り値  
 チェック マークが設定されている場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="a-namesetticfreqa--csliderctrlsetticfreq"></a><a name="setticfreq"></a>CSliderCtrl::SetTicFreq  
 スライダーの目盛りでマークの表示頻度を設定します。  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>パラメーター  
 *nFreq*  
 目盛りの頻度です。  
  
### <a name="remarks"></a>コメント  
 たとえば、頻度が 2 に設定されている場合、スライダーの範囲内の他のすべての増分の目盛りが表示されます。 頻度が 1 の既定の設定 (つまり、範囲のすべての増分値が目盛りに関連付けられて)。  
  
 持つコントロールを作成する必要があります、`TBS_AUTOTICKS`この関数を使用するスタイル。 詳細については、次を参照してください。 [CSliderCtrl::Create](#create)します。  
  
##  <a name="a-namesettipsidea--csliderctrlsettipside"></a><a name="settipside"></a>CSliderCtrl::SetTipSide  
 Trackbar コントロールで使用されるツール ヒント コントロールを位置。  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLocation`  
 Tooltip コントロールを表示する位置を表す値。 使用可能な値の一覧は、Win32 メッセージを参照してください。 [TBM_SETTIPSIDE](http://msdn.microsoft.com/library/windows/desktop/bb760240)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 ツール ヒント コントロールの前の位置を表す値。 戻り値に等しいに使用できる値のいずれかの`nLocation`です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して**TBM_SETTIPSIDE**」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 スライダー コントロールを使用して、 **TBS_TOOLTIPS**表示ツール ヒントのスタイルを設定します。 スライダー コントロールのスタイルについては、次を参照してください。 [Trackbar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)で、[!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
##  <a name="a-namesettooltipsa--csliderctrlsettooltips"></a><a name="settooltips"></a>CSliderCtrl::SetToolTips  
 スライダー コントロールにツールヒント コントロールを割り当てます。  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndTip`  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)スライダー コントロールで使用するツール ヒントを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TBM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760242)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 スライダー コントロールを作成すると、 **TBS_TOOLTIPS**スタイル、スライダーの現在の位置を表示するスライダーの横に表示される既定のツール ヒント コントロール作成します。 スライダー コントロールのスタイルについては、次を参照してください。 [Trackbar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)で、[!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl クラス](../../mfc/reference/cprogressctrl-class.md)

