---
title: "asctime、_wasctime | Microsoft Docs"
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
  - "_wasctime"
  - "asctime"
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
  - "_tasctime"
  - "asctime"
  - "_wasctime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tasctime 関数"
  - "_wasctime 関数"
  - "asctime 関数"
  - "tasctime 関数"
  - "時間構造体の変換"
  - "時間, 変換"
  - "wasctime 関数"
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# asctime、_wasctime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列に `tm` の時刻構造体を変換します。  これらの関数のセキュリティを強化したバージョンについては、「[asctime\_s、\_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)」を参照してください。  
  
## 構文  
  
```  
char *asctime(   
   const struct tm *timeptr   
);  
wchar_t *_wasctime(   
   const struct tm *timeptr   
);  
```  
  
#### パラメーター  
 `timeptr`  
 日付\/時刻構造体。  
  
## 戻り値  
 `asctime` は 結果の文字列へのポインターを返します。; `_wasctime` はワイド文字列の結果へのポインターを返します。  エラー戻り値はありません。  
  
## 解説  
 これらの関数のセキュリティが強化されたバージョンを使用して; [\_gmtime32\_s、\_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)を参照してください。  
  
 `asctime` 関数は文字列を構造体として格納されている時刻を変換します。  `timeptr` 値は通常、呼び出しからの両方 `tm` 構造体へのポインターを返す `localtime`または TIME.H.で定義されている `gmtime` 取得されます。  
  
|timeptr のメンバー|値|  
|-------------------|-------|  
|`tm_hour`|深夜 0–23\) からの経過時間|  
|`tm_isdst`|夏時間が有効な場合は正; 夏時間が有効な場合は 0; 夏時間が不明な場合は負。  C のランタイム ライブラリには、夏時間 \(DST\) の計算を実装するための米国の規則が使用されます。|  
|`tm_mday`|月 \(1–31\) の日|  
|`tm_min`|時間 \(分後の 0–59\)|  
|`tm_mon`|月 \(0–11; 1 年 \= 0\)|  
|`tm_sec`|分 \(0–59 後の秒\)|  
|`tm_wday`|曜日 \(0–6 の日; 日曜日 \= 0\)|  
|`tm_yday`|年 \(0–365 の日; 1 年 1 月 1 日 \= 0\)|  
|`tm_year`|年 \(実際の西暦から 1900 を引いた数\)|  
  
 変換された文字列は、現地のタイム ゾーンの設定に合わせて調整されます。  現地時間の設定の詳細については、タイム ゾーンの環境変数とグローバル変数の定義については、" [時間](../Topic/time,%20_time32,%20_time64.md)、[\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)と [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 関数と [\_tzset](../Topic/_tzset.md) 関数を参照してください。  
  
 `asctime` で生成される結果の文字列は、26 文字からなる、フォーム `Wed Jan 02 02:03:55 1980\n\0`があります。  時刻は 24 時間制です。  すべてのフィールドは固定幅です。  改行文字と空白文字は、文字列の最後の 2 個の位置に配置されます。  `asctime` が 返す文字列を保持するために、一つの静的に割り当てたバッファーを使用します。  この関数を呼び出すたびに、前の呼び出しの結果は破棄されます。  
  
 `_wasctime` 関数は、`asctime` 関数のワイド文字バージョンです。  それ以外では、`_wasctime` と `asctime` の動作は同じです。  
  
 これらの関数では、パラメーターの検証が行われます。  `timeptr` が null ポインターの場合、または範囲の値を含む場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tasctime`|`asctime`|`asctime`|`_wasctime`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`asctime`|\<time.h\>|  
|`_wasctime`|\<time.h または\> wchar.h \<\>|  
  
## 使用例  
 このプログラムは長整数 `aclock`にシステム時刻を置き、構造 `newtime` に変換し、出力の文字列形式に `asctime` 関数を使用して、変換します。  
  
```  
// crt_asctime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
    struct tm   *newTime;  
    time_t      szClock;  
  
    // Get time in seconds  
    time( &szClock );  
  
    // Convert time to struct tm form   
    newTime = localtime( &szClock );  
  
    // Print local time as a string.  
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996  
    // Note: asctime is deprecated; consider using asctime_s instead  
}  
```  
  
  **現在の日付と時間: 太陽の 2 年 1 月 03 日 11:38: 58 2002 年**   
## 同等の .NET Framework 関数  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [ctime、\_ctime32、\_ctime64、\_wctime、\_wctime32、\_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime、\_ftime32、\_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、\_localtime32、\_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)   
 [asctime\_s、\_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)