---
title: "コンパイラの警告 (レベル 4) C4127 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 3e9fb4ed25e51311ec4f6b1d71a249c21d466069
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4127"></a>コンパイラの警告 (レベル 4) C4127
条件式が定数です。  
  
 `if` ステートメントまたは `while` ループの制御式が定数に評価されます。 ための一般的な慣用用法、ある 1 などの単純な定数または`true`式内の操作の結果でない限り、警告はトリガーされません。 場合の制御式、`while`中央でループを終了したため、ループが定数の場合を考慮してください、`while`のループ、`for`ループします。 初期化、終了テストを省略でき、ループのインクリメント、`for`によってと同じように、無限ループがループ`while(1)`の本体からループを終了して、`for`ステートメントです。  
  
 次の例は C4127 が生成され、使用する方法を示しています。 2 つの方法を示しています、for ループが、警告を回避します。  
  
```  
// C4127.cpp  
// compile with: /W4  
#include <stdio.h>  
int main() {  
   if (1 == 1) {}   // C4127  
   while (42) { break; }   // C4127  
  
   // OK  
   for ( ; ; ) {  
      printf("test\n");  
      break;  
   }  
}  
```
