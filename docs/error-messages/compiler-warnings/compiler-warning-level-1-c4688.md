---
title: "コンパイラの警告 (レベル 1) C4688 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4688"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4688"
ms.assetid: a027df3c-b2b8-4c49-8539-c2bc42db74e8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4688
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constraint': 制約リストはアセンブリ プライベート型 'type' を含んでいます  
  
 制約リストにアセンブリ プライベート型があります。つまり、型にアセンブリの外部からアクセスする場合は、このリストを使用できません。 詳細については、「[Generics](../../windows/generics-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C4688 警告が生成されます。  
  
```  
// C4688.cpp // compile with: /clr /c /W1 ref struct A {};   // private type public ref struct B {}; // Delete the following 3 lines to resolve. generic <class T> where T : A   // C4688 public ref struct M {}; generic <class T> where T : B public ref struct N {};  
```