---
title: "printf 関数の文字幅指定 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "printf 関数, 書式指定フィールド"
  - "printf 関数, 幅指定"
ms.assetid: 8b4a1b1e-bf6e-414f-a1b6-a9b6f1b6ce92
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# printf 関数の文字幅指定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

書式指定で、2 番目のフィールドは、幅指定です。  `width` の引数が出力される最小文字数を制御する負の 10 進整数です。  出力値の文字数が指定された幅より小さい場合は、空白は左揃えフラグ \(`-`\) であるかどうかを示す値依存の左側または右側に最低幅指定に達するまで追加されます。  `width` が 0 がプレフィックスとして付けられている場合、先行ゼロは整数または浮動小数点数に変換する変換は無限大または非数になると最小幅に到達するまでを除き、追加されます。  
  
 幅の指定は、値をまたは。  出力値の文字数が指定された幅より大きいか、または `width` を指定しない場合、値のすべての文字を [精度](../c-runtime-library/precision-specification.md) 仕様に応じて出力されます。  
  
 幅の指定にアスタリスク \(`*`\) の場合、引数リストに `int` の引数が値を指定します。  `width` の引数は、この例に示すように引数リストで書式設定された値を入力する必要があります:  
  
 `printf("%0*f", 5, 3);  /* 00003 is output */`  
  
 書式指定の `width` 見つからないか小さい値によって出力値の切り捨てが行われません。  変換の結果が `width` 値より広い場合、変換結果が含まれるように、フィールドが拡張されます。  
  
## 参照  
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [書式指定構文: printf 関数と wprintf 関数](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)   
 [フラグ ディレクティブ](../Topic/Flag%20Directives.md)   
 [精度指定](../c-runtime-library/precision-specification.md)   
 [サイズ指定](../c-runtime-library/size-specification.md)   
 [printf 関数の型フィールド文字](../c-runtime-library/printf-type-field-characters.md)