---
title: "CListView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CListView
dev_langs:
- C++
helpviewer_keywords:
- views, and common controls
- CListView class
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ebf6c93aa6d88d1942af4ecb9e3373fa57d84b65
ms.lasthandoff: 02/24/2017

---
# <a name="clistview-class"></a>CListView クラス
リスト コントロールとの使用を簡略化[CListCtrl](../../mfc/reference/clistctrl-class.md)MFC のドキュメント/ビュー アーキテクチャのリスト コントロールの機能をカプセル化するクラス。  
  
## <a name="syntax"></a>構文  
  
```  
class CListView : public CCtrlView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CListView::CListView](#clistview)|`CListView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CListView::GetListCtrl](#getlistctrl)|ビューに関連付けられているリスト コントロールを返します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CListView::RemoveImageList](#removeimagelist)|リスト ビューから、指定されたイメージのリストを削除します。|  
  
## <a name="remarks"></a>コメント  
 このアーキテクチャの詳細については、の概要を参照してください、 [CView](../../mfc/reference/cview-class.md)クラスとクロス リファレンスがあります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcview.h  
  
##  <a name="a-nameclistviewa--clistviewclistview"></a><a name="clistview"></a>CListView::CListView  
 `CListView` オブジェクトを構築します。  
  
```  
CListView();
```  
  
##  <a name="a-namegetlistctrla--clistviewgetlistctrl"></a><a name="getlistctrl"></a>CListView::GetListCtrl  
 このメンバー関数を呼び出して、ビューに関連付けられたリスト コントロールへの参照を取得します。  
  
```  
CListCtrl& GetListCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビューに関連付けられているリスト コントロールへの参照。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCListView&#7;](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]  
  
##  <a name="a-nameremoveimagelista--clistviewremoveimagelist"></a><a name="removeimagelist"></a>CListView::RemoveImageList  
 リスト ビューから、指定されたイメージのリストを削除します。  
  
```  
void RemoveImageList(int nImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `nImageList`  
 削除するイメージの&0; から始まるインデックス。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル rowlist で](../../visual-cpp-samples.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)

