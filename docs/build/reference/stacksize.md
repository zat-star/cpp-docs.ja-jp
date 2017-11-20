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
ms.openlocfilehash: 82b33d217e593a35b66bb3530840a739e93082ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="stacksize"></a>STACKSIZE
スタック サイズをバイト単位で設定します。  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## <a name="remarks"></a>コメント  
 スタックを設定すると同等の方法は、[スタック割り当て](../../build/reference/stack-stack-allocations.md)(/stack) オプション。 このオプションは、詳細については、ドキュメントを参照してください、*予約*と`commit`引数。  
  
 このオプションは、Dll への影響を与えません。  
  
## <a name="see-also"></a>関連項目  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)