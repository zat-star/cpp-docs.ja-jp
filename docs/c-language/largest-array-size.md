---
title: "最大配列サイズ | Microsoft Docs"
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
ms.assetid: 4c782cf6-73f3-40b0-b306-229d22da4ee1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 最大配列サイズ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.3.3.4, 4.1.1** 配列の最大サイズ、つまり **size\_t** のサイズを保持するために必要な整数の型  
  
 `size_t` は、32 ビット x86 プラットフォームでは `unsigned int` です。  64 ビット プラットフォームでは、`size_t` typedef は**符号なし \_\_int64** です。  
  
## 参照  
 [配列とポインター](../c-language/arrays-and-pointers.md)