---
title: "_get_output_format | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_output_format"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_output_format"
  - "_get_output_format"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_output_format 関数"
  - "get_output_format 関数"
  - "出力の書式指定"
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _get_output_format
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

出力形式フラグの現在の値を取得します。  
  
> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降では、CRT で使用できません。  
  
## 構文  
  
```  
unsigned int _get_output_format();  
```  
  
## 戻り値  
 出力形式フラグの現在の値。  
  
## 解説  
 出力形式フラグは、書式付き I\/O の機能を制御します。 現在、このフラグに指定できるのは 0 と `_TWO_DIGIT_EXPONENT` という 2 つの値です。`_TWO_DIGIT_EXPONENT` に設定すると、指数部の大きさによって 3 桁目が必要になる場合を除いて、浮動小数点数の指数部は 2 桁のみで出力されます。 このフラグを 0 に設定すると、浮動小数点数の指数部は 3 桁で出力され、必要な場合は 0 を埋め込んで 3 桁にされます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_get_output_format`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf\_s、\_printf\_s\_l、wprintf\_s、\_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [printf 関数の型フィールド文字](../c-runtime-library/printf-type-field-characters.md)   
 [\_set\_output\_format](../c-runtime-library/set-output-format.md)