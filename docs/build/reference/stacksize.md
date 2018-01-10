---
title: "STACKSIZE |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: STACKSIZE
dev_langs: C++
helpviewer_keywords: STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9c09bea88c4f9452d0fab9371c8b9af8011fd32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="stacksize"></a>STACKSIZE
スタック サイズをバイト単位で設定します。  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## <a name="remarks"></a>コメント  
 スタックを設定すると同等の方法は、[スタック割り当て](../../build/reference/stack-stack-allocations.md)(/stack) オプション。 このオプションは、詳細については、ドキュメントを参照してください、*予約*と`commit`引数。  
  
 このオプションは、Dll への影響を与えません。  
  
## <a name="see-also"></a>参照  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)