---
title: "1 つのウィンドウで 1 つ以上のコントロールをホストすることができますか。 | Microsoft Docs"
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
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be87c0bad9ab250593847cc24d16158030040054
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>1 つのウィンドウで 1 つ以上のコントロールをホストすることができますか。
単一の ATL ホスト ウィンドウに 2 つ以上のコントロールをホストすることはできません。 各ホスト ウィンドウは、(これにより、メッセージのリフレクションとコントロールごとのアンビエント プロパティを処理するための簡単なメカニズム) 時に正確に 1 つのコントロールを保持するために設計されています。 ただし、1 つのウィンドウで複数のコントロールを表示するユーザーに、必要な場合は、そのウィンドウの子として複数のホスト ウィンドウを作成するだけの簡単なです。  
  
## <a name="see-also"></a>参照  
 [コントロール コンテインメントよく寄せられる質問](../atl/atl-control-containment-faq.md)

