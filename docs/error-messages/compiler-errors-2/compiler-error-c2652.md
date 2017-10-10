---
title: "コンパイラ エラー C2652 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2652
dev_langs:
- C++
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 56cfdf52ec3a6947a6a82774f551fc1a6880c959
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2652"></a>コンパイラ エラー C2652
'identifier': コピー コンス トラクター: 最初のパラメーターが 'identifier' することはできません  
  
 コピー コンス トラクターの最初のパラメーターは、クラス、構造体、または共用体が定義されているのと同じ型を持ちます。 最初のパラメーターは、型が型自体ではなくへの参照を指定できます。  
  
 次の例では、C2651 が生成されます。  
  
```  
// C2652.cpp  
// compile with: /c  
class A {  
   A( A );   // C2652 takes an A  
};  
class B {  
   B( B& );   // OK, reference to B  
};  
```
