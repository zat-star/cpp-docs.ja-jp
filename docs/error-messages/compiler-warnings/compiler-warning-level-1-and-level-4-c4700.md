---
title: "コンパイラの警告 (レベル 1 およびレベル 4) C4700 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4700
dev_langs:
- C++
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f41e519a9dbcff3cc5ad4b718003e5964bfc3e85
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>コンパイラの警告 (レベル 1 およびレベル 4) C4700
初期化されていないローカル変数 'name' の使用  
  
 ローカル変数を使用した*名前*最初に、値を代入せず予想外の結果を招く可能性があります。  
  
 次の例では、C4700 が生成されます。  
  
```  
// C4700.cpp  
// compile with: /W1  
int main() {  
   int i;  
   return i;   // C4700  
}  
```  
  
 [/Clr:safe](../../build/reference/clr-common-language-runtime-compilation.md)レベル 4 の警告です。  次の例では、C4700 が生成されます。  
  
```  
// C4700b.cpp  
// compile with: /W4 /clr:safe /c  
using namespace System;  
int main() {  
   Int32^ bi;  
   return *bi;   // C4700  
}  
```
