---
title: "CTreeView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- directory lists
- tree view controls
- file lists [C++]
- CTreeView class, common controls
- CTreeView class
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
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
ms.openlocfilehash: c317d91a07b5cb45b58ec4c4af2e9ee0f3b24e28
ms.lasthandoff: 02/24/2017

---
# <a name="ctreeview-class"></a>CTreeView クラス
ツリー コントロールとの使用を簡略化[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)MFC のドキュメント/ビュー アーキテクチャのツリー コントロールの機能をカプセル化するクラス。  
  
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
|[CTreeView::GetTreeCtrl](#gettreectrl)|ビューに関連付けられているツリー コントロールを返します。|  
  
## <a name="remarks"></a>コメント  
 このアーキテクチャの詳細については、の概要を参照してください、 [CView](../../mfc/reference/cview-class.md)クラスとクロス リファレンスがあります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcview.h  
  
##  <a name="ctreeview"></a>CTreeView::CTreeView  
 `CTreeView` オブジェクトを構築します。  
  
```  
CTreeView();
```  
  
##  <a name="gettreectrl"></a>CTreeView::GetTreeCtrl  
 ビューに関連付けられているツリー コントロールへの参照を返します。  
  
```  
CTreeCtrl& GetTreeCtrl() const;  
```  
  
## <a name="see-also"></a>関連項目  
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)

