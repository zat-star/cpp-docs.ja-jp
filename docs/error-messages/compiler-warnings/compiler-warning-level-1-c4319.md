---
title: "コンパイラの警告 (レベル 1) C4319 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4319
dev_langs: C++
helpviewer_keywords: C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dded592ef5b82329725937c40584d889d5aeb249
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4319"></a>コンパイラの警告 (レベル 1) C4319
'operator' : type' からより大きいサイズの 'type' へのゼロ拡張です。  
  
 ~ (ビットごとの補数) 演算子の結果は符号なしであるため、より大きい型に変換するとゼロ拡張になります。  
  
 次の例では、~(a - 1) が 32 ビットの unsigned long 式として評価され、ゼロ拡張によって 64 ビットに変換されます。 これは、予期しない操作結果になる可能性があります。  
  
```  
// C4319.cpp  
// compile with: cl /W4 C4319.cpp  
int main() {  
   unsigned long a = 0;  
   unsigned long long q = 42;  
   q = q & ~(a - 1);    // C4319 expected  
}  
```