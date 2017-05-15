---
title: "_strtime、_wstrtime | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wstrtime
- _strtime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wstrtime
- _strtime
- wstrtime
- strtime
- _tstrtime
dev_langs:
- C++
helpviewer_keywords:
- strtime function
- _strtime function
- _wstrtime function
- copying time to buffers
- wstrtime function
- tstrtime function
- _tstrtime function
- time, copying
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
caps.latest.revision: 22
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: d442d5d1d32fe7ab1a6dfe4e16e64b3dd994b73e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="strtime-wstrtime"></a>_strtime、_wstrtime
時刻をバッファーにコピーします。 これらの関数のセキュリティを強化したバージョンを使用できます。「[_strtime_s、_wstrtime_s (_strtime_s、_wstrtime_s)](../../c-runtime-library/reference/strtime-s-wstrtime-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
char *_strtime(  
   char *timestr   
);  
wchar_t *_wstrtime(  
   wchar_t *timestr   
);  
template <size_t size>  
char *_strtime(  
   char (&timestr)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wstrtime(  
   wchar_t (&timestr)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `timestr`  
 時刻の文字列。  
  
## <a name="return-value"></a>戻り値  
 結果の文字列 `timestr` へのポインターを返します。  
  
## <a name="remarks"></a>コメント  
 `_strtime`関数が指すバッファーに現在の現地時刻をコピー`timestr`です。 時刻は `hh:mm:ss` という形式で、`hh` は 24 時間表示で時間を表す 2 桁、`mm` は分を表す 2 桁、`ss` は秒を表す 2 桁です。 たとえば、文字列 `18:23:44` は午後 6 時 23 分 44 秒を表します。 バッファーは 9 バイト以上の長さである必要があります。  
  
 ワイド文字を扱う場合は、`_wstrtime` ではなく `_strtime` を使用します。`_wstrtime` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 それ以外の場合、これらの関数の動作は同じです。`timestr` が `NULL` ポインターの場合、または `timestr` の形式が正しくない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 例外の続行が許可される場合、これらの関数は NULL を返し、`timestr` が NULL の場合は `errno` を `EINVAL` に設定します。`timestr` の形式が正しくない場合は `errno` を `ERANGE` に設定します。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrtime`|`_strtime`|`_strtime`|`_wstrtime`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_strtime`|\<time.h>|  
|`_wstrtime`|\<time.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strtime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char tbuffer [9];  
   _strtime( tbuffer ); // C4996  
   // Note: _strtime is deprecated; consider using _strtime_s instead  
   printf( "The current time is %s \n", tbuffer );  
}  
```  
  
```Output  
The current time is 14:21:44  
```  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime、_mktime32、_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
