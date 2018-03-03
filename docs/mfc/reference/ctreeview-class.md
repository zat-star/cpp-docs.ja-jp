---
title: "CTreeView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7530569d5e5313ebfcbdaf92ebd245962b9e443c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ctreeview-class"></a>CTreeView クラス
ツリー コントロールの使用との使用を簡略化[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)MFC のドキュメント/ビュー アーキテクチャのツリー コントロールの機能をカプセル化するクラス。  
  
## <a name="syntax"></a>構文  
  
```  
class CTreeView : public CCtrlView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CTreeView::CTreeView](#ctreeview)|`CTreeView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTreeView::GetTreeCtrl](#gettreectrl)|ビューに関連付けられているツリーのコントロールを返します。|  
  
## <a name="remarks"></a>コメント  
 このアーキテクチャの詳細については、「の概要、 [CView](../../mfc/reference/cview-class.md)クラスおよびクロス リファレンスがあります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcview.h  
  
##  <a name="ctreeview"></a>CTreeView::CTreeView  
 `CTreeView` オブジェクトを構築します。  
  
```  
CTreeView();
```  
  
##  <a name="gettreectrl"></a>CTreeView::GetTreeCtrl  
 ビューに関連付けられているツリーのコントロールへの参照を返します。  
  
```  
CTreeCtrl& GetTreeCtrl() const;  
```  
  
## <a name="see-also"></a>参照  
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)
