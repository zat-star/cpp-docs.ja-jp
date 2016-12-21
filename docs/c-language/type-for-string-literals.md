---
title: "文字列リテラルの型 | Microsoft Docs"
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
  - "リテラル文字列, 型"
  - "型 [C], リテラル文字列"
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 文字列リテラルの型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

文字列リテラルは、`char` の型配列 \(つまり、**char\[\]**\) を持ちます  \(ワイド文字列は、`wchar_t` の型配列 \(つまり、**wchar\_t\[ \]**\) を持ちます\)。 これは、文字列が型 `char` の要素の配列であることを意味しています。  配列の要素の数は、文字列の文字の数に 1 \(終端の null 文字\) を足した数と同じです。  
  
## 参照  
 [C 文字列リテラル](../c-language/c-string-literals.md)