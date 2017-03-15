---
title: "コンパイラ エラー C2153 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2153"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2153"
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2153
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

16 進型定数で 0x、0X の後には、少なくとも 1 桁の 16 進数が必要です。  
  
 0x、0X、\\x などの 16 進定数は無効です。  少なくとも 1 桁の 16 進数を x または X の後に指定する必要があります。  
  
 次の例では警告 C2153 が生成されます。  
  
```  
// C2153.cpp  
int main() {  
   int a= 0x;    // C2153  
   int b= 0xA;   // OK  
}  
```