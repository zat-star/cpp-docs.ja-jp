---
title: "_strtime_s、_wstrtime_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wstrtime_s"
  - "_strtime_s"
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
  - "_wstrtime_s"
  - "strtime_s"
  - "wstrtime_s"
  - "_strtime_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strtime_s 関数"
  - "_wstrtime_s 関数"
  - "コピー時間 (バッファーへの書き込み時の)"
  - "strtime_s 関数"
  - "時間, コピー"
  - "wstrtime_s 関数"
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strtime_s、_wstrtime_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バッファーに現在の時刻をコピーします。  これらは [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)"に説明されているように、セキュリティが強化された [\_strtime \_wstrtime、](../Topic/_strtime,%20_wstrtime.md) のバージョンです。  
  
## 構文  
  
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
  
#### パラメーター  
 \[出力\] `buffer`  
 時間を記述する場合、バッファー、長の少なくとも 10 バイト。  
  
 \[入力\] `numberOfElements`  
 バッファーのサイズ。  
  
## 戻り値  
 正常に終了した場合は 0 を返します。  
  
 エラー条件が発生すると、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  エラーが発生した場合の戻り値はエラー コードです。  エラー コードは ERRNO.H で定義される; この関数によって生成される正確なエラーには、次の表を参照してください。  エラー コードの詳細については、「[errno の定数](../../c-runtime-library/errno-constants.md)」を参照してください。  
  
### エラー条件  
  
|`buffer`|`numberOfElements`|戻り値|`buffer` の内容|  
|--------------|------------------------|---------|------------------|  
|`NULL`|\(任意\)|`EINVAL`|変更されない|  
|`NULL` 以外 \(有効なバッファーを指し示している\)|0|`EINVAL`|変更されない|  
|`NULL` 以外 \(有効なバッファーを指し示している\)|サイズ \< 0 \< 9|`EINVAL`|空の文字列|  
|`NULL` 以外 \(有効なバッファーを指し示している\)|サイズ \> 9|0|"解説"で説明しているように書式設定された現在の時刻|  
  
## セキュリティの問題  
 バッファーに無効な以外の値を渡すと、アクセス違反が `numberOfElements` パラメーターが 9.よりも長くなります。  
  
 実際の buffer のサイズを超える `numberOfElements` の値を渡すと、バッファー オーバーランが発生します。  
  
## 解説  
 これらの関数は、`_strtime` 関数と `_wstrtime` 関数のセキュリティが強化されたバージョンです。  `_strtime_s` 関数は `timestr`が指すバッファーに現在の現地時刻をコピーします*。*時間は `hh` が 24 時間表記の時間を表す 2 桁の数値である `hh:mm:ss` として `mm` で時間を超える分を表す 2 桁の数値書式が指定され `ss` は秒を表す 2 桁の数値です。  たとえば、文字列 `18:23:44` は 6 アフリカーンス語.を過去 23 分と 44 秒を表します。バッファーの長さは少なくとも 9 バイト必要です; 実際のサイズは 2 番目のパラメーターで指定されます。  
  
 ワイド文字を扱う場合は、`_strtime` ではなく `_wstrtime` を使用します。`_wstrtime` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  それ以外では、これらの関数の動作は同じです。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tstrtime_s`|`_strtime_s`|`_strtime_s`|`_wstrtime_s`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_strtime_s`|\<time.h\>|  
|`_wstrtime_s`|\<time.h または\> wchar.h \<\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
  
  **OS の時間:            14:37: 49**  
**OS の日付:            04\/25\/03**   
## 同等の .NET Framework 関数  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime\_s、\_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime\_s、\_ctime32\_s、\_ctime64\_s、\_wctime\_s、\_wctime32\_s、\_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime\_s、\_gmtime32\_s、\_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s、\_localtime32\_s、\_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime、\_mktime32、\_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)