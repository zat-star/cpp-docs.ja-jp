---
title: "コンパイラ エラー C3280 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3280"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3280"
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3280
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': マネージ クラスのメンバー関数をアンマネージ関数としてコンパイルできません  
  
 マネージ クラスのメンバー関数は、アンマネージ関数としてコンパイルできません。  
  
 次の例では C3280 が生成されます。  
  
```  
// C3280_2.cpp // compile with: /clr ref struct A { void func(); }; #pragma managed(push,off) void A::func()   // C3280 { } #pragma managed(pop)  
```  
  
 次の例では C3280 が生成されます。  
  
```  
// C3280.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __gc struct A { void func(); }; #pragma managed(push,off) void A::func()   // C3280 { } #pragma managed(pop)  
```