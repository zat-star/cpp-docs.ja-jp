---
title: "コンパイラ エラー C2884 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2884"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2884"
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2884
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : using 宣言で導入された関数は、ローカル関数 'function' と競合しています。  
  
 関数を 2 回以上定義しようとしました。  最初の定義はローカル定義です。  2 番目の定義は、名前空間から `using` 宣言で行われています。  
  
 次の例では警告 C2884 が生成されます。  
  
```  
// C2884.cpp  
namespace A {  
   void z(int);  
}  
  
void f() {  
   void z(int);  
   using A::z;   // C2884 z is already defined  
}  
```