---
title: "CMFCDragFrameImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CMFCDragFrameImpl
dev_langs: C++
helpviewer_keywords: CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 580b7a2eb320542223b0c19d18a8401ad3778e40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl クラス
`CMFCDragFrameImpl`クラスは、ユーザーが標準ドッキング モードのペインをドラッグしたときに表示されるドラッグ四角形を描画します。  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
## <a name="syntax"></a>構文  
  
```  
class CMFCDragFrameImpl  
```  
  
## <a name="remarks"></a>コメント  
 このクラスのオブジェクトがそれぞれに埋め込まれた[CPane クラス](../../mfc/reference/cpane-class.md)オブジェクト。 したがって、されるそれぞれのウィンドウを使用して、`CanFloat`メソッドが、ユーザーがドラッグしたときに、ドラッグ四角形を表示します。  
  
 使用してドラッグ四角形の幅を制御する [AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat]--brokenlink--(afx-global-data-structure.md#m_ndragframethicknessfloat) と[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock).  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdragframeimpl.h  
  
##  <a name="enddrawdragframe"></a>CMFCDragFrameImpl::EndDrawDragFrame  

  
```  
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bClearInternalRects`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="init"></a>CMFCDragFrameImpl::Init  

  
```  
void Init(CWnd* pDraggedWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDraggedWnd`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="movedragframe"></a>CMFCDragFrameImpl::MoveDragFrame  

  
```  
void MoveDragFrame(BOOL bForceMove = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bForceMove`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="placetabpredocking"></a>CMFCDragFrameImpl::PlaceTabPreDocking  

  
```  
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,  
    BOOL bFirstTime);  
  
void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTabbedBar`  
 [入力] `bFirstTime`  
 [入力] `pCBarToPlaceOn`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removetabpredocking"></a>CMFCDragFrameImpl::RemoveTabPreDocking  

  
```  
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOldTargetBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resetstate"></a>CMFCDragFrameImpl::ResetState  

  
```  
void ResetState();
```  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)