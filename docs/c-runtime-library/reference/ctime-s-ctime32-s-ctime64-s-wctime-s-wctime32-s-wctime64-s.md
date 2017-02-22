---
title: "ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ctime64_s"
  - "_wctime32_s"
  - "ctime_s"
  - "_wctime64_s"
  - "_ctime32_s"
  - "_wctime_s"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "ctime64_s"
  - "_ctime32_s"
  - "_tctime32_s"
  - "_ctime64_s"
  - "_wctime_s"
  - "_tctime_s"
  - "_tctime64_s"
  - "ctime_s"
  - "ctime32_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctime32_s 関数"
  - "ctime64_s 関数"
  - "_tctime64_s 関数"
  - "_wctime_s 関数"
  - "tctime_s 関数"
  - "_wctime64_s 関数"
  - "ctime_s 関数"
  - "ctime32_s 関数"
  - "_ctime64_s 関数"
  - "tctime64_s 関数"
  - "wctime64_s 関数"
  - "wctime_s 関数"
  - "_tctime_s 関数"
  - "tctime32_s 関数"
  - "wctime32_s 関数"
  - "時間、変換"
  - "_ctime32_s 関数"
  - "_tctime32_s 関数"
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

時刻の値を文字列に変換し、ローカル タイム ゾーンの設定を調整します。 これらのバージョンは、 [ctime、\_ctime64、\_wctime、\_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) 」の説明に従って、セキュリティ強化機能を備えた [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)します。  
  
## 構文  
  
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
  
#### パラメーター  
 \[out\] `buffer`  
 26 文字を保持するのに十分である必要があります。 文字の文字列の結果へのポインターまたは `NULL`場合。  
  
-   `time` 1970 年 1 月 1 日午前 0 時 \(utc\) より前に、の日付を表します。  
  
-   使用する場合 `_ctime32_s` または `_wctime32_s` と `time` 23時 59分: 59 以後 2038 年 1 月 18 日 \(utc\) 日付を表します。  
  
-   使用する場合 `_ctime64_s` または `_wctime64_s` と `time` UTC 3000 年 12 月 31 日 23時 59分: 59 秒後の日付を表します。  
  
-   使用する場合 `_ctime_s` または `_wctime_s`, 、これらの関数は前の関数のラッパーです。 「解説」を参照してください。  
  
 \[入力\] `numberOfElements`  
 バッファーのサイズ。  
  
 \[in\] t`ime`  
 格納されている時刻へのポインター。  
  
## 戻り値  
 正常終了した場合は 0 を返します。 無効なパラメーターによる障害が発生する場合は、無効なパラメーター ハンドラーが呼び出される」の説明に従って [パラメーターの検証](../../c-runtime-library/parameter-validation.md)します。 実行の継続が許可された場合は、エラー コードが返されます。 エラー コードは ERRNO で定義されます。H です。これらのエラーの一覧については、次を参照してください。 [errno](../../c-runtime-library/errno-constants.md)します。 各エラーに対してスロー実際のエラー コードを次の表に示します。  
  
## エラー条件  
  
|`buffer`|`numberOfElements`|`time`|リターン|値します。 `buffer`|  
|--------------|------------------------|------------|----------|--------------------|  
|`NULL`|任意|任意|`EINVAL`|変更されません。|  
|いない `NULL` \(有効なメモリを指す\)|0|任意|`EINVAL`|変更されません。|  
|Not `NULL`|0 \< \< 26 のサイズ|任意|`EINVAL`|空の文字列|  
|Not `NULL`|\>\= 26|NULL|`EINVAL`|空の文字列|  
|Not `NULL`|\>\= 26|\< 0|`EINVAL`|空の文字列|  
  
## 解説  
 `ctime_s` 関数として格納されている時刻値に変換する [time\_t](../../c-runtime-library/standard-types.md) 文字の文字列に構造体。`time` 値は、通常の呼び出しから取得 [時間](../Topic/time,%20_time32,%20_time64.md), 、午前 0 時から経過した秒数を返します \(00: 00:00\)、世界協定時刻 \(UTC\) 1970 年 1 月 1 日です。 戻り値の文字列では、26 文字であり、形式は。  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24 時間制が使用されます。 すべてのフィールドを持つ定数の幅。 文字列の最後の 2 つの位置は、改行文字 \('\\n'\) と null 文字 \('\\0'\) で使用します。  
  
 変換された文字列は、ローカル タイム ゾーンの設定に従っても調整します。 参照してください、 `time`, 、[\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), 、および [localtime32\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) ローカル時刻を構成する方法についての関数と [\_tzset](../Topic/_tzset.md) については、タイム ゾーンの環境とグローバル変数を定義する関数。  
  
 `_wctime32_s` `_wctime64_s` のワイド文字バージョン `_ctime32_s` と `_ctime64_s`; ワイド文字列へのポインターを返します。 それ以外の場合、 `_ctime64_s`, 、`_wctime32_s`, 、および `_wctime64_s` と同様に動作 `_ctime32_s`します。  
  
 `ctime_s` 評価されるインライン関数は、 `_ctime64_s` と `time_t` は `__time64_t`です。 コンパイラが `time_t` を古い 32 ビットの `time_t` として解釈するよう強制する必要がある場合には、`_USE_32BIT_TIME_T` を定義します。 これにより、その `ctime_s` を評価する `_ctime32_s`です。 2038 年 1 月 18 日後に、アプリケーションが失敗して、64 ビット プラットフォーム上で許可されていないために、この操作は推奨されません。  
  
 C\+\+ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tctime_s`|`ctime_s`|`ctime_s`|`_wctime_s`|  
|`_tctime32_s`|`_ctime32_s`|`_ctime32_s`|`_wctime32_s`|  
|`_tctime64_s`|`_ctime64_s`|`_ctime64_s`|`_wctime64_s`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`ctime_s,`<br /><br /> `_ctime32_s,`<br /><br /> `_ctime64_s`|\<time.h\>|  
|`_wctime_s,`<br /><br /> `_wctime32_s,`<br /><br /> `_wctime64_s`|\< time.h \> または \< wchar.h \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
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
  
## 出力例  
  
```  
The time is Fri Apr 25 13:03:39 2003  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime\_s、\_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime、\_ctime32、\_ctime64、\_wctime、\_wctime32、\_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime、\_ftime32、\_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s、\_gmtime32\_s、\_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s、\_localtime32\_s、\_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)