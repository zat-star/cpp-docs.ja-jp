---
title: "NMAKE の致命的なエラー U1000 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1000"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1000"
ms.assetid: 49b9bd9e-f1bc-4b55-a171-c748e40b195e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE の致命的なエラー U1000
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

構文エラー : マクロ呼び出しに '\)' がありません。  
  
 マクロの呼び出しで、対応する右かっこ\(**\)**\)がない左かっこ \(**\(**\) があります。  正しい形式は **$\(***name***\)** です。ただし、1 文字の名前の場合は;`$`*n* と記述することもできます。