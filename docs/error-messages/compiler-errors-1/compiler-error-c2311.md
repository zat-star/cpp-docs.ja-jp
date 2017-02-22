---
title: "コンパイラ エラー C2311 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2311"
ms.assetid: 1aff9bd5-ed0b-4db6-bbc0-01ac89850cf2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'exception' : '...' によってキャッチされました。\(number 行\)  
  
 省略記号 \(...\) を指定した catch ハンドラーは、どの throw 式においても最後のハンドラーにする必要があります。  
  
 次の例では警告 C2311 が生成されます。  
  
```  
// C2311.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try {  
      throw "ooops!";  
   }  
   catch( ... ) {}  
   catch( int ) {}   // C2311  ellipsis handler not last catch  
}  
```