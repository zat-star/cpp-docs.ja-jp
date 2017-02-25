---
title: "clock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "clock"
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
  - "clock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "計算 (プロセスが使用した CPU 時間を)"
  - "clock 関数"
  - "プロセッサ時間 (使用された)"
  - "プロセッサ時間 (使用された), 計算"
  - "時間, 計算 (プロセッサを)"
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# clock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

呼び出しプロセスにかかったウォール クロック時間を計算します。  
  
## 構文  
  
```  
clock_t clock( void );  
```  
  
## 戻り値  
 プロセス開始時からのウォール クロックの経過時間 \(秒単位の経過時間 `CLOCKS_PER_SEC`\) を返します。  経過時間を使用できない場合、関数は、`clock_t` としてキャストされた – 1 を返します。  
  
## 解説  
 `clock` 関数は、呼び出し元プロセスが使用したウォール クロック時間を通知します。  この時間は、厳密には ISO C99 \(正味の CPU 時間を戻り値にすることが規定されている\) に準拠していないことに注意してください。  CPU 時間を取得するには、Win32 の [GetProcessTimes](http://msdn.microsoft.com/library/windows/desktop/ms683223) 関数を使用します。  
  
 タイマーのティックは約 1\/`CLOCKS_PER_SEC` 秒です。  十分な時間が経過すると、`clock` から返される値が `clock_t` の最大の正の値を超えて負の値になり、最終的には絶対値の最大値を超過してロール オーバーします。  この値に依存して、214,748 秒 \(約 59 時間\) を超えて実行されるプロセスの合計経過時間を計算しないでください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`clock`|\<time.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_clock.c  
// This example prompts for how long  
// the program is to run and then continuously  
// displays the elapsed time for that period.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
void sleep( clock_t wait );  
  
int main( void )  
{  
   long    i = 6000000L;  
   clock_t start, finish;  
   double  duration;  
  
   // Delay for a specified time.  
   printf( "Delay for three seconds\n" );  
   sleep( (clock_t)3 * CLOCKS_PER_SEC );  
   printf( "Done!\n" );  
  
   // Measure the duration of an event.  
   printf( "Time to do %ld empty loops is ", i );  
   start = clock();  
   while( i-- )   
      ;  
   finish = clock();  
   duration = (double)(finish - start) / CLOCKS_PER_SEC;  
   printf( "%2.1f seconds\n", duration );  
}  
  
// Pauses for a specified number of milliseconds.  
void sleep( clock_t wait )  
{  
   clock_t goal;  
   goal = wait + clock();  
   while( goal > clock() )  
      ;  
}  
```  
  
  **Delay for three seconds**  
**Done\!  Time to do 6000000 empty loops is 0.1 seconds**    
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [difftime、\_difftime32、\_difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)