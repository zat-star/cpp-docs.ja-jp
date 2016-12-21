---
title: "コンパイラ エラー C2777 | Microsoft Docs"
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
  - "C2777"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2777"
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2777
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティ毎に設定可能な 'put' メソッドは 1 つだけです。  
  
 1 つの [プロパティ](../../cpp/property-cpp.md) declspec 修飾子に `put` プロパティが複数あります。  
  
 次の例では警告 C2777 が生成されます。  
  
```  
// C2777.cpp  
struct A {  
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777  
   // try the following line instead  
   // __declspec(property(put=PutProp))  
      int prop;  
   int PutProp(void);  
   int PutPropToo(void);  
};  
```