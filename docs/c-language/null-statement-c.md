---
title: "Null ステートメント (C) | Microsoft Docs"
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
  - "式 [C++], null"
  - "null ステートメント"
  - "null 値, 式"
  - "セミコロン, C の null ステートメント"
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Null ステートメント (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"null ステートメント" はセミコロンのみを含むステートメントで、ステートメントが使用できるあらゆる場所に配置できます。  null ステートメントが実行されても、何も処理されません。  null ステートメントのコーディング方法は次のとおりです。  
  
## 構文  
  
```  
  
;  
  
```  
  
## 解説  
 **do**、**for**、**if**、`while` などのステートメントでは、ステートメント本体に実行可能なステートメントを記述する必要があります。  null ステートメントは、実質的なステートメント本体が不要な場合にこの構文の要件を満たします。  
  
 null ステートメントは、他の C ステートメントと同様、前にラベルを付けることができます。  ステートメントではない項目 \(複合ステートメントの右中かっこ \(}\) など\) にラベルを付けるには、null ステートメントにラベルを付け、それを項目の直前に挿入して同じ効果を得ることができます。  
  
 null ステートメントの例を次に示します。  
  
```  
for ( i = 0; i < 10; line[i++] = 0 )  
     ;  
```  
  
 この例では、**for** ステートメントのループ式 `line[i++] = 0` によって、`line` の最初の 10 要素を 0 に初期化します。  それ以上のステートメントが不要であるため、ステートメント本体には null ステートメントを使用します。  
  
## 参照  
 [ステートメント](../c-language/statements-c.md)