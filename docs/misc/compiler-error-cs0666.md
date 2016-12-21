---
title: "コンパイラ エラー CS0666 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0666"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0666"
ms.assetid: 44ad4574-b4a2-487b-8d05-0116762231ab
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# コンパイラ エラー CS0666
'member': 新規のプロテクト メンバーが構造体で宣言されています  
  
 [struct](../Topic/struct%20\(C%23%20Reference\).md) を [abstract](../Topic/abstract%20\(C%23%20Reference\).md) にすることはできず、常に暗黙的にシール \([sealed](../Topic/sealed%20\(C%23%20Reference\).md)\) されます。 struct は、継承をサポートしていないため、struct の [protected](../Topic/protected%20\(C%23%20Reference\).md) メンバーの概念は意味がありません。 詳細については、「[継承](../Topic/Inheritance%20\(C%23%20Programming%20Guide\).md)」を参照してください。  
  
## 使用例  
 次の例では CS0666 が生成されます。  
  
```  
// CS0666.cs class M { static void Main() { } } struct S { protected int x;   // CS0666 }  
```