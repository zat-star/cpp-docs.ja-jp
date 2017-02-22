---
title: "文法の概要での定義 | Microsoft Docs"
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
  - "プリプロセッサ"
  - "プリプロセッサ, 定義"
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 文法の概要での定義
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

終端は構文定義内のエンドポイントです。  他の解決はありません。  終端には、予約語およびユーザー定義の識別子が含まれます。  
  
 非終端は構文内のプレースホルダーです。  ほとんどは、この構文概要の他の場所で定義されています。  定義は再帰的に行うことができます。  次の非終端は、『C\+\+ 言語リファレンス』の「[文法概要](../misc/grammar-summary-cpp.md)」で定義されています。  
  
 `constant`、*constant\-expression*、*identifier*、*keyword*、`operator`、`punctuator`  
  
 省略可能な構成要素には添字 "opt" を付けます。  たとえば、次の例では、省略可能な式が中かっこで囲まれています。  
  
 **{** *expression*opt **}**  
  
## 参照  
 [文法の概要](../preprocessor/grammar-summary-c-cpp.md)