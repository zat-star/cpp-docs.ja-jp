---
title: "コンパイラ エラー C3215 | Microsoft Docs"
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
  - "C3215"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3215"
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3215
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1': 'type2' によって既に制限されているジェネリック型パラメーターです  
  
 制約が複数回指定されました。  
  
 ジェネリックの詳細については、「[Generics](../../windows/generics-cpp-component-extensions.md)」を参照してください。  
  
 次の例では C3215 が生成されます。  
  
```  
// C3215.cpp // compile with: /clr interface struct A {}; generic <class T> where T : A,A ref class C {};   // C3215  
```  
  
 考えられる解決策:  
  
```  
// C3215b.cpp // compile with: /clr /c interface struct A {}; generic <class T> where T : A ref class C {};  
```