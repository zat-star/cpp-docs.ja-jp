---
title: "コンパイラ エラー C3217 | Microsoft Docs"
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
  - "C3217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3217"
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param' : ジェネリック パラメーターは、この宣言内で制限されることはできません  
  
 制約の形式が正しくありません。制約のジェネリック パラメーターは、ジェネリック クラスのテンプレート パラメーターと一致している必要があります。  
  
 次の例では C3217 が生成されます。  
  
```  
// C3217.cpp // compile with: /clr interface struct A {}; generic <class T> ref class C { generic <class T1> where T : A   // C3217 void f(); };  
```  
  
 次の例では、考えられる解決策を示しています。  
  
```  
// C3217b.cpp // compile with: /clr /c interface struct A {}; generic <class T> ref class C { generic <class T1> where T1 : A void f(); };  
```