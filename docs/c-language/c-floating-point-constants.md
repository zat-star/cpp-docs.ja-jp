---
title: "C 浮動小数点定数 | Microsoft Docs"
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
  - "定数, 浮動小数点"
  - "Double 型, 浮動小数点定数"
  - "浮動小数点定数"
  - "浮動小数点定数, 浮動小数点定数の概要"
  - "浮動小数点数, 浮動小数点定数"
  - "型 [C], 定数"
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 浮動小数点定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"浮動小数点定数" は符号付き実数を表す 10 進数です。  符号付き実数の表現には、整数部分、小数部分、および指数が含まれます。  変更できない浮動小数点値を表すには、浮動小数点定数を使用します。  
  
## 構文  
 *floating\-point\-constant*:  
 *fractional\-constant exponent\-part*  opt *floating\-suffix* opt  
  
 *digit\-sequence exponent\-part floating\-suffix*  opt  
  
 *fractional\-constant*:  
 *digit\-sequence*  opt **.** *digit\-sequence*  
  
 *digit\-sequence*  **.**  
  
 *exponent\-part*:  
 **e**  *sign*  opt *digit\-sequence*  
  
 **E**  *sign*  opt *digit\-sequence*  
  
 *sign* : 次のいずれかです。  
 **\+ –**  
  
 *digit\-sequence*:  
 *digit*  
  
 *digit\-sequence digit*  
  
 *floating\-suffix* : 次のいずれかです。  
 **f l F L**  
  
 小数点の前の桁 \(値の整数の部分\) または小数点の後の桁 \(小数の部分\) を省略できますが、両方を省略することはできません。  指数を含めた場合にのみ、小数点を省略することができます。  空白文字で定数の数値または文字を分離することはできません。  
  
 次の例では、浮動小数点定数と式のフォームをいくつか示します。  
  
```  
15.75  
1.575E1   /* = 15.75   */  
1575e-2   /* = 15.75   */  
-2.5e-3   /* = -0.0025 */  
25E-4     /* =  0.0025 */  
```  
  
 浮動小数点定数は、負符号 \(**–**\) が前にない限り、正の値です。  この場合、負符号は単項算術否定演算子として扱われます。  浮動小数点定数には、**float**、**double**、または `long double` 型があります。  
  
 **f**、**F**、**l**、または **L** のサフィックスのない浮動小数点定数は、**double** 型を持ちます。  文字 **f** または **F** がサフィックスの場合、定数の型は **float** になります。  末尾に文字 **l** また **L** が付いている場合、`long double` 型になります。  次のように記述します。  
  
```  
100L  /* Has type long double  */  
100F  /* Has type float        */  
```  
  
 Microsoft C コンパイラは **long double**  を **double** 型にマップすることに注意してください。  **double**、**float**、および **long** 型については、「[基本型のストレージ](../c-language/storage-of-basic-types.md)」を参照してください。  
  
 次の例に示すように、浮動小数点定数の整数の部分を省略できます。  数値 .75 は、次のようなさまざまな方法で表現されます。  
  
```  
.0075e2  
0.075e1  
.075e1  
75e-2  
```  
  
## 参照  
 [C 定数](../c-language/c-constants.md)