---
title: "_get_printf_count_output | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_printf_count_output"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_printf_count_output"
  - "_get_printf_count_output"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%n 書式"
  - "_get_printf_count_output 関数"
  - "get_printf_count_output 関数"
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _get_printf_count_output
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

かどうかを示します。[printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)ファミリの関数は `%n` 形式をサポートします。  
  
## 構文  
  
```  
int _get_printf_count_output();  
```  
  
## 戻り値  
 `%n` がサポートされない場合 `%n` がサポートされている場合、ゼロ以外の場合は 0。  
  
## 解説  
 `%n` がサポートされていない場合 \(既定\)、`printf` 関数の書式指定文字列の `%n` が発生する可能性も [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  `%n` サポート \(有効な [\_set\_printf\_count\_output](../../c-runtime-library/reference/set-printf-count-output.md)\)、`%n` を提供します [printf 関数の型フィールド文字](../../c-runtime-library/printf-type-field-characters.md)"に説明されているように、参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_get_printf_count_output`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [\_set\_printf\_count\_output](../../c-runtime-library/reference/set-printf-count-output.md) 関数の例を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。