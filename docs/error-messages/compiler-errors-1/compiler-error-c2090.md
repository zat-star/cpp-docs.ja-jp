---
title: "コンパイラ エラー C2090 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2090"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2090"
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2090
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数は配列を返せません。  
  
 関数は配列を返すことができません。  代わりに配列へのポインターが返されます。  
  
 次の例では警告 C2090 が生成されます。  
  
```  
// C2090.cpp  
int func1(void)[] {}   // C2090  
```  
  
 解決方法 :  
  
```  
// C2090b.cpp  
// compile with: /c  
int* func2(int * i) {  
   return i;  
}  
```