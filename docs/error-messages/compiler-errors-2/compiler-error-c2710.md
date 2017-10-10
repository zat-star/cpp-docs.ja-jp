---
title: "コンパイラ エラー C2710 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2710
dev_langs:
- C++
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5bb6349bf6efb8c63b68c78644343ace5dc07e67
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2710"></a>コンパイラ エラー C2710
'construct': '__declspec(modifier)' は、ポインターを返す関数にのみ適用できます  
  
 戻り値があるポインター関数は、唯一の構造体を`modifier`適用できます。  
  
 次の例では、C2710 が生成されます。  
  
```  
// C2710.cpp  
__declspec(restrict) void f();   // C2710  
// try the following line instead  
__declspec(restrict) int * g();  
```
