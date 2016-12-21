---
title: "_vprintf_p、_vprintf_p_l、_vwprintf_p、_vwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vwprintf_p"
  - "_vprintf_p"
  - "_vprintf_p_l"
  - "_vwprintf_p_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "_vwprintf_p_l"
  - "vprintf_p"
  - "_vprintf_p_l"
  - "_vwprintf_p"
  - "vprintf_p_l"
  - "vwprintf_p_l"
  - "vwprintf_p"
  - "vtprintf_p"
  - "_vtprintf_p"
  - "_vprintf_p"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_vprintf_p 関数"
  - "_vprintf_p_l 関数"
  - "_vtprintf_p 関数"
  - "_vtprintf_p_l 関数"
  - "_vwprintf_p 関数"
  - "_vwprintf_p_l 関数"
  - "書式設定テキスト [C++]"
  - "vprintf_p 関数"
  - "vprintf_p_l 関数"
  - "vtprintf_p 関数"
  - "vtprintf_p_l 関数"
  - "vwprintf_p 関数"
  - "vwprintf_p_l 関数"
ms.assetid: 3f99bde3-c891-493d-908f-30559c421058
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _vprintf_p、_vprintf_p_l、_vwprintf_p、_vwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数リストへのポインターを使用して、書式付き出力を書き込みます。その際、引数を使用する順序を指定できます。  
  
## 構文  
  
```  
int _vprintf_p(  
   const char *format,  
   va_list argptr   
);  
int _vprintf_p_l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vwprintf_p(  
   const wchar_t *format,  
   va_list argptr   
);  
int _vwprintf_p_l(  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### パラメーター  
 `format`  
 書式の指定。  
  
 `argptr`  
 引数リストへのポインター。  
  
 `locale`  
 使用するロケール。  
  
 詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)」を参照してください。  
  
## 戻り値  
 `_vprintf_p` 関数と `_vwprintf_p` 関数は、書き込まれた文字数を返します。終端の null 文字は含まれません。出力エラーが発生した場合は、負の値を返します。  
  
## 解説  
 これらの関数は、引数リストへのポインターを使用して、指定されたデータを書式化して `stdout` に書き込みます。  これらの関数は、引数を使用する順序を指定できることを除いて `vprintf_s` と `vwprintf_s` と同じです。  詳細については、「[printf\_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)」を参照してください。  
  
 `_vwprintf_p` は `_vprintf_p` のワイド文字バージョンであり、ストリームが ANSI モードで開いている場合、この 2 つの関数の動作は同じです。  `_vprintf_p` では、UNICODE ストリームへの出力はサポートされていません。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
 `format` が null ポインターの場合、または書式指定文字列に無効な書式指定文字が含まれている場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_vtprintf_p`|`_vprintf_p`|`_vprintf_p`|`_vwprintf_p`|  
|`_vtprintf_p_l`|`_vprintf_p_l`|`_vprintf_p_l`|`_vwprintf_p_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|----------|------------|---------------|  
|`_vprintf_p`, `_vprintf_p_l`|\<stdio.h\> および \<stdarg.h\>|\<varargs.h\>\*|  
|`_vwprintf_p`, `_vwprintf_p_l`|\<stdio.h\> または \<wchar.h\>、および \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* UNIX V との互換性用  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)   
 [\_fprintf\_p、\_fprintf\_p\_l、\_fwprintf\_p、\_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [\_printf\_p、\_printf\_p\_l、\_wprintf\_p、\_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [\_sprintf\_p、\_sprintf\_p\_l、\_swprintf\_p、\_swprintf\_p\_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)   
 [vsprintf\_s、\_vsprintf\_s\_l、vswprintf\_s、\_vswprintf\_s\_l](../../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)   
 [va\_arg、va\_copy、va\_end、va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)   
 [\_vfprintf\_p、\_vfprintf\_p\_l、\_vfwprintf\_p、\_vfwprintf\_p\_l](../../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)   
 [\_printf\_p、\_printf\_p\_l、\_wprintf\_p、\_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf\_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)