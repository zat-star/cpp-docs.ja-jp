---
title: "コンパイラ エラー C2792 | Microsoft Docs"
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
  - "C2792"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2792"
ms.assetid: 392cf748-4f5e-4e62-a364-3118d5658408
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2792
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'super' : このキーワードは '::' の後に使用する必要があります。  
  
 キーワード `__super` の後に使用できるトークンは `::` だけです。  
  
 次の例では警告 C2792 が生成されます。  
  
```  
// C2792.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super.();   // C2792  
  
      // try the following line instead  
      // __super::mf();  
   }  
};  
```