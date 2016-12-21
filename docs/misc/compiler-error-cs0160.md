---
title: "コンパイラ エラー CS0160 | Microsoft Docs"
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
  - "CS0160"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0160"
ms.assetid: 4ef07061-8ef5-42d9-b043-3f81307d569f
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# コンパイラ エラー CS0160
前の catch 句は、これまたはスーパー型 \('type'\) の例外を、すべて既にキャッチしています  
  
 一連の **catch** ステートメントは、派生の降順になっている必要があります。 たとえば、最派生オブジェクトが最初に現れる必要があります。  
  
 詳細については、「[例外処理ステートメント](../Topic/Exception%20Handling%20Statements%20\(C%23%20Reference\).md)」および「[例外と例外処理](../Topic/Exceptions%20and%20Exception%20Handling%20\(C%23%20Programming%20Guide\).md)」を参照してください。  
  
 次の例では CS0160 が生成されます。  
  
```  
// CS0160.cs public class MyClass2 : System.Exception {} public class MyClass { public static void Main() { try {} catch(System.Exception) {}   // Second-most derived; should be second catch catch(MyClass2) {}   // CS0160  Most derived; should be first catch } }  
```