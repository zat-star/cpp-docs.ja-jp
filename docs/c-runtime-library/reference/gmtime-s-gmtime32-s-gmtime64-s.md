---
title: "gmtime_s、_gmtime32_s、_gmtime64_s | Microsoft Docs"
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
  - "_gmtime32_s"
  - "gmtime_s"
  - "_gmtime64_s"
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
  - "_gmtime_s"
  - "gmtime64_s"
  - "gmtime32_s"
  - "_gmtime64_s"
  - "gmtime_s"
  - "_gmtime32_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "gmtime_s 関数"
  - "gmtime32_s 関数"
  - "時間関数"
  - "gmtime64_s 関数"
  - "_gmtime64_s 関数"
  - "時間構造体の変換"
  - "_gmtime_s 関数"
  - "_gmtime32_s 関数"
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# gmtime_s、_gmtime32_s、_gmtime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

時刻の値を構造体に変換します。 これらのバージョンは、 [\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) 」の説明に従って、セキュリティ強化機能を備えた [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)します。  
  
## 構文  
  
```  
errno_t gmtime_s(  
   struct tm* _tm,  
   const __time_t* time  
);  
errno_t _gmtime32_s(  
   struct tm* _tm,  
   const __time32_t* time  
);  
errno_t _gmtime64_s(  
   struct tm* _tm,  
   const __time64_t* time   
);  
```  
  
#### パラメーター  
 `_tm`  
 ポインター、 `tm` 構造体。 返された構造体の各フィールドには、`timer` 引数を現地時刻ではなく UTC で評価した値が格納されています。  
  
 `time`  
 格納されている時刻へのポインター。 時刻は、世界協定時刻 \(UTC: Coordinated Universal Time\) の 1970 年 1 月 1 日の深夜 00:00:00 から経過した時間 \(秒単位\) を表します。  
  
## 戻り値  
 正常終了した場合は 0 を返します。 戻り値は、障害が発生した場合、エラー コードです。 エラー コードが Errno.h; で定義されています。これらのエラーの一覧については、次を参照してください。 [errno](../../c-runtime-library/errno-constants.md)します。  
  
### エラー条件  
  
|`_tm`|`time`|リターン|値します。 `_tm`|  
|-----------|------------|----------|-----------------|  
|`NULL`|任意|`EINVAL`|変更されていません。|  
|いない `NULL` \(有効なメモリを指す\)|`NULL`|`EINVAL`|すべてのフィールドが\-1 に設定します。|  
|Not `NULL`|\< 0|`EINVAL`|すべてのフィールドが\-1 に設定します。|  
  
 」の説明に従って、最初の 2 つのエラー条件の場合、無効なパラメーター ハンドラーが呼び出される [パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## 解説  
 `_gmtime32_s` 機能は分割し、 `time` 値し、型の構造体に格納 `tm`, 、Time.h で定義します。 構造体のアドレスが渡された `_tm`です。 値 `time` は、通常の呼び出しから取得、 `time` 関数です。  
  
> [!NOTE]
>  ターゲット環境は、夏時間が有効になっているかどうかを判断するください。 C ランタイム ライブラリは、夏時間の計算の実装にアメリカ合衆国の規則を前提とします。  
  
 型の構造体のフィールドの各は `int`, 、次の表に示すようにします。  
  
 `tm_sec`  
 秒 \(0 ～ 59\)。  
  
 `tm_min`  
 分 \(0 ～ 59\)。  
  
 `tm_hour`  
 時 \(0 ～ 23\)。  
  
 `tm_mday`  
 日 \(1 ～ 31\)。  
  
 `tm_mon`  
 月 \(0 ～ 11、1 月 \= 0\)。  
  
 `tm_year`  
 年 \(実際の西暦から 1900 を引いた数\)  
  
 `tm_wday`  
 曜日 \(0 ～ 6、日曜日 \= 0\)。  
  
 `tm_yday`  
 年内の通算日 \(0 ～ 365、1 月 1 日 \= 0\)。  
  
 `tm_isdst`  
 `gmtime` では常に 0。  
  
 `_gmtime64_s`, 、が使用される、 `__time64_t` 構造体、ことができますを UTC 3000 年 12 月 31 日 23時 59分: 59 秒を表す日付 `gmtime32_s` のみ 2038 年 1 月 18 日 23時 59分: 59 までの日付を表します。 午前 0 時、1970 年 1 月 1 日は、これら両方の関数の日付範囲の下限値です。  
  
 `gmtime_s` 評価されるインライン関数は、 `_gmtime64_s` と `time_t` は `__time64_t`です。 コンパイラが `time_t` を古い 32 ビットの `time_t` として解釈するよう強制する必要がある場合には、`_USE_32BIT_TIME_T` を定義します。 これにより、その `gmtime_s` でインラインである `_gmtime32_s`です。 2038 年 1 月 18 日後に、アプリケーションが失敗して、64 ビット プラットフォーム上で許可されていないために、この操作は推奨されません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`gmtime_s`|\<time.h\>|  
|`_gmtime32_s`|\<time.h\>|  
|`_gmtime64_s`|\<time.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_gmtime64_s.c  
// This program uses _gmtime64_s to convert a 64-bit  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime_s to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm newtime;  
   __int64 ltime;  
   char buf[26];  
   errno_t err;  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:   
   err = _gmtime64_s( &newtime, &ltime );  
   if (err)  
   {  
      printf("Invalid Argument to _gmtime64_s.");  
   }  
  
   // Convert to an ASCII representation   
   err = asctime_s(buf, 26, &newtime);  
   if (err)  
   {  
      printf("Invalid Argument to asctime_s.");  
   }  
  
   printf( "Coordinated universal time is %s\n",   
           buf );  
}  
```  
  
```Output  
世界協定時刻は、Fri 年 4 月 25日 20時 12分: 33 2003年  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx)  
  
-   [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime\_s、\_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime、\_ctime32、\_ctime64、\_wctime、\_wctime32、\_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime、\_ftime32、\_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime\_s、\_localtime32\_s、\_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [\_mkgmtime、\_mkgmtime32、\_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime、\_mktime32、\_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)