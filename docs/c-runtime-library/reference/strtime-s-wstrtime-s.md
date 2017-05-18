---
title: "_strtime_s、_wstrtime_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wstrtime_s
- _strtime_s
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
- _wstrtime_s
- strtime_s
- wstrtime_s
- _strtime_s
dev_langs:
- C++
helpviewer_keywords:
- wstrtime_s function
- copying time to buffers
- strtime_s function
- _wstrtime_s function
- time, copying
- _strtime_s function
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
caps.latest.revision: 25
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
ms.openlocfilehash: e253a90b195ccd5aaf60942a243d8ebc50993b94
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="strtimes-wstrtimes"></a>_strtime_s、_wstrtime_s
現在の時刻をバッファーにコピーします。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) の説明にあるとおり、セキュリティが強化されたバージョンの [_strtime、_wstrtime](../../c-runtime-library/reference/strtime-wstrtime.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _strtime_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrtime_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strtime_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrtime_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `buffer`  
 バッファーの長さは少なくとも 10 バイトで、時刻が書き込まれます。  
  
 [入力] `numberOfElements`  
 バッファーのサイズ。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。  
  
 エラー状況が発生した場合は、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは ERRNO.H で定義されます。この関数によって生成される正確なエラーについては、下記の表をご覧ください。 エラー コードの詳細については、「[errno 定数](../../c-runtime-library/errno-constants.md)」をご覧ください。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`buffer`|`numberOfElements`|リターン|`buffer` の内容|  
|--------------|------------------------|------------|--------------------------|  
|`NULL`|(任意)|`EINVAL`|変更されない|  
|`NULL` ではない (有効なバッファーを指す)|0|`EINVAL`|変更されない|  
|`NULL` ではない (有効なバッファーを指す)|0 < サイズ < 9|`EINVAL`|空の文字列|  
|`NULL` ではない (有効なバッファーを指す)|サイズ > 9|0|コメントで指定されている書式設定の、現在の時刻|  
  
## <a name="security-issues"></a>セキュリティ上の問題  
 `numberOfElements` パラメーターが 9 よりも大きい場合、バッファーに無効な非 NULL 値を渡すとアクセス違反になります。  
  
 バッファーの実際のサイズより大きい `numberOfElements` の値を渡すと、バッファー オーバーランが発生します。  
  
## <a name="remarks"></a>コメント  
 これらの関数には、セキュリティを強化したバージョンとして `_strtime` および `_wstrtime` があります。 `_strtime_s`関数が指すバッファーに現在の現地時刻をコピー`timestr`です。 時刻は `hh:mm:ss` という形式で、`hh` は 24 時間表示で時間を表す 2 桁、`mm` は分を表す 2 桁、`ss` は秒を表す 2 桁です。 たとえば、文字列 `18:23:44` は午後 6 時 23 分 44 秒を表します。 バッファーは少なくとも 9 バイト長である必要があります。実際のサイズは、2 番目のパラメーターによって指定されます。  
  
 ワイド文字を扱う場合は、`_wstrtime` ではなく `_strtime` を使用します。`_wstrtime` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mapping"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrtime_s`|`_strtime_s`|`_strtime_s`|`_wstrtime_s`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_strtime_s`|\<time.h>|  
|`_wstrtime_s`|\<time.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// strtime_s.c  
  
#include <time.h>  
#include <stdio.h>  
  
int main()  
{  
    char tmpbuf[9];  
    errno_t err;  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    // Display operating system-style date and time.   
    err = _strtime_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
      exit(1);  
    }  
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );  
    err = _strdate_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
       exit(1);  
    }  
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );  
  
}  
```  
  
```Output  
OS time:            14:37:49  
OS date:            04/25/03  
```  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime、_mktime32、_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
