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
ms.workload: cplusplus
ms.openlocfilehash: b7008b0f618048f5a4538a7aff55f03bab3d406d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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