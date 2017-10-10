---
title: "コンパイラ エラー C2647 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2647
dev_langs:
- C++
helpviewer_keywords:
- C2647
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8d9a068e70f39f05624cc1af843f1c8ae8db7caf
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2647"></a>コンパイラ エラー C2647
'operator': 'type2' で 'type1' を逆参照できません  
  
 メンバーへのポインター演算子の左オペランド (`->*`または`.*`) を右辺のオペランドに関連する型に暗黙的に変換できません。  
  
 次の例では、C2647 が生成されます。  
  
```  
// C2647.cpp  
class C {};  
class D {};  
  
int main() {  
   D d, *pd;  
   C c, *pc = 0;  
   int C::*pmc = 0;  
   pd->*pmc = 0;   // C2647  
   d.*pmc = 0;   // C2647  
  
   // OK  
   pc->*pmc = 0;  
   c.*pmc = 0;  
}  
```
