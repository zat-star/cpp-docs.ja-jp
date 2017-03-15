---
title: "リソース コンパイラの警告 RC4093 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC4093"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4093"
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# リソース コンパイラの警告 RC4093
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unescaped newline in character constant in inactive code  
  
 プリプロセッサ ディレクティブ `#if`、`#elif`、**\#ifdef**、または **\#ifndef** の定数式の評価結果が 0 になるため、後ろに続くコードは無効になります。  この無効になったコードの中に、単一引用符または二重引用符で囲まれた改行文字があります。  
  
 次の二重引用符までのすべてのテキストは、文字定数内にあると見なされます。