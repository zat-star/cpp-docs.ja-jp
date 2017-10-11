---
title: "コンパイラの警告 (レベル 1) C4020 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4020
dev_langs:
- C++
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f4980961746f2711fcf0655dd37b5f37d8d8124e
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4020"></a>コンパイラの警告 (レベル 1) C4020
'function': 実引数が多すぎます  
  
 関数呼び出しで指定された実引数の数は、関数プロトタイプまたは定義で仮パラメーターの数を超えています。 コンパイラは、関数の呼び出し規則に従って余分な実際のパラメーターを渡します。  
  
 次の例では、C4020 が生成されます。  
  
```  
// C4020.c  
// compile with: /W1 /c  
void f(int);  
int main() {  
   f(1,2);   // C4020  
}  
```  
  
 考えられる解決策:  
  
```  
// C4020b.c  
// compile with: /c  
void f(int);  
int main() {  
   f(1);  
}  
```
