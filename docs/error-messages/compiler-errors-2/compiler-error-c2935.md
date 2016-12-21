---
title: "コンパイラ エラー C2935 | Microsoft Docs"
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
  - "C2935"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2935"
ms.assetid: e11ef90d-0756-4e43-8a09-4974c6aa72a3
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2935
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': type\-class\-id がグローバル関数として再定義されています  
  
 ジェネリック クラスまたはテンプレート クラスをグローバル関数として使用することはできません。  
  
 このエラーは、中かっこが正しく一致していない場合に発生することがあります。  
  
 次の例では C2935 が生成されます。  
  
```  
// C2935.cpp // compile with: /c template<class T> struct TC {}; void TC<int>() {}   // C2935 // OK struct TC2 {}; void TC2() {}  
```  
  
 C2935 は、ジェネリックを使用しているときも発生します。  
  
```  
// C2935b.cpp // compile with: /clr /c generic<class T> ref struct GC { }; void GC<int>() {}   // C2935 void GC() {}   // OK  
```