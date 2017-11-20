---
title: "ときに AtlAxWinTerm を呼び出す必要があるのですか。 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AtlAxWinTerm
dev_langs: C++
helpviewer_keywords: AtlAxWinTerm method
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cdba5255560f220a80a016f17e574721b12f486d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="when-do-i-need-to-call-atlaxwinterm"></a>ときに AtlAxWinTerm を呼び出す必要があるのですか。
[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)の登録を解除、 **"AtlAxWin80"**ウィンドウ クラスです。 既存のすべてのホスト ウィンドウが破棄された後に、(不要になった、ホスト ウィンドウを作成する必要がある) 場合に、この関数を呼び出す必要があります。 この関数が呼び出されない場合、ウィンドウ クラスが登録解除する自動的にプロセスが終了したときにします。  
  
## <a name="see-also"></a>関連項目  
 な呼び出しに必要な場合  
[コントロール コンテインメントよく寄せられる質問](../atl/atl-control-containment-faq.md)

