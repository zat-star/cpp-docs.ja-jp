---
title: "コンパイラ エラー C2193 | Microsoft Docs"
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
  - "C2193"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2193"
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2193
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 既にセグメント内で割り当てられています。  
  
 `alloc_text` プラグマと `code_seg` プラグマによって、関数が 2 つの異なるセグメントに置かれました。  
  
 次の例では警告 C2193 が生成されます。  
  
```  
// C2193.cpp  
// compile with: /c  
extern "C" void MYFUNCTION();  
#pragma alloc_text(MYCODE, MYFUNCTION)  
#pragma code_seg("MYCODE2")  
extern "C" void MYFUNCTION() {}   // C2193  
extern "C" void MYFUNCTION2() {}  
```