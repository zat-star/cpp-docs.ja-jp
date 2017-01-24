---
title: "コンパイラ エラー CS0541 | Microsoft Docs"
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
  - "CS0541"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0541"
ms.assetid: ed812c07-24f7-43c6-9a44-553f27f6249d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# コンパイラ エラー CS0541
'declaration' : 明示的インターフェイスはクラス、または構造体の中でのみ宣言できます。  
  
 明示的な [interface](../Topic/interface%20\(C%23%20Reference\).md) 宣言が、[クラス](../Topic/class%20\(C%23%20Reference\).md)または[構造体](../Topic/struct%20\(C%23%20Reference\).md)の外側で見つかりました。  
  
 次の例では CS0541 が生成されます。  
  
```  
// CS0541.cs namespace x { interface IFace { void F(); } interface IFace2 : IFace { void IFace.F();   // CS0541 } }  
```