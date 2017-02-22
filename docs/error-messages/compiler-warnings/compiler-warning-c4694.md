---
title: "コンパイラの警告 C4694 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4694"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4694"
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# コンパイラの警告 C4694
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class\_1': シールされた抽象クラスには、基底クラス 'base\_class' を含めることはできません  
  
 シールされた抽象クラスは参照型を継承できません。シールされた抽象クラスは、基底クラスの関数を実装することも、それ自体を基底クラスとして使用しすることもできません。  
  
 詳細については、「[abstract](../../windows/abstract-cpp-component-extensions.md)「[sealed](../../windows/sealed-cpp-component-extensions.md)および「[Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C4694 が生成されます。  
  
```  
// C4694.cpp // compile with: /c /clr ref struct A {}; ref struct B sealed abstract : A {};   // C4694  
```