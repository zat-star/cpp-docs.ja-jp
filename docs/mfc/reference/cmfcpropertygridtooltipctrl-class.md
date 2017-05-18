---
title: "CMFCPropertyGridToolTipCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl class
- CMFCPropertyGridToolTipCtrl class, destructor
- PreTranslateMessage method
- ~CMFCPropertyGridToolTipCtrl destructor
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
caps.latest.revision: 24
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
ms.openlocfilehash: e5290706799dcd253205ac74dad72cd7783d19dd
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl クラス
ツール ヒントを実装を制御する、 [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)を使用してツールヒントを表示します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|`CMFCPropertyGridToolTipCtrl` オブジェクトを構築します。|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCPropertyGridToolTipCtrl::Create](#create)|ツール ヒント コントロールのウィンドウを作成します。|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|非アクティブ化し、tooltip コントロールを非表示にします。|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|ツール ヒント コントロールの最後の位置の座標を返します。|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Tooltip コントロールを非表示にします。|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|クラスで使用される[CWinApp](../../mfc/reference/cwinapp-class.md)にディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 (上書き[CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage))。|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|ツールヒントのテキストと、ヒント ウィンドウの枠線の間隔を設定します。|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Tooltip コントロールが表示されます。|  
  
## <a name="remarks"></a>コメント  
 プロパティ名にポインターを合わせると、ツールヒントが表示されます。 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)クラスでは、ユーザーが読みやすいように、ツールヒントが表示されます。 通常、ツールヒントの位置は、ポインターの位置によって決まります。 このクラスを使用するは、ツールヒントは、プロパティの名前が表示され、プロパティ名が完全に表示されるように、本来のプロパティの拡張機能に似ています。  
  
 MFC は、自動的にこのコントロールを作成してでそれを使用して、 [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)します。  
  
## <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCPropertyGridToolTipCtrl`クラス、および tooltip コントロールを表示する方法です。  
  
 [!code-cpp[NVC_MFC_RibbonApp 第&23;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpropertygridtooltipctrl.h  
  
##  <a name="cmfcpropertygridtooltipctrl"></a>CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl  
 `CMFCPropertyGridToolTipCtrl` オブジェクトを構築します。  
  
```  
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```  
  
##  <a name="create"></a>CMFCPropertyGridToolTipCtrl::Create  
 ツール ヒント コントロールのウィンドウを作成します。  
  
```  
BOOL Create(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 親ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが作成された場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="deactivate"></a>CMFCPropertyGridToolTipCtrl::Deactivate  
 非アクティブ化し、tooltip コントロールを非表示にします。  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドの最後の位置とテキストに設定の空白値ように呼び出しを将来[CMFCPropertyGridToolTipCtrl::Track](#track)ツールヒントを表示します。  
  
##  <a name="getlastrect"></a>CMFCPropertyGridToolTipCtrl::GetLastRect  
 ツール ヒント コントロールの最後の位置の座標を返します。  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rect`  
 ツール ヒント コントロールの最後の位置が含まれています。  
  
##  <a name="hide"></a>CMFCPropertyGridToolTipCtrl::Hide  
 Tooltip コントロールを非表示にします。  
  
```  
void Hide();
```  
  
##  <a name="settextmargin"></a>CMFCPropertyGridToolTipCtrl::SetTextMargin  
 ツールヒントのテキストと、ヒント ウィンドウの枠線の間隔を設定します。  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTextMargin`  
 ツール ヒント コントロールのテキストと、ヒント ウィンドウの枠線の間隔を指定します。 既定値は、10 ピクセルです。  
  
##  <a name="track"></a>CMFCPropertyGridToolTipCtrl::Track  
 Tooltip コントロールが表示されます。  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 ツール ヒント コントロールのサイズと位置を指定します。  
  
 [入力] `strText`  
 ツール ヒントに表示されるテキストを指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定されたサイズと位置で tooltip コントロールを表示する`rect`です。 位置、サイズ、およびテキストが変わらない場合前回このメソッドが呼び出された後、このメソッドは影響を与えません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

