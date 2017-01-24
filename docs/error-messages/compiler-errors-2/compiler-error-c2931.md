---
title: "コンパイラ エラー C2931 | Microsoft Docs"
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
  - "C2931"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2931"
ms.assetid: 33430407-b149-4ba3-baf8-b0dae1ea3a5d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2931
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': type\-class\-id が 'identifier' のメンバー関数として再定義されています  
  
 ジェネリック クラスまたはテンプレート クラスは、別のクラスのメンバー関数として使用できません。  
  
 このエラーは、中かっこが正しく一致していない場合に発生することがあります。  
  
 次の例では C2931 が生成されます。  
  
```  
// C2931.cpp // compile with: /c template<class T> struct TC { }; struct MyStruct { void TC<int>();   // C2931 }; struct TC2 { }; struct MyStruct2 { void TC2(); };  
```  
  
 C2931 は、ジェネリックを使用する場合にも発生することがあります。  
  
```  
// C2931b.cpp // compile with: /clr /c generic<class T> ref struct GC {}; struct MyStruct { void GC<int>();   // C2931 void GC2();   // OK };  
```