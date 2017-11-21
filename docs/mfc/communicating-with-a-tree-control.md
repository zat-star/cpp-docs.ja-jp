---
title: "ツリー コントロールとの通信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 33835dcaa40b217e9248e5c03b775f968332b687
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="communicating-with-a-tree-control"></a>ツリー コントロールとの情報のやり取り
メンバー関数を呼び出すさまざまな方法を使用する、 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)オブジェクトの作成方法に依存するオブジェクト。  
  
-   ツリー コントロールがダイアログ ボックス内にある場合は、型のメンバー変数を使用して`CTreeCtrl` ダイアログ ボックス クラスで作成します。  
  
-   ツリー コントロールが子ウィンドウの場合を使用して、`CTreeCtrl`オブジェクトを構築するために使用するオブジェクト (またはポインター)。  
  
-   使用する場合、`CTreeView`オブジェクト、関数を使用して[CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl)ツリーのコントロールへの参照を取得します。 この値を持つ別の参照を初期化またはへの参照のアドレスを割り当てることができます、`CTreeCtrl`ポインター。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

