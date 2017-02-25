---
title: "asctime_s、_wasctime_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wasctime_s"
  - "asctime_s"
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
  - "asctime_s"
  - "_wasctime_s"
  - "_tasctime_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tasctime_s 関数"
  - "_wasctime_s 関数"
  - "asctime_s 関数"
  - "tasctime_s 関数"
  - "時間構造体の変換"
  - "時間, 変換"
  - "wasctime_s 関数"
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# asctime_s、_wasctime_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列に `tm` の時刻構造体を変換します。  これらの関数は [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)"に説明されているように、セキュリティが強化された [asctime、\_wasctime](../../c-runtime-library/reference/asctime-wasctime.md) のバージョンです。  
  
## 構文  
  
```  
errno_t asctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const struct tm *_tm   
);  
errno_t _wasctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements  
   const struct tm *_tm   
);  
template <size_t size>  
errno_t asctime_s(   
   char (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
template <size_t size>  
errno_t _wasctime_s(   
   wchar_t (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
```  
  
#### パラメーター  
 `buffer`  
 \[\]結果の文字列を格納するバッファーへのポインター。  この関数は `numberOfElements`で指定されたサイズの有効なメモリ位置へのポインターを前提としています。  
  
 `numberOfElements`  
 \[\]結果を格納するために使用されるバッファーのサイズ。  
  
 `_tm`  
 \[\]日付\/時刻構造体。  この関数は `struct` 有効な `tm` オブジェクトへのポインターを前提としています。  
  
## 戻り値  
 正常に終了した場合は 0 を返します。  失敗した場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の戻り値はエラー コードです。  エラー コードは ERRNO.H.で定義されます。  詳細については、「[errno 定数](../../c-runtime-library/errno-constants.md)」を参照してください。  各エラー条件に対して返される実際のエラー コードを次の表に示します。  
  
### エラー条件  
  
|`buffer`|`numberOfElements`|`tm`|戻り値|`buffer` の値|  
|--------------|------------------------|----------|---------|-----------------|  
|`NULL`|どれでも可|どれでも可|`EINVAL`|変更されない|  
|存在しない`NULL` \(有効なメモリへのポインター\)|0|どれでも可|`EINVAL`|変更されない|  
|`NULL` 以外|サイズ \< 0\< 26|どれでも可|`EINVAL`|空の文字列|  
|`NULL` 以外|\>\= 26|`NULL`|`EINVAL`|空の文字列|  
|`NULL` 以外|\>\= 26|時間のコンポーネントの範囲の値から無効な時刻構造体または|`EINVAL`|空の文字列|  
  
> [!NOTE]
>  `wasctime_s` のエラー条件は `asctime_s` に似ています。ただし、してサイズ制限は、単語単位です。  
  
## 解説  
 `asctime` 関数は文字列を構造体として格納されている時刻を変換します。  `_tm` 値は通常、呼び出しから `gmtime` または `localtime`に取得されます。  関数が両方とも TIME.H.で定義されている `tm` の構造、入力するために使用できます。  
  
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
  
 変換された文字列は、現地のタイム ゾーンの設定に合わせて調整されます。  タイム ゾーンの環境変数とグローバル変数の定義については、"現地時間と [\_tzset](../Topic/_tzset.md) 関数の設定の詳細については、" [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)、[\_ftime、\_ftime32、\_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)と [localtime\_s、\_localtime32\_s、\_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) 関数を参照してください。  
  
 `asctime_s` で生成される結果の文字列は、26 文字からなる、フォーム `Wed Jan 02 02:03:55 1980\n\0`があります。  時刻は 24 時間制です。  すべてのフィールドは固定幅です。  改行文字と空白文字は、文字列の最後の 2 個の位置に配置されます。  2 番目のパラメーターとして渡された値これ以上である必要があります。  これはより小さい場合は、エラー コードを返します `EINVAL`は、返されます。  
  
 `_wasctime_s` 関数は、`asctime_s` 関数のワイド文字バージョンです。  それ以外では、`_wasctime_s` と `asctime_s` の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tasctime_s`|`asctime_s`|`asctime_s`|`_wasctime_s`|  
  
 C\+\+ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`asctime_s`|\<time.h\>|  
|`_wasctime_s`|\<time.h または\> wchar.h \<\>|  
  
## Security  
 バッファーが `NULL` ポインターではなく、ポインターが有効なバッファーを指す、関数は、内容が、場所を上書きできます。  これは、アクセス違反が発生することがあります。  
  
 [バッファー オーバーラン](http://msdn.microsoft.com/library/windows/desktop/ms717795) が自動サイズ引数がバッファーの実際のサイズよりも大きい場合に発生します。  
  
## 使用例  
 このプログラムは長整数 `aclock`にシステム時刻を置き、構造 `newtime` に変換し、出力の文字列形式に `asctime_s` 関数を使用して、変換します。  
  
```  
// crt_asctime_s.c  
#include <time.h>  
#include <stdio.h>  
  
struct tm newtime;  
__time32_t aclock;  
  
int main( void )  
{  
   char buffer[32];  
   errno_t errNum;  
   _time32( &aclock );   // Get time in seconds.  
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.  
  
   // Print local time as a string.  
  
   errNum = asctime_s(buffer, 32, &newtime);  
   if (errNum)  
   {  
       printf("Error code: %d", (int)errNum);  
       return 1;  
   }  
   printf( "Current date and time: %s", buffer );  
   return 0;  
}  
```  
  
  **現在の日付と時間: 水曜日 5 年 1 月 14 日 15:30: 17 2003 年**   
## 同等の .NET Framework 関数  
  
-   <xref:System.DateTime.ToLongDateString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToLongTimeString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToShortDateString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToShortTimeString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToString%2A?displayProperty=fullName>  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [ctime\_s、\_ctime32\_s、\_ctime64\_s、\_wctime\_s、\_wctime32\_s、\_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [\_ftime、\_ftime32、\_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s、\_gmtime32\_s、\_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s、\_localtime32\_s、\_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)