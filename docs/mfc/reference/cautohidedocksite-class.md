---
title: "CAutoHideDockSite クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoHideDockSite
- AllowShowOnPaneMenu
- CAutoHideDockSite::AllowShowOnPaneMenu
- CAutoHideDockSite.AllowShowOnPaneMenu
dev_langs:
- C++
helpviewer_keywords:
- AllowShowOnPaneMenu method
- CAutoHideDockSite class
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: 32
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
ms.openlocfilehash: 58beaa382a2ef04cfaee0fbcf63b9eef36831472
ms.lasthandoff: 02/24/2017

---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite クラス
`CAutoHideDockSite`拡張、 [CDockSite クラス](../../mfc/reference/cdocksite-class.md)自動非表示のドッキング ペインを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CAutoHideDockSite::CAutoHideDockSite`|
          `CAutoHideDockSite` オブジェクトを構築します。|  
|`CAutoHideDockSite::~CAutoHideDockSite`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|示すかどうか、`CAutoHideDockSite`ウィンドウのメニューに表示されます。|  
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|基本ペインのオブジェクトがから派生するかどうかを確認、 [CMFCAutoHideBar クラス](../../mfc/reference/cmfcautohidebar-class.md)します。|  
|[CAutoHideDockSite::DockPane](#dockpane)|このペインをドッキング`CAuotHideDockSite`オブジェクトです。|  
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|画面座標でドッキング サイトのサイズを取得します。|  
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|上ペインを再描画、`CAutoHideDockSite`グローバル余白とボタン間のスペースを使用します。|  
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|ドッキング バーの左側にある余白を設定します。|  
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|ドッキング バーの右側にある余白を設定します。|  
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|呼び出し[CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode)上のオブジェクトに対して、`CAutoHideDockSite`です。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|ツールバーとドッキング バーの端との間隔のサイズを定義します。 この領域は、左端、またはドッキング領域の配置に応じて、上端から測定されます。|  
  
## <a name="remarks"></a>コメント  
 呼び出すと[CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)、フレームワークによって自動的に作成、`CAutoHideDockSite`オブジェクトです。 ほとんどの場合、インスタンス化、またはこのクラスを直接使用することはできません。  
  
 ドッキング バーがドッキング ペインの左側にあるとの左側にある溝を埋めて、 [CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="example"></a>例  
 次の例では、取得、`CAutoHideDockSite`オブジェクトから、`CMFCAutoHideBar`オブジェクト、およびドッキング バーの左と右の余白を設定する方法です。  
  
 [!code-cpp[NVC_MFC_RibbonApp #&29;](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxautohidedocksite.h  
  
##  <a name="a-namecanacceptpanea--cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a>CAutoHideDockSite::CanAcceptPane  
 基本のペインがあるかどうかを判断、 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)から派生したオブジェクト、または`CMFCAutoHideBar`です。  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pBar`|フレームワークがテストする基本のウィンドウ。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合`pBar`から派生した`CMFCAutoHideBar`です。`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 基本ウィンドウ オブジェクトの派生元場合`CMFCAutoHideBar`、含めることができます、`CAutoHideDockSite`です。  
  
##  <a name="a-namedockpanea--cautohidedocksitedockpane"></a><a name="dockpane"></a>CAutoHideDockSite::DockPane  
 このペインをドッキング[CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)オブジェクトです。  
  
```  
virtual void DockPane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod,  
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pWnd`|フレームワークをドッキングするウィンドウ。|  
|[入力] `dockMethod`|ウィンドウのオプションをドッキングします。|  
|[入力] `lpRect`|ドッキング ウィンドウの境界を指定する四角形。|  
  
### <a name="remarks"></a>コメント  
 既定の実装がパラメーターを使用しない`dockMethod`、将来使用するために提供されています。  
  
 場合`lpRect`は`NULL`フレームワークは、ドッキング サイトの既定の場所に、ウィンドウを配置します。 ドッキング サイトが水平方向の場合は、既定の場所は、ドッキング サイトの一番左にあるです。 それ以外の場合、既定の場所は、ドッキング サイトの上部には。  
  
##  <a name="a-namegetalignrecta--cautohidedocksitegetalignrect"></a><a name="getalignrect"></a>CAutoHideDockSite::GetAlignRect  
 画面座標でドッキング サイトのサイズを取得します。  
  
```  
void GetAlignRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `rect`|四角形への参照。 メソッドは、この四角形にドッキング サイトのサイズを格納します。|  
  
### <a name="remarks"></a>コメント  
 四角形は、含まれていないようにオフセット余白が調整されます。  
  
##  <a name="a-namemnextraspacea--cautohidedocksitemnextraspace"></a><a name="m_nextraspace"></a>CAutoHideDockSite::m_nExtraSpace  
 境界間の領域のサイズ、 [CAutoHideDockSite クラス](../../mfc/reference/cautohidedocksite-class.md)と[CMFCAutoHideBar クラス](../../mfc/reference/cmfcautohidebar-class.md)オブジェクトです。  
  
```  
static int m_nExtraSpace;  
```  
  
### <a name="remarks"></a>コメント  
 ときに、`CMFCAutoHideBar`にドッキングされている場合は、 `CAutoHideDockSite`、全体のドッキング サイトを占有する必要があります。 このグローバル変数の左端または上端境界線間の余白を制御する、`CMFCAutoHideBar`と、対応する`CAutoHideDockSite`エッジです。 上または左のエッジを使用するかどうかは、現在の配置によって異なります。  
  
##  <a name="a-namesetoffsetlefta--cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a>CAutoHideDockSite::SetOffsetLeft  
 ドッキング バーの左側にある余白を設定します。  
  
```  
void SetOffsetLeft(int nOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 新しい位置のオフセット。  
  
### <a name="remarks"></a>コメント  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)オブジェクトが静的に配置されている、`CAutoHideDockSite`オブジェクトです。 つまり、ユーザーは、の場所に手動で変更できません`CMFCAutoHideBar`オブジェクトです。 `SetOffsetLeft`メソッドは、一番左の左側にある間の間隔を制御`CMFCAutoHideBar`およびの左側にある、`CAutoHideDockSite`です。  
  
##  <a name="a-namesetoffsetrighta--cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a>CAutoHideDockSite::SetOffsetRight  
 ドッキング バーの右側にある余白を設定します。  
  
```  
void SetOffsetRight(int nOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 新しい位置のオフセット。  
  
### <a name="remarks"></a>コメント  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)オブジェクトが静的に配置されている、`CAutoHideDockSite`オブジェクトです。 つまり、ユーザーがの場所を手動で変更できないこと、`CMFCAutoHideBar`オブジェクトです。 `SetOffsetRight`メソッドは、最も右側の右側にある間の間隔を制御`CMFCAutoHideBar`およびの右側にある、`CAutoHideDockSite`です。  
  
##  <a name="a-namerepositionpanesa--cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a>CAutoHideDockSite::RepositionPanes  
 上ペインを再描画、 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)します。  
  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `rectNewClientArea`|予約済みの値。|  
  
### <a name="remarks"></a>コメント  
 既定の実装を使わない`rectNewClientArea`します。 [グローバル] ツールバーの余白とボタン間のスペースを使用して、ペインが再描画します。  
  
##  <a name="a-nameunsetautohidemodea--cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a>CAutoHideDockSite::UnSetAutoHideMode  
 呼び出し[CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode)ドッキング サイト上のオブジェクト。  
  
```  
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pAutoHideToolbar`|ポインター、 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)上にある [オブジェクト] ペイン、`CAutoHideDockSite`です。|  
  
### <a name="remarks"></a>コメント  
 このメソッドを含む行を検索`pAutoHideToolbar`します。 呼び出す`CMFCAutoHideBar.UnSetAutoHideMode`すべてに対して、`CMFCAutoHideBar`その行にオブジェクトです。 場合`pAutoHideToolbar`が見つからないか、 `NULL`、このメソッドを呼び出す`CMFCAutoHideBar.UnSetAutoHideMode`すべて、`CMFCAutoHideBar`でオブジェクトを`CAutoHideDockSite`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockSite クラス](../../mfc/reference/cdocksite-class.md)

