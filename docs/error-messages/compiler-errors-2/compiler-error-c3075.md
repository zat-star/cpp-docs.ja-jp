---
title: "コンパイラ エラー C3075 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3075"
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# コンパイラ エラー C3075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'instance': 参照型 'type' のインスタンスを値型に埋め込むことはできません  
  
 値型に参照型のインスタンスを含めることはできません。  
  
 詳細については、「[参照型の C\+\+ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)」を参照してください。  
  
## 使用例  
 次の例では C3075 が生成されます。  
  
```  
// C3075.cpp // compile with: /clr /c ref struct U {}; value struct X { U y;   // C3075 }; ref struct Y { U y;   // OK };  
```