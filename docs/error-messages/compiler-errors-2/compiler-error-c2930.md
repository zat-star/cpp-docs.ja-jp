---
title: "コンパイラ エラー C2930 | Microsoft Docs"
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
  - "C2930"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2930"
ms.assetid: f07eecd1-e5d1-4518-bd89-b1fd2a003a17
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2930
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'クラス' : 'type\-class\-id' が、'enum identifier' の列挙子として再定義されています  
  
 ジェネリック クラスまたはテンプレート クラスは、列挙型のメンバーとして使用できません。  
  
 このエラーは、中かっこが正しく一致していない場合に発生することがあります。  
  
 次の例では C2930 が生成されます。  
  
```  
// C2930.cpp // compile with: /c template<class T> class x{}; enum SomeEnum { x };   // C2930 class y{}; enum SomeEnum { y };  
```  
  
 C2930 は、ジェネリックを使用する場合にも発生することがあります。  
  
```  
// C2930c.cpp // compile with: /clr /c generic<class T> ref struct GC {}; enum SomeEnum { GC };   // C2930 ref struct GC2 {}; enum SomeEnum2 { GC2 };  
```