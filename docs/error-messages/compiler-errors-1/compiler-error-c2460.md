---
title: "コンパイラ エラー C2460 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 00e4015a0dae5054973ba72bb0e4f89c7443ae03
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2460"></a>コンパイラ エラー C2460
'identifier1': は 'identifier2' で宣言されています。  
  
 クラスまたは構造体 (`identifier2`) がそれ自体のメンバーとして宣言されている (`identifier1`)。 クラスと構造体の再帰的な定義を指定することはできません。  
  
 次の例では、C2460 が生成されます。  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 代わりに、クラスのポインターの参照を使用します。  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```
