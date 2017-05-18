---
title: "_cprintf_p、_cprintf_p_l、_cwprintf_p、_cwprintf_p_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cprintf_p_l
- _cwprintf_p_l
- _cwprintf_p
- _cprintf_p
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
- cprintf_p
- cwprintf_p
- tcprintf_p
- _cwprintf_p_l
- _cprintf_p
- csprintf_p_l
- _cprintf_p_l
- _cwprintf_p
- _tcprintf_p
- cprintf_p_l
dev_langs:
- C++
helpviewer_keywords:
- _cwprintf_p_l function
- cwprintf_p function
- tcprintf_p_l function
- cprintf_p_l function
- _tcprintf_p function
- _tcprintf_p_l function
- _cprintf_p function
- _cprintf_p_l function
- cwprintf_p_l function
- _cwprintf_p function
- tcprintf_p function
- cprintf_p function
ms.assetid: 1f82fd7d-13c8-4c4a-a3e4-db0df3873564
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 6209795c87430de802309c199bc2902ed296287e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="cprintfp-cprintfpl-cwprintfp-cwprintfpl"></a>_cprintf_p、_cprintf_p_l、_cwprintf_p、_cwprintf_p_l
書式化してコンソールに出力します。書式指定文字列で位置指定パラメーターをサポートしています。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _cprintf_p(   
   const char * format [,   
   argument] ...   
);  
int _cprintf_p_l(   
   const char * format,  
   locale_t locale [,   
   argument] ...   
);  
int _cwprintf_p(  
   const wchar * format [,   
   argument] ...  
);  
int _cwprintf_p_l(  
   const wchar * format,  
   locale_t locale [,  
   argument] ...  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能なパラメーター。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 出力した文字数。エラーが発生した場合は負の値を返します。  
  
## <a name="remarks"></a>コメント  
 これらの関数は、文字を出力する `_putch` 関数と `_putwch` 関数を使用し、一連の文字や値を書式化して直接コンソールに出力します。 各 `argument` (指定されている場合) は、 `format`中の対応する書式指定に応じて変換され、格納されます。 書式には、[printf_p](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) 関数の `format` パラメーターと同じ形式と関数があります。 `_cprintf_p` と `cprintf_s` の違いは、`_cprintf_p` では位置指定パラメーターをサポートし、これによって、書式指定文字列で引数を使用する順序を指定できることです。 詳細については、「[printf_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)」を参照してください。  
  
 異なり、 `fprintf_p`、 `printf_p`、および`sprintf_p`関数も`_cprintf_p`また`_cwprintf_p`ライン フィード文字をキャリッジ リターンとライン フィード (CR-LF) の組み合わせに変換出力時にします。 `_cwprintf_p` を Windows NT で使用すると、Unicode 文字が表示される点に注意してください。 `_cprintf_p` と異なり、`_cwprintf_p` はコンソールの現在のロケール設定を使用します。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。  
  
 また、`_cprintf_s` 関数や `_cwprintf_s` 関数と同様に、これらの関数は入力ポインターを検証して文字列を書式化します。 `format` または `argument` が `NULL` の場合、あるいは書式指定文字列に無効な書式指定文字が含まれている場合、これらの関数は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は -1 を返し、 `errno` を `EINVAL`に設定します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcprintf_p`|`_cprintf_p`|`_cprintf_p`|`_cwprintf_p`|  
|`_tcprintf_p_l`|`_cprintf_p_l`|`_cprintf_p_l`|`_cwprintf_p_l`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_cprintf_p`、`_cprintf_p_l`|\<conio.h>|  
|`_cwprintf_p`、`_cwprintf_p_l`|\<conio.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_cprintf_p.c  
// This program displays some variables to the console  
// using the _cprintf_p function.  
  
#include <conio.h>  
  
int main( void )  
{  
    int         i = -16,  
                h = 29;  
    unsigned    u = 62511;  
    char        c = 'A';  
    char        s[] = "Test";  
  
    // Note that console output does not translate  
    // \n as standard output does. Use \r\n instead.  
    _cprintf_p( "%2$d  %1$.4x  %3$u  %4$c %5$s\r\n",   
                h, i, u, c, s );  
}  
```  
  
```Output  
-16  001d  62511  A Test  
```  
  
## <a name="see-also"></a>関連項目  
 [コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)   
 [_cscanf、_cscanf_l、_cwscanf、_cwscanf_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [_cscanf_s、_cscanf_s_l、_cwscanf_s、_cwscanf_s_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)   
 [_fprintf_p、_fprintf_p_l、_fwprintf_p、_fwprintf_p_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [_printf_p、_printf_p_l、_wprintf_p、_wprintf_p_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](../../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [_sprintf_p、_sprintf_p_l、_swprintf_p、_swprintf_p_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)   
 [_vfprintf_p、_vfprintf_p_l、_vfwprintf_p、_vfwprintf_p_l](../../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)   
 [_cprintf_s、_cprintf_s_l、_cwprintf_s、_cwprintf_s_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)   
 [printf_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)   
 [書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)
