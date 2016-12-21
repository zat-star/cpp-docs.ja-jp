---
title: "単項加算演算子と否定演算子: + および - | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "+"
  - "-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "- 演算子"
  - "+ 演算子"
  - "+ 演算子, 単項演算子"
  - "否定演算子"
  - "単項演算子, plus"
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 単項加算演算子と否定演算子: + および -
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
+ cast-expression  
```  
  
```  
  
- cast-expression  
  
```  
  
## \+ 演算子  
 単項プラス演算子 \(**\+**\) の結果はそのオペランドの値です。  単項プラス演算子のオペランドは数値型である必要があります。  
  
 整数の上位変換が整数オペランドに対して実行されます。  結果の型は、オペランドの上位変換先の型です。  したがって、式 `+ch` \(`ch` が `char` 型\) は、結果が `int` 型になります。値は変更されません。  上位変換のしくみの詳細については、「[整数の上位変換](../misc/integral-promotions.md)」を参照してください。  
  
## \- 演算子  
 単項否定演算子 \(**–**\) はオペランドの負数を生成します。  単項否定演算子のオペランドには数値型を指定する必要があります。  
  
 整数の上位変換は、整数オペランドに対して実行され、結果の型は、そのオペランドが昇格される型になります。  上位変換のしくみについては、「[整数の上位変換](../misc/integral-promotions.md)」を参照してください。  
  
## Microsoft 固有の仕様  
 符号なし数値の単項否定演算は、2^n からオペランドの値を減算することによって実行されます。この n は、指定した符号なし型のオブジェクトのビット数です   \(Microsoft C\+\+ は、2 の補数演算を利用するプロセッサで実行されます。  他のプロセッサでは否定のアルゴリズムが異なる場合があります\)。  
  
## 参照  
 [単項演算子を含む式](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)