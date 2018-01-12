---
title: "vfprintf_s、_vfprintf_s_l、vfwprintf_s、_vfwprintf_s_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- vfwprintf_s
- _vfprintf_s_l
- vfprintf_s
- _vfwprintf_s_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _vftprintf_s
- vfwprintf_s
- vfprintf_s
dev_langs: C++
helpviewer_keywords:
- vfprintf_s_l function
- vfwprintf_s_l function
- vfwprintf_s function
- _vfprintf_s_l function
- _vfwprintf_s_l function
- vftprintf_s_l function
- vfprintf_s function
- _vftprintf_s_l function
- formatted text [C++]
- _vftprintf_s function
ms.assetid: eab6f563-46e2-4806-963f-2b23f339ecdc
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71cc3edcecaf9cf9717fe38705a8e3a8660efb8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="vfprintfs-vfprintfsl-vfwprintfs-vfwprintfsl"></a>vfprintf_s、_vfprintf_s_l、vfwprintf_s、_vfwprintf_s_l
引数リストへのポインターを使用して、書式付き出力を書き込みます。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [vfprintf、_vfprintf_l、vfwprintf、_vfwprintf_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
int vfprintf_s(  
   FILE *stream,  
   const char *format,  
   va_list argptr   
);  
int _vfprintf_s_l(  
   FILE *stream,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int vfwprintf_s(  
   FILE *stream,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vfwprintf_s_l(  
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
  
 詳細については、「 [printf 関数と wprintf 関数の書式指定フィールド](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」を参照してください。  
  
## <a name="return-value"></a>戻り値  
 `vfprintf_s` 関数と `vfwprintf_s` 関数は、書き込まれた文字数を返します。終端の null 文字は含まれません。出力エラーが発生した場合は、負の値を返します。 `stream` または `format` が Null ポインターの場合、または書式指定文字列に無効な書式指定文字が含まれている場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数は -1 を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 これらの関数は、引数リストへのポインターを使用して、指定されたデータを書式化して `stream` に書き込みます。  
  
 セキュリティが強化されたバージョンは `format` 文字列に有効な書式指定文字が含まれていることを確認する点を除いて、セキュリティが万全でないバージョンと同じです。  
  
 `vfwprintf_s` は `vfprintf_s` のワイド文字バージョンであり、ストリームが ANSI モードで開いている場合、この 2 つの関数の動作は同じです。 `vfprintf_s` では、UNICODE ストリームへの出力はサポートされていません。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vftprintf_s`|`vfprintf_s`|`vfprintf_s`|`vfwprintf_s`|  
|`_vftprintf_s_l`|`_vfprintf_s_l`|`_vfprintf_s_l`|`_vfwprintf_s_l`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|  
|-------------|---------------------|----------------------|  
|`vfprintf_s`, `_vfprintf_s_l`|\<stdio.h> および \<stdarg.h>|\<varargs.h>*|  
|`vfwprintf_s`, `_vfwprintf_s_l`|\<stdio.h> または \<wchar.h>、および \<stdarg.h>|\<varargs.h>*|  
  
 \* UNIX V との互換性用。  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)   
 [fprintf、_fprintf_l、fwprintf、_fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg、va_copy、va_end、va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)