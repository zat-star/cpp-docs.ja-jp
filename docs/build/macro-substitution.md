---
title: "マクロでの代入 | Microsoft Docs"
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
helpviewer_keywords: 
  - "マクロ, NMAKE"
  - "NMAKE プログラム, マクロでの代入"
  - "代入マクロ (NMAKE の)"
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# マクロでの代入
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*macroname* が呼び出されると、定義文字列の中の *string1* が *string2* で置換されます。  
  
## 構文  
  
```  
$(macroname:string1=string2)  
```  
  
## 解説  
 マクロでの代入は、リテラルであり、大文字と小文字が区別されます。*string1* および *string2* では、マクロを呼び出すことはできません。  代入では、元の定義は変更されません。  [$$@](../build/filename-macros.md) を除き、どの組み込みマクロでもテキストを置換できます。  
  
 コロンの前に空白やタブは配置できません。コロンの後の文字は、リテラルとして解釈されます。  *string2* が null の場合は、すべての *string1* がマクロの定義文字列から削除されます。  
  
## 参照  
 [NMAKE マクロの使用](../build/using-an-nmake-macro.md)