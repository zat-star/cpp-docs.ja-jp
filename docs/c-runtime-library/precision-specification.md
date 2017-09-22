---
title: "精度指定 | Microsoft Docs"
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
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c.math"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "printf 関数, 書式指定フィールド"
ms.assetid: dc59ea4e-d23a-4f1f-9881-2c919ebefb82
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 精度指定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

書式指定で、3 番目のフィールドは正確に固有です。  これは、換算の種類によって、文字列の文字数、10 進数、または出力される有効桁数を示す、負の 10 進整数に続くピリオドで \(\) で構成されます。  
  
 幅の指定とは異なり、精度の仕様によって、出力値の切り捨てまたは浮動小数点値の丸めることになることがあります。  0 および変換される値が 0 であるため `precision` を指定すると、結果は次の例のように文字出力、です:  
  
 `printf( "%.0d", 0 );      /* No characters output */`  
  
 精度の指定にアスタリスク \(\*\) の場合、引数リストに `int` の引数が値を指定します。  引数リストで、`precision` の引数には、この例に示す書式が設定される値を指定する必要があります:  
  
 `printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`  
  
 型は、次の表に示すように `precision` を省略した場合 `precision` の解釈や既定の精度が決まります。  
  
### 有効桁数の値の型のように  
  
|型|説明|既定の|  
|-------|--------|---------|  
|`a`, `A`|精度は点の後の桁数を指定します。|既定の精度は 6.です。  有効桁数が 0 の場合、小数点は `#` フラグが使用する印刷されません。|  
|`c`, `C`|精度は無効です。|文字が印刷されます。|  
|`d`, `i`, `u`, `o`, `x`, `X`|精度は印刷される最小桁数を指定します。  引数の桁数が `precision`未満の場合、出力値はゼロの左で埋められます。  値は、桁数が `precision`を超えると切捨てられません。|既定の精度は 1.です。|  
|`e`, `E`|精度は 10 進数の後に印刷する桁数を指定します。  最後の印刷された数字が丸められます。|既定の精度は 6.です。  `precision` が 0 の場合、またはピリオドとそれに続く数字なし \(\) が小数点は印刷されません。|  
|`f`|有効桁数の値が小数点以下の桁数を指定します。  小数点が表示されたら、少なくとも 1 桁がその前に表示されます。  値が数値の適切な数に丸められます。|既定の精度は 6.です。  `precision` が 0 の場合、またはピリオドとそれに続く数字なし \(\) が小数点は印刷されません。|  
|`g`, `G`|精度が印刷される有効桁数の最大値を指定します。|6 桁の有効桁数が出力され、後続のゼロは切り捨てられます。|  
|`s`, `S`|精度が印刷される最大文字数を指定します。  `precision` 以上の文字は表示されません。|文字が null 文字が出現するまで表示されます。|  
  
## 参照  
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [書式指定構文: printf 関数と wprintf 関数](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)   
 [フラグ ディレクティブ](../Topic/Flag%20Directives.md)   
 [printf 関数の文字幅指定](../c-runtime-library/printf-width-specification.md)   
 [サイズ指定](../c-runtime-library/size-specification.md)   
 [printf 関数の型フィールド文字](../c-runtime-library/printf-type-field-characters.md)