---
title: "コンパイラ エラー CS0244 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0244"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0244"
ms.assetid: f10e4479-ed6e-40dc-9fab-914e404d7f84
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# コンパイラ エラー CS0244
is' と 'as' のどちらもポインター型では無効です  
  
 キーワードの [is](../Topic/is%20\(C%23%20Reference\).md) と [as](../Topic/as%20\(C%23%20Reference\).md) は、ポインター型では使用できません。 詳細については、「[unsafe コードとポインター](../Topic/Unsafe%20Code%20and%20Pointers%20\(C%23%20Programming%20Guide\).md)」を参照してください。  
  
 次の例では CS0244 が生成されます。  
  
```  
// CS0244.cs // compile with: /unsafe class UnsafeTest { unsafe static void SquarePtrParam (int* p) { bool b = p is object;   // CS0244 p is pointer } unsafe public static void Main() { int i = 5; SquarePtrParam (&i); } }  
```