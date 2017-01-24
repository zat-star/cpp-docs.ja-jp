---
title: "かっこで囲んだ式 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "式の評価, 評価順序"
  - "式 [C++], 評価"
  - "かっこ"
  - "かっこ, 式"
ms.assetid: b8636147-6982-408c-9e64-29e40678ee43
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# かっこで囲んだ式
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オペランドはかっこで囲むことができ、囲まれた式の型と値は変わりません。  たとえば、次の式では、  
  
```  
( 10 + 5 ) / 5  
```  
  
 `10 + 5` を囲むかっこは、`10 + 5` の値を最初に評価し、それが除算 \(**\/**\) 演算子の左側のオペランドになることを意味します。  `( 10 + 5 ) / 5` の結果は 3 です。  かっこがない場合、`10 + 5 / 5` は 11 に評価されます。  
  
 かっこはオペランドが式内でグループ化される方法に影響を与えますが、すべての場合に特定の評価の順序を保証できません。  たとえば次の式では、かっこによっても、左から右へのグループ化によっても、`i` の値が部分式のどちらに含まれるかは保証されません。  
  
```  
( i++ +1 ) * ( 2 + i )  
```  
  
 コンパイラは、乗算の 2 つの辺を任意の順序で自由に評価します。  `i` の初期値がゼロの場合、式全体が次の 2 つのステートメントのどちらかとして評価されます。  
  
```  
( 0 + 1 + 1 ) * ( 2 + 1 )   
( 0 + 1 + 1 ) * ( 2 + 0 )  
```  
  
 副作用の結果として発生する例外については、「[副作用](../c-language/side-effects.md)」を参照してください。  
  
## 参照  
 [C 一次式](../c-language/c-primary-expressions.md)