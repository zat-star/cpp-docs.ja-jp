---
title: "コンパイラの警告 (レベル 4) C4127 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1a5bbd86b6197907f043478df225dceb79679f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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