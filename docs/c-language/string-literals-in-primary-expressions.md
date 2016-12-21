---
title: "一次式の文字列リテラル | Microsoft Docs"
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
  - "リテラル文字列, 一次式の場合"
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 一次式の文字列リテラル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"文字列リテラル" は、二重引用符で囲まれた文字、ワイド文字、または隣接する文字のシーケンスです。  これらは変数ではないため、文字列リテラルおよびその要素はいずれも代入演算の左側のオペランドにはなりません。  文字列リテラルの型は `char` の配列 \(またはワイド文字列リテラルを表す `wchar_t` の配列\) です。  式に含まれる配列は、ポインターに変換されます。  文字列の詳細については、「[文字列リテラル](../c-language/c-string-literals.md)」を参照してください。  
  
## 参照  
 [C 一次式](../c-language/c-primary-expressions.md)