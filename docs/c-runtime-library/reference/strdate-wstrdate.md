---
title: "_strdate、_wstrdate | Microsoft Docs"
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
  - "_strdate"
  - "_wstrdate"
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
  - "_tstrdate"
  - "wstrdate"
  - "_wstrdate"
  - "_strdate"
  - "strdate"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "strdate 関数"
  - "日付、コピー"
  - "tstrdate 関数"
  - "_wstrdate 関数"
  - "wstrdate 関数"
  - "_strdate 関数"
  - "_tstrdate 関数"
  - "コピー (日付を)"
ms.assetid: de8e4097-58f8-42ba-9dcd-cb4d9a9f1696
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strdate、_wstrdate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のシステム日付をバッファーにコピーします。  これらの関数のセキュリティを強化したバージョンについては、「[\_strdate\_s、\_wstrdate\_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md)」を参照してください。  
  
## 構文  
  
```  
char *_strdate(  
   char *datestr   
);  
wchar_t *_wstrdate(  
   wchar_t *datestr   
);  
template <size_t size>  
char *_strdate(  
   char (&datestr)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wstrdate(  
   wchar_t (&datestr)[size]  
); // C++ only  
```  
  
#### パラメーター  
 `datestr`  
 格納するバッファーへのポインター書式設定された日付文字列。  
  
## 戻り値  
 これらの関数は、結果の文字列 `datestr`へのポインターを返します。  
  
## 解説  
 これらの関数のセキュリティが強化されたバージョンを使用して; [\_strdate\_s、\_wstrdate\_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md)を参照してください。  より安全な関数を使用することをお勧めします。  
  
 `_strdate` 関数は `datestr`、書式設定された `mm`\/`dd`\/`yy`が指すバッファーに `mm` は月を表す 2 桁の数値の場合、現在のシステム日付を `dd` です日を表す 2 桁の数値 `yy` コピーし、年の最後の 2 桁です。  たとえば、文字列 `12/05/99` は 1999 年 12 月 5 日を表します。  バッファーの長さは少なくとも 9 バイト必要です。  
  
 `datestr` が `NULL` ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
 ワイド文字を扱う場合は、`_strdate` ではなく `_wstrdate` を使用します。`_wstrdate` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  それ以外では、これらの関数の動作は同じです。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tstrdate`|`_strdate`|`_strdate`|`_wstrdate`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_strdate`|\<time.h\>|  
|`_wstrdate`|\<time.h または\> wchar.h \<\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// strdate.c  
// compile with: /W3  
#include <time.h>  
#include <stdio.h>  
int main()  
{  
    char tmpbuf[9];  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    printf( "OS date: %s\n", _strdate(tmpbuf) ); // C4996  
    // Note: _strdate is deprecated; consider using _strdate_s instead  
}  
```  
  
  **OS の日付: 04\/25\/03**   
## 同等の .NET Framework 関数  
 [System::DateTime::Parse](https://msdn.microsoft.com/en-us/library/system.datetime.parse.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、\_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime、\_ctime32、\_ctime64、\_wctime、\_wctime32、\_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime、\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、\_localtime32、\_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime、\_mktime32、\_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)