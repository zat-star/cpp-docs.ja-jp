---
title: "コンパイラの警告 (レベル 4) C4610 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4610
dev_langs: C++
helpviewer_keywords: C4610
ms.assetid: 23c1a16c-9ca9-4bf6-9911-a72b785560c2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b2d8793dd3bc179f9c198195efcb9ba9b4ae556f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4610"></a>コンパイラの警告 (レベル 4) C4610
'class' のオブジェクトを初期化できません。 - ユーザー定義のコンス トラクターが必要  
  
 クラスは、ユーザー定義がありませんか、既定のコンス トラクターです。 インスタンス化は実行されません。 次の例では、C4610 が生成されます。  
  
```  
// C4610.cpp  
// compile with: /W4  
struct A {  
   int &j;  
  
   A& A::operator=( const A& );  
};   // C4610  
  
/* use this structure definition to resolve the warning  
struct B {  
   int &k;  
  
   B(int i = 0) : k(i) {  
   }  
  
   B& B::operator=( const B& );  
} b;  
*/  
  
int main() {  
}  
```