---
title: "vfprintf、_vfprintf_l、vfwprintf、_vfwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vfprintf_l"
  - "vfprintf"
  - "vfwprintf"
  - "_vfwprintf_l"
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
  - "vfwprintf"
  - "_vftprintf"
  - "vfprintf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_vfwprintf_l 関数"
  - "_vftprintf 関数"
  - "vfprintf 関数"
  - "_vftprintf_l 関数"
  - "vfprintf_l 関数"
  - "vftprintf_l 関数"
  - "vfwprintf_l 関数"
  - "vftprintf 関数"
  - "vfwprintf 関数"
  - "_vfprintf_l 関数"
  - "書式設定テキスト [C++]"
ms.assetid: 4443be50-cedf-40b2-b3e2-ff2b3af3b666
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vfprintf、_vfprintf_l、vfwprintf、_vfwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数リストへのポインターを使用して、書式付き出力を書き込みます。 これらの関数のより安全なバージョンが存在します。参照してください [vfprintf_s、_vfprintf_s_l、vfwprintf_s、_vfwprintf_s_l](../Topic/vfprintf_s,%20_vfprintf_s_l,%20vfwprintf_s,%20_vfwprintf_s_l.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
int vfprintf(  
   FILE *stream,  
   const char *format,  
   va_list argptr   
);  
int _vfprintf_l(  
   FILE *stream,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int vfwprintf(  
   FILE *stream,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vfwprintf_l(  
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `format`  
 書式の指定。  
  
 `argptr`  
 引数リストへのポインター。  
  
 `locale`  
 使用するロケール。  
  
 詳細については、次を参照してください。 [書式指定](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)します。  
  
## <a name="return-value"></a>戻り値  
 `vfprintf` 関数と `vfwprintf` 関数は、書き込まれた文字数を返します。終端の null 文字は含まれません。出力エラーが発生した場合は、負の値を返します。 いずれか `stream` または `format` null ポインター」の説明に従って、無効なパラメーター ハンドラーが呼び出される [パラメーターの検証](../../c-runtime-library/parameter-validation.md)します。 実行の継続が許可された場合、関数は -1 を返し、`errno` を `EINVAL` に設定します。  
  
 詳細については、その他のエラー コードは、次を参照してください。 [_doserrno、errno、_sys_errlist、および _sys_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)します。  
  
## <a name="remarks"></a>解説  
 これらの関数は、引数リストへのポインターを使用して、指定されたデータを書式化して `stream` に書き込みます。  
  
 `vfwprintf` は `vfprintf` のワイド文字バージョンであり、ストリームが ANSI モードで開いている場合、この 2 つの関数の動作は同じです。 `vfprintf` では、UNICODE ストリームへの出力はサポートされていません。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。 詳細については、次を参照してください。 [Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vftprintf`|`vfprintf`|`vfprintf`|`vfwprintf`|  
|`_vftprintf_l`|`_vfprintf_l`|`_vfprintf_l`|`_vfwprintf_l`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|-------------|---------------------|----------------------|  
|`vfprintf`, _`vfprintf_l`|\<stdio.h> および \<stdarg.h>|\<varargs.h>*|  
|`vfwprintf`, _`vfwprintf_l`|\<stdio.h> または \<wchar.h>、および \<stdarg.h>|\<varargs.h>*|  
  
 \* UNIX V との互換性に必要です。  
  
 互換性に関する追加情報を参照してください。 [互換性](../../c-runtime-library/compatibility.md) では、導入します。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当しない。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、次を参照してください。 [プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)します。  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)   
 [fprintf、_fprintf_l、fwprintf、_fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、_sprintf_l、swprintf、_swprintf_l、 \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg、va_copy、va_end、va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)