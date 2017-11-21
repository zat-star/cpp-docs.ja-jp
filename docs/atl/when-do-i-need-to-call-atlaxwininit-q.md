---
title: "ときになを呼び出す必要があるのですか。 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AtlAxWinInit
dev_langs: C++
helpviewer_keywords: AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2ec7d8d15b8219071b593368ed539d92ff3c9032
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>ときになを呼び出す必要があるのですか。

[な](reference/composite-control-global-functions.md#atlaxwininit)登録、 **"AtlAxWin80"**ウィンドウ (さらに、いくつかのカスタム ウィンドウ メッセージには) クラスのため、ホスト ウィンドウを作成しようとする前に、この関数を呼び出す必要があります。 ただし、常にする必要はありません Api (およびそれらを使用するクラス) をホストから明示的に、この関数の呼び出しを多くの場合、この関数を呼び出します。 この関数を複数回呼び出す害はありません。 。  
  
## <a name="see-also"></a>関連項目  
 AtlAxWinTerm を呼び出す必要が場合     
 [コントロール コンテインメントよく寄せられる質問](../atl/atl-control-containment-faq.md)
