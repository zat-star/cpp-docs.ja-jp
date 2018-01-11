---
title: "アニメーション コントロールによる通知の送信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c57a33bf4b13397d4f296ef4e5aa8e137c2d3594
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="notifications-sent-by-animation-controls"></a>アニメーション コントロールによる通知の送信
アニメーション コントロール ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) 2 つのさまざまな種類の通知メッセージを送信します。 形式で、通知を送信[WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージ。  
  
 [ACN_START](http://msdn.microsoft.com/library/windows/desktop/bb761891)アニメーション コントロールのクリップの再生が開始されたときに、メッセージが送信されます。 [ACN_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893)アニメーション コントロールが完了またはクリップの再生を停止したときにメッセージが送信されます。  
  
## <a name="see-also"></a>参照  
 [CAnimateCtrl の使い方](../mfc/using-canimatectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

