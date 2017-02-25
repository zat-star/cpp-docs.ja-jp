---
title: "コンパイラ エラー C2824 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2824"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2824"
ms.assetid: 5bd865f7-e0af-404e-80fe-e2b798b44a59
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2824
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator new' 演算子の 'return' 値は 'void \*' 型でなければなりません。  
  
 非 based ポインターでは、`new` 演算子のオーバーロードは `void *` を返す必要があります。  
  
 次の例では警告 C2824 が生成されます。  
  
```  
// C2824.cpp  
// compile with: /c  
class   A {  
   A* operator new(size_t i, char *m);   // C2824  
   // try the following line instead  
   // void* operator new(size_t i, char *m);  
};  
```