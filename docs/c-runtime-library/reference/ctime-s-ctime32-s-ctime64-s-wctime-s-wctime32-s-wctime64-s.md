---
title: "ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ctime64_s
- _wctime32_s
- ctime_s
- _wctime64_s
- _ctime32_s
- _wctime_s
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
- ctime64_s
- _ctime32_s
- _tctime32_s
- _ctime64_s
- _wctime_s
- _tctime_s
- _tctime64_s
- ctime_s
- ctime32_s
dev_langs:
- C++
helpviewer_keywords:
- _wctime32_s function
- ctime64_s function
- _tctime64_s function
- _wctime_s function
- tctime_s function
- _wctime64_s function
- ctime_s function
- ctime32_s function
- _ctime64_s function
- tctime64_s function
- wctime64_s function
- wctime_s function
- _tctime_s function
- tctime32_s function
- wctime32_s function
- time, converting
- _ctime32_s function
- _tctime32_s function
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 371ca59a6002cd5936771f1ac9cea7c39b192cee
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="ctimes-ctime32s-ctime64s-wctimes-wctime32s-wctime64s"></a>ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s
時刻値を文字列に変換し、ローカルの時間帯設定に合わせて調整します。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) で説明されているように、セキュリティが強化されたバージョンの [ctime、_ctime64、_wctime、_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t ctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _ctime32_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _ctime64_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time64_t *time )  
;  
errno_t _wctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _wctime32_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _wctime64_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time64_t *time   
);  
template <size_t size>  
errno_t _ctime32_s(   
   char (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _ctime64_s(   
   char (&buffer)[size],  
   const __time64_t *time  
); // C++ only  
template <size_t size>  
errno_t _wctime32_s(   
   wchar_t (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _wctime64_s(   
   wchar_t (&buffer)[size],  
   const __time64_t *time   
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `buffer`  
 26 文字を収納できる大きさが必要です。 文字の文字列の結果へのポインターまたは`NULL`場合。  
  
-   `time` が 1970 年 1 月 1 日の深夜 0 時 (協定世界時) よりも前の日付を示している場合。  
  
-   `_ctime32_s` または `_wctime32_s` と `time` が 2038 年 1 月 18 日の 23:59:59 時 (協定世界時) よりも後の日付を示している場合。  
  
-   `_ctime64_s` または `_wctime64_s` と `time` が 3000 年 12 月 31 日の 23:59:59 時 (協定世界時) よりも後の日付を示している場合。  
  
-   `_ctime_s` または `_wctime_s` を使用する場合、これらの関数は前の関数のラッパーになります。 「解説」を参照してください。  
  
 [入力] `numberOfElements`  
 バッファーのサイズ。  
  
 [入力] `time`  
 格納されている時刻へのポインター。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0。 無効なパラメーターに起因して障害が発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、エラー コードが返されます。 エラー コードは ERRNO.H で定義されます。これらのエラーの一覧については、[errno](../../c-runtime-library/errno-constants.md) を参照してください。 各エラー条件に対してスローされる実際のエラー コードを、次の表に示します。  
  
## <a name="error-conditions"></a>エラー条件  
  
|`buffer`|`numberOfElements`|`time`|リターン|`buffer` の値|  
|--------------|------------------------|------------|------------|-----------------------|  
|`NULL`|任意|任意|`EINVAL`|変更されない|  
|`NULL` ではない (有効なメモリを指す)|0|任意|`EINVAL`|変更されない|  
|`NULL` ではない|0< サイズ < 26|任意|`EINVAL`|空の文字列|  
|`NULL` ではない|>= 26|NULL|`EINVAL`|空の文字列|  
|`NULL` ではない|>= 26|< 0|`EINVAL`|空の文字列|  
  
## <a name="remarks"></a>コメント  
 `ctime_s` 関数は、[time_t](../../c-runtime-library/standard-types.md) 構造として格納されている時間を文字列に変換します。 `time` 値は通常、協定世界時刻 (UTC) の 1970 年 1 月 1 日の真夜中 (00:00:00) 以降の経過時間を返す [time](../../c-runtime-library/reference/time-time32-time64.md) を呼び出すことで取得されます。 戻り値には厳密に 26 文字が含まれ、次の形式になります。  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24 時間制が使用されます。 すべてのフィールドには一定の幅があります。 文字列の最後の 2 つの位置には、改行文字 ('\n') と null 文字 ('\0') が入ります。  
  
 変換された文字列も、ローカル タイム ゾーンの設定に従って調整されます。 ローカル タイムの設定の詳細については、`time`、[_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)、[localtime32_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) の関数を参照してください。また、タイム ゾーン環境とグローバル変数の定義の詳細については、[_tzset](../../c-runtime-library/reference/tzset.md) 関数を参照してください。  
  
 `_wctime32_s` と `_wctime64_s` は `_ctime32_s` と `_ctime64_s` のワイド文字バージョンです。ワイド文字列のポインターを返します。 それ以外では、`_ctime64_s`、`_wctime32_s`、`_wctime64_s` の動作は `_ctime32_s` と同じです。  
  
 `ctime_s` は `_ctime64_s` と評価されるインライン関数であり、`time_t` は `__time64_t` と等価です。 コンパイラが `time_t` を古い 32 ビットの `time_t` として解釈するよう強制する必要がある場合には、`_USE_32BIT_TIME_T` を定義します。 これにより、`ctime_s` の値は `_ctime32_s` になります。 この方法はお勧めしません。2038 年 1 月 18 日より後にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。  
  
 C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime_s`|`ctime_s`|`ctime_s`|`_wctime_s`|  
|`_tctime32_s`|`_ctime32_s`|`_ctime32_s`|`_wctime32_s`|  
|`_tctime64_s`|`_ctime64_s`|`_ctime64_s`|`_wctime64_s`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`ctime_s`、`_ctime32_s`、`_ctime64_s`|\<time.h>|  
|`_wctime_s`、`_wctime32_s`、`_wctime64_s`|\<time.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_wctime_s.c  
/* This program gets the current  
 * time in time_t form and then uses _wctime_s to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
#define SIZE 26  
  
int main( void )  
{  
   time_t ltime;  
   wchar_t buf[SIZE];  
   errno_t err;  
  
   time( &ltime );  
  
   err = _wctime_s( buf, SIZE, &ltime );  
   if (err != 0)  
   {  
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);  
   }  
   wprintf_s( L"The time is %s\n", buf );  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
The time is Fri Apr 25 13:03:39 2003  
```  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)
