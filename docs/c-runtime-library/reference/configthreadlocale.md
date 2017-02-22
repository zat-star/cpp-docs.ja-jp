---
title: "_configthreadlocale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_configthreadlocale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_configthreadlocale"
  - "configthreadlocale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_configthreadlocale 関数"
  - "configthreadlocale 関数"
  - "ロケール, スレッドごとの"
  - "スレッドごとのロケール"
  - "スレッドのロケール"
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _configthreadlocale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スレッドごとのロケール オプションを設定します。  
  
## 構文  
  
```  
int _configthreadlocale(  
   int type  
);  
```  
  
#### パラメーター  
 `type`  
 設定する値。  次の一覧に示すオプションのいずれかを指定します。  
  
## 戻り値  
 スレッドごとのロケールの以前のステータス \(`_DISABLE_PER_THREAD_LOCALE` または `_ENABLE_PER_THREAD_LOCALE`\) を返します。エラー発生時には \-1 を返します。  
  
## 解説  
 `_configurethreadlocale` 関数は、スレッド固有のロケールの使用を制御するために使用します。  次のオプションのいずれかを使用して、スレッドごとのロケールの状態を指定または確認します。  
  
 `_ENABLE_PER_THREAD_LOCALE`  
 現在のスレッドでスレッド固有のロケールを使用させます。  今後このスレッドで `setlocale` を呼び出すと、スレッド独自のロケールだけに影響します。  
  
 `_DISABLE_PER_THREAD_LOCALE`  
 現在のスレッドでグローバルなロケールを使用させます。  今後このスレッドで `setlocale` を呼び出すと、グローバルなロケールを使用する他のスレッドに影響します。  
  
 `0`  
 この特定のスレッドの現在の設定を取得します。  
  
 これらの関数は、`setlocale`、`_tsetlocale`、`_wsetlocale`、`_beginthread`、および  `_beginthreadex` の動作に影響します。  別のメソッドを使用してスレッドを作成した場合、ロケールの設定はこれらのスレッドに影響しません。  
  
 スレッドごとのロケールが無効になると、その後で `setlocale` または `_wsetlocale` を呼び出すたびに、すべてのスレッドのロケールが変更されます。  スレッドごとのロケールが有効な場合、`setlocale` または `_wsetlocale` は現在のスレッドのロケールだけに影響します。  
  
 `_configurethreadlocale` を使用してスレッドごとのロケールを有効にした場合は、その後すぐに `setlocale` または `_wsetlocale` を呼び出して、そのスレッドで優先ロケールを設定することをお勧めします。  
  
 `type` が上記の一覧に示されている値のいずれでもない場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、\-1 を返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_configthreadlocale`|\<locale.h\>|  
  
## 使用例  
  
```  
// crt_configthreadlocale.cpp  
//   
// This program demonstrates the use of _configthreadlocale when  
// using is two independent threads.  
//  
  
#include <locale.h>  
#include <process.h>  
#include <windows.h>  
#include <stdio.h>  
#include <time.h>  
  
#define BUFF_SIZE 100  
  
// Retrieve the date and time in the current  
// locale's format.  
int get_time(unsigned char* str)  
{  
    __time64_t  ltime;  
    struct tm   thetime;  
  
    // Retieve the time  
    _time64(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // Format the current time structure into a string  
    // using %#x is the long date representation,  
    // appropriate to the current locale  
    if (!strftime((char *)str, BUFF_SIZE, "%#x",   
                  (const struct tm*)&thetime))  
    {  
        printf("strftime failed!\n");  
        return -1;  
    }  
    return 0;  
}  
  
// This thread sets its locale to German  
// and prints the time.  
unsigned __stdcall SecondThreadFunc( void* pArguments )  
{  
    unsigned char str[BUFF_SIZE];  
  
    // Set the thread code page  
    _setmbcp(_MB_CP_ANSI)  
  
    // Set the thread locale  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "German"));  
  
    // Retrieve the time string from the helper function  
    if (get_time(str) == 0)  
    {  
        printf("The time in German locale is: '%s'\n", str);  
    }  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
// The main thread spawns a second thread (above) and then  
// sets the locale to English and prints the time.  
int main()  
{   
    HANDLE          hThread;  
    unsigned        threadID;  
    unsigned char   str[BUFF_SIZE];  
  
    // Configure per-thread locale to cause all subsequently created   
    // threads to have their own locale.  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
  
    // Retrieve the time string from the helper function  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "English"));  
  
    // Create the second thread.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,  
                                      NULL, 0, &threadID );  
  
    if (get_time(str) == 0)  
    {  
        // Retrieve the time string from the helper function  
        printf("The time in English locale is: '%s'\n\n", str);  
    }  
  
    // Wait for the created thread to finish.  
    WaitForSingleObject( hThread, INFINITE );  
  
    // Destroy the thread object.  
    CloseHandle( hThread );  
}  
```  
  
  **スレッドのロケールは現在 English\_United States.1252 に設定されています。**  
**English ロケールの時刻: 'Wednesday, May 12, 2004'**  
**スレッドのロケールは現在 German\_Germany.1252 に設定されています。**  
**German ロケールの時刻: 'Mittwoch, 12.  Mai 2004'**    
## 同等の .NET Framework 関数  
 使用できません。ただし、「[CurrentCulture プロパティの使用](http://msdn.microsoft.com/ja-jp/3156042d-6082-4205-90b4-c917ae6a3ba6)」を参照してください。  
  
## 参照  
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_beginthread、\_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチスレッドとロケール](../../parallel/multithreading-and-locales.md)