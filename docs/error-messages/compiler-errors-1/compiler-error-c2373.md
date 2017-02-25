---
title: "コンパイラ エラー C2373 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2373"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2373"
ms.assetid: 7a08bf0b-852d-48be-ba75-70df9f4b5951
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2373
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 再定義されています。異なる型修飾子です  
  
 識別子は、異なる型修飾子で既に定義されています。  
  
 次の例では C2373 が生成されます。  
  
```  
// C2373.h void __clrcall func( void ); const int i = 20;  
```  
  
 この場合、次のようになります。  
  
```  
// C2373.cpp // compile with: /c #include "C2373.h" extern void __cdecl func( void );   // C2373 extern void __clrcall func( void );   // OK extern int i;   // C2373 extern const int i;   // OK  
```