---
title: "リスト コントロールとリスト ビュー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46c9d559d642b6edf926b9feb49332ef7ec2924a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="list-control-and-list-view"></a>リスト コントロールとリスト ビュー
便宜上は、MFC は、2 つの方法でリスト コントロールをカプセル化します。 リスト コントロールを使用することができます。  
  
-   埋め込むことによって、直接、 [CListCtrl](../mfc/reference/clistctrl-class.md)ダイアログ クラス内のオブジェクト。  
  
-   クラスを使用して直接、 [CListView](../mfc/reference/clistview-class.md)です。  
  
 `CListView`簡単にコントロールをカプセル化 MFC ドキュメント/ビュー アーキテクチャは、リスト コントロールを統合すると同じ[CEditView](../mfc/reference/ceditview-class.md)エディット コントロールをカプセル化: コントロールが MFC ビューのすべての画面領域を塗りつぶします。 (ビュー*は*にキャスト、コントロール`CListView`)。  
  
 A`CListView`オブジェクトから継承[CCtrlView](../mfc/reference/cctrlview-class.md)とその基本クラスを基になるリスト コントロールを取得するメンバー関数を追加します。 ビューをビューとして使用するには、メンバーの表示を使用します。 使用して、 [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl)リスト コントロールのメンバー関数にアクセスするためにメンバー関数。 これらのメンバーを使用します。  
  
-   追加、削除、またはリスト内の「アイテム」を操作します。  
  
-   リスト コントロールの属性を取得または設定。  
  
 参照を取得する、`CListCtrl`基になる、 `CListView`、呼び出す`GetListCtrl`リスト ビュー クラスから。  
  
 [!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]  
  
 このトピックでは、リスト コントロールを使用する両方の方法について説明します。  
  
## <a name="see-also"></a>参照  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

