---
title: "データ型指定子と同等物 | Microsoft Docs"
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
  - "データ型 [C++], 等価"
  - "データ型 [C++], 指定子"
  - "識別子, データ型"
  - "符号拡張された整数型"
  - "単純型, 名前"
  - "型名 [C++], 単純な"
  - "型指定子 [C++], 一覧"
  - "整数の拡大"
  - "ゼロ拡張"
ms.assetid: 0d4b515a-4f68-4786-83cf-a5d43c7cb6f3
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# データ型指定子と同等物
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このブックでは、通常、次の表に示す型指定子の短い形式を使用し、長い形式は使用しません。`char` 型は既定で符号付きであることを前提としています。  したがって、このブックでは、`char` は **signed char** と等価です。  
  
### 型指定子と同等の形式  
  
|型指定子|同等の形式|  
|----------|-----------|  
|**signed char**1|`char`|  
|**signed int**|**signed**、`int`|  
|**signed short int**|**short**、`signed short`|  
|**signed long int**|**long**、**signed long**|  
|`unsigned char`|—|  
|`unsigned int`|`unsigned`|  
|**unsigned short int**|**unsigned short**|  
|**unsigned long int**|`unsigned long`|  
|**float**|—|  
|`long double`2|—|  
  
 1   `char` 型を既定で unsigned にすると \(\/J コンパイラ オプションを指定\)、**signed char** を `char` と短縮できません。  
  
 2   32 ビット オペレーティング システムでは、Microsoft C コンパイラは **long double**  を **double** 型にマップします。  
  
 **Microsoft 固有の仕様 →**  
  
 \/J コンパイラ オプションを指定して、既定の `char` 型を符号付きから符号なしに変更できます。  このオプションが有効になっている場合、`char` は `unsigned char` と同じ意味であり、符号付き文字の値を宣言するには **signed** キーワードを使用する必要があります。  `char` 値を明示的に signed 宣言すると、\/J オプションは適用されません。`int` 型に上位変換すると、値が符号拡張されます。  `char` 型は、`int` 型に上位変換するとゼロ拡張されます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [C 型指定子](../c-language/c-type-specifiers.md)