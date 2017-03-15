---
title: "C++ 区切り記号 | Microsoft Docs"
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
  - ";"
  - ","
  - "{"
  - "}"
  - "("
  - ")"
  - "["
  - "]"
  - "!"
  - "%"
  - "^"
  - "*"
  - """
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "区切り記号"
ms.assetid: 1521564c-a977-488a-9490-068079897592
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 区切り記号
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ の区切り記号はコンパイラに対する構文上およびセマンティック上の意味を持ちますが、それ自体は値を生成する演算を指定しません。  一部の区切り記号 \(単独または組み合わせ\) は、C\+\+ の演算子としても使用できたり、プリプロセッサで意味を持つことがあります。  
  
 次の文字が区切り記号と見なされます。  
  
```  
! % ^ & * ( ) – + = { } | ~  
[ ] \ ; ' : " < > ? , . / #  
```  
  
 区切り記号 **\[ \]**、**\( \)**、および **{ }** は、[変換フェーズ](../preprocessor/phases-of-translation.md) 4 の後は、ペアで使用する必要があります。  
  
## 参照  
 [構文規則](../cpp/lexical-conventions.md)