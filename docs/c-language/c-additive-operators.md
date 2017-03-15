---
title: "C 加法演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "+ 演算子, 加法演算子"
  - "加法演算子"
  - "算術演算子 [C++], 加法演算子"
  - "演算子 [C], 加算"
  - "通常の算術変換"
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# C 加法演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

加法演算子は加算 \(**\+**\) と減算 \(**–**\) を実行します。  
  
## 構文  
 *additive\-expression*:  
 *multiplicative\-expression*  
  
 *additive\-expression*  **\+**  *multiplicative\-expression*  
  
 *additive\-expression*  **–**  *multiplicative\-expression*  
  
> [!NOTE]
>  *additive\-expression* の構文に *multiplicative\-expression* が含まれてますが、乗算を使用する式が必要なわけではありません。  「[C 言語の構文概要](../c-language/c-language-syntax-summary.md)」で、*multiplicative\-expression*、*cast\-expression*、および *unary\-expression* の構文を参照してください。  
  
 オペランドは整数値または浮動小数点値になります。  各演算子の説明に記載されているように、一部の加算演算はポインター値に対しても実行できます。  
  
 加算演算子は、整数および浮動小数点のオペランドに対して通常の算術変換を実行します。  結果の型は、変換後のオペランドの型です。  加算演算子によって実行される変換にはオーバーフロー条件やアンダーフロー条件が用意されていないため、加算演算の結果を変換後のオペランドの型で表すことができない場合、情報が失われる可能性があります。  
  
## 参照  
 [加法演算子: \+ および \-](../cpp/additive-operators-plus-and.md)