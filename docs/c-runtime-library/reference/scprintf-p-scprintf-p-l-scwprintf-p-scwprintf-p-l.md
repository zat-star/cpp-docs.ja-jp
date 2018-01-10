---
title: "_scprintf_p、_scprintf_p_l、_scwprintf_p、_scwprintf_p_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _scwprintf_p
- _scprintf_p_l
- _scwprintf_p_l
- _scprintf_p
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
- _scwprintf_p_l
- _sctprintf_p
- scprintf_p_l
- scprintf_p
- _sctprintf_p_l
- scwprintf_p
- _scprintf_p_l
- scwprintf_p_l
- _scprintf_p
- _scwprintf_p
dev_langs: C++
helpviewer_keywords:
- sctprintf_p_l function
- _scwprintf_p_l function
- scprintf_p_l function
- _scprintf_p function
- _scprintf_p_l function
- scprintf_p function
- sctprintf_p function
- _scwprintf_p function
- _sctprintf_p function
- scwprintf_p function
- scwprintf_p_l function
- _sctprintf_p_l function
ms.assetid: 8390d1e1-2826-47a4-851f-6635a88087cc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84e0cae612e1ee27b841089176ce1e2dfa368d29
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="scprintfp-scprintfpl-scwprintfp-scwprintfpl"></a>_scprintf_p、_scprintf_p_l、_scwprintf_p、_scwprintf_p_l
書式設定された文字列内の文字数を返します。その際、書式指定文字列で使用されるパラメーターの順序を指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
int _scprintf_p(  
   const char *format [,  
   argument] ...   
);  
int _scprintf_p_l(  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _scwprintf_p (  
   const wchar_t *format [,  
   argument] ...   
);  
int _scwprintf_p _l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 文字列が出力されたか、指定した書式設定コードを使用してファイルまたはバッファーに送信された場合は、生成される文字数を返します。 戻り値には、終端の NULL 文字は含まれません。 `_scwprintf_p` は、ワイド文字に対して同じ機能を果たします。  
  
 `_scprintf_p` と `_scprintf` の違いは、`_scprintf_p` では位置指定パラメーターをサポートし、これによって、書式指定文字列で引数を使用する順序を指定できることです。 詳細については、「[printf_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)」をご覧ください。  
  
 `format` が `NULL` ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は -1 を返し、 `errno` を `EINVAL`に設定します。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 各 `argument` (指定されている場合) は、`format` 中の対応する書式指定に応じて変換されます。 format は通常の文字で構成し、その形式と機能は [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 関数の `format` 引数と同じです。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_sctprintf_p`|`_scprintf_p`|`_scprintf_p`|`_scwprintf_p`|  
|`_sctprintf_p_l`|`_scprintf_p_l`|`_scprintf_p_l`|`_scwprintf_p_l`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_scprintf_p`, `_scprintf_p_l`|\<stdio.h>|  
|`_scwprintf_p`, `_scwprintf_p_l`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_scprintf、_scprintf_l、_scwprintf、_scwprintf_l](../../c-runtime-library/reference/scprintf-scprintf-l-scwprintf-scwprintf-l.md)   
 [_printf_p、_printf_p_l、_wprintf_p、_wprintf_p_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)