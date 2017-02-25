---
title: "vprintf_s、_vprintf_s_l、vwprintf_s、_vwprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vwprintf_s_l"
  - "vwprintf_s"
  - "_vprintf_s_l"
  - "vprintf_s"
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
  - "vprintf_s"
  - "vwprintf_s"
  - "_vtprintf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vprintf_s_l 関数"
  - "_vtprintf_s 関数"
  - "_vtprintf_s_l 関数"
  - "_vwprintf_s_l 関数"
  - "書式設定テキスト [C++]"
  - "vprintf_s 関数"
  - "vprintf_s_l 関数"
  - "vtprintf_s 関数"
  - "vtprintf_s_l 関数"
  - "vwprintf_s 関数"
  - "vwprintf_s_l 関数"
ms.assetid: cf864996-a530-4b40-9c30-54c4cef439c8
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# vprintf_s、_vprintf_s_l、vwprintf_s、_vwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数リストへのポインターを使用して、書式付き出力を書き込みます。  [vprintf、\_vprintf\_l、vwprintf、\_vwprintf\_l](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md) のこれらのバージョンは、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、セキュリティが強化されています。  
  
## 構文  
  
```  
int vprintf_s(  
   const char *format,  
   va_list argptr   
);  
int _vprintf_s_l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int vwprintf_s(  
   const wchar_t *format,  
   va_list argptr   
);  
int _vwprintf_s_l(  
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
 `vprintf_s` 関数と `vwprintf_s` 関数は、書き込まれた文字数を返します。終端の null 文字は含まれません。出力エラーが発生した場合は、負の値を返します。  `format` が null ポインターの場合、または書式指定文字列に無効な書式指定文字が含まれている場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 これらの関数は、引数リストへのポインターを使用して、指定されたデータを書式化して `stdout` に書き込みます。  
  
 これらの関数のセキュリティが強化されたバージョンは、書式指定文字列に有効な書式指定文字が含まれていることを確認する点を除いて、`vprintf` 関数および `vwprintf` 関数と同じです。  
  
 `vwprintf_s` は `vprintf_s` のワイド文字バージョンであり、ストリームが ANSI モードで開いている場合、この 2 つの関数の動作は同じです。  `vprintf_s` では、UNICODE ストリームへの出力はサポートされていません。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_vtprintf_s`|`vprintf_s`|`vprintf_s`|`vwprintf_s`|  
|`_vtprintf_s_l`|`_vprintf_s_l`|`_vprintf_s_l`|`_vwprintf_s_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|----------|------------|---------------|  
|`vprintf_s`, `_vprintf_s_l`|\<stdio.h\> および \<stdarg.h\>|\<varargs.h\>\*|  
|`vwprintf_s`, `_vwprintf_s_l`|\<stdio.h\> または \<wchar.h\>、および \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* UNIX V との互換性用  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)   
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg、va\_copy、va\_end、va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)