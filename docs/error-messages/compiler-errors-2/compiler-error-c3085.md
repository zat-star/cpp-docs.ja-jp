---
title: "コンパイラ エラー C3085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3085"
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constructor': コンストラクターを 'keyword' にすることはできません  
  
 コンストラクターが正しく宣言されていません。 詳細については、「[オーバーライド指定子](../../windows/override-specifiers-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3085 が生成されます。  
  
```  
// C3085.cpp // compile with: /c /clr ref struct S { S() abstract;   // C3085 S(S%) abstract;   // C3085 }; ref struct T { T() sealed {}   // C3085 T(T%) sealed {}   // C3085 };  
```