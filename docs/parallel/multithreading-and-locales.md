---
title: "マルチスレッドとロケール | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ロケール [C++], マルチスレッド"
  - "マルチスレッド処理 [C++], ロケール"
  - "スレッドごとのロケール"
  - "スレッド処理 [C++], ロケール"
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# マルチスレッドとロケール
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C ランタイム ライブラリと標準 C\+\+ ライブラリはどちらも、プログラムのロケールの変更をサポートしています。  このトピックでは、マルチスレッド アプリケーションでこの両方のライブラリのロケール機能を使用した場合に発生する問題について説明します。  
  
## 解説  
 C ランタイム ライブラリでは、`_beginthread` および `_beginthreadex` 関数を使用してマルチスレッド アプリケーションを作成できます。  このトピックでは、これらの関数を使用して作成されたマルチスレッド アプリケーションだけについて説明します。  詳細については、「[\_beginthread、\_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md)」を参照してください。  
  
 C ランタイム ライブラリを使用してロケールを変更するには、[setlocale](../preprocessor/setlocale.md) 関数を使用します。  以前のバージョンの [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] では、この関数は常にアプリケーション全体のロケールを変更していました。  現在は、スレッド単位でロケールを設定できます。  これらの処理を行うには、[\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) 関数を使用します。  [setlocale](../preprocessor/setlocale.md) が現在のスレッドのロケールだけを変更するように指定するには、そのスレッドで `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` を呼び出します。  逆に、`_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` を呼び出すと、そのスレッドでグローバル ロケールが使用され、そのスレッド内で [setlocale](../preprocessor/setlocale.md) を呼び出すと、明示的なスレッド個別のロケールを持たないすべてのスレッドのロケールが変更されます。  
  
 C\+\+ ランタイム ライブラリを使用してロケールを変更するには、[locale クラス](../standard-library/locale-class.md) を使用します。  [locale::global](../Topic/locale::global.md) メソッドを呼び出すことによって、明示的に有効化されたスレッド個別のロケールを持たないすべてのスレッドのロケールが変更されます。  単一スレッドまたはアプリケーションの一部のロケールを変更するには、単にそのスレッドまたはコードの該当部分に `locale` オブジェクトのインスタンスを作成します。  
  
> [!NOTE]
>  [locale::global](../Topic/locale::global.md) を呼び出すと、標準 C\+\+ ライブラリと C ランタイム ライブラリの両方のロケールが変更されます。  しかし、[setlocale](../preprocessor/setlocale.md) を呼び出した場合には、C ランタイム ライブラリのロケールだけが変更され、標準 C\+\+ ライブラリは影響を受けません。  
  
 次の例は、[setlocale](../preprocessor/setlocale.md) 関数、[locale クラス](../standard-library/locale-class.md)、および [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) 関数を使用してアプリケーションのロケールを変更する方法を、いくつかのシナリオで示します。  
  
## 使用例  
 この例では、メイン スレッドによって 2 つの子スレッドが生成されます。  最初のスレッドであるスレッド A は、`_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` を呼び出してスレッド個別のロケールを有効化します。  次のスレッドであるスレッド B は、メイン スレッドと同様、スレッド個別のロケールを有効化しません。  次にスレッド A は、C ランタイム ライブラリの [setlocale](../preprocessor/setlocale.md) 関数を使用してロケールを変更します。  
  
 スレッド A ではスレッド個別のロケールが有効化されているため、スレッド A の C ランタイム ライブラリ関数だけで "フランス語" ロケールの使用が開始されます。  スレッド B およびメイン スレッドの C ランタイム ライブラリ関数では、引き続き "C" ロケールが使用されます。  また、[setlocale](../preprocessor/setlocale.md) は標準 C\+\+ ライブラリのロケールには影響しないため、すべての標準 C\+\+ ライブラリ オブジェクトでも引き続き "C" ロケールが使用されます。  
  
```  
// multithread_locale_1.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    setlocale(LC_ALL, "french");  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[Thread A\] Per\-thread locale is enabled.**  
**\[Thread A\] CRT locale is set to "French\_France.1252"**  
**\[Thread A\] locale::global is set to "C"**  
**\[Thread B\] Per\-thread locale is NOT enabled.**  
**\[Thread B\] CRT locale is set to "C"**  
**\[Thread B\] locale::global is set to "C"**  
**\[Thread main\] Per\-thread locale is NOT enabled.**  
**\[Thread main\] CRT locale is set to "C"**  
**\[Thread main\] locale::global is set to "C"**   
## 使用例  
 この例では、メイン スレッドによって 2 つの子スレッドが生成されます。  最初のスレッドであるスレッド A は、`_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` を呼び出してスレッド個別のロケールを有効化します。  次のスレッドであるスレッド B は、メイン スレッドと同様、スレッド個別のロケールを有効化しません。  次にスレッド A は、標準 C\+\+ ライブラリの [locale::global](../Topic/locale::global.md) メソッドを使用してロケールを変更します。  
  
 スレッド A ではスレッド個別のロケールが有効化されているため、スレッド A の C ランタイム ライブラリ関数だけで "フランス語" ロケールの使用が開始されます。  スレッド B およびメイン スレッドの C ランタイム ライブラリ関数では、引き続き "C" ロケールが使用されます。  しかし、[locale::global](../Topic/locale::global.md) メソッドによってロケールが "グローバルに" 変更されているため、すべてのスレッドのすべての標準 C\+\+ ライブラリ オブジェクトで "フランス語" ロケールの使用が開始されます。  
  
```  
// multithread_locale_2.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    locale::global(locale("french"));  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[Thread A\] Per\-thread locale is enabled.**  
**\[Thread A\] CRT locale is set to "French\_France.1252"**  
**\[Thread A\] locale::global is set to "French\_France.1252"**  
**\[Thread B\] Per\-thread locale is NOT enabled.**  
**\[Thread B\] CRT locale is set to "C"**  
**\[Thread B\] locale::global is set to "French\_France.1252"**  
**\[Thread main\] Per\-thread locale is NOT enabled.**  
**\[Thread main\] CRT locale is set to "C"**  
**\[Thread main\] locale::global is set to "French\_France.1252"**   
## 使用例  
 この例では、メイン スレッドによって 2 つの子スレッドが生成されます。  最初のスレッドであるスレッド A は、`_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` を呼び出してスレッド個別のロケールを有効化します。  次のスレッドであるスレッド B は、メイン スレッドと同様、スレッド個別のロケールを有効化しません。  次にスレッド B は、C ランタイム ライブラリの [setlocale](../preprocessor/setlocale.md) 関数を使用してロケールを変更します。  
  
 スレッド B ではスレッド個別のロケールが有効化されていないため、スレッド B およびメイン スレッドの C ランタイム ライブラリ関数で "フランス語" ロケールの使用が開始されます。  スレッド A ではスレッド個別のロケールが有効化されているため、スレッド A の C ランタイム ライブラリ関数は引き続き "C" ロケールを使用します。  また、[setlocale](../preprocessor/setlocale.md) は標準 C\+\+ ライブラリのロケールには影響しないため、すべての標準 C\+\+ ライブラリ オブジェクトでも引き続き "C" ロケールが使用されます。  
  
```  
// multithread_locale_3.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
BOOL configThreadLocaleCalled = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    configThreadLocaleCalled = TRUE;  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!configThreadLocaleCalled)  
        Sleep(100);  
    setlocale(LC_ALL, "french");  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[Thread B\] Per\-thread locale is NOT enabled.**  
**\[Thread B\] CRT locale is set to "French\_France.1252"**  
**\[Thread B\] locale::global is set to "C"**  
**\[Thread A\] Per\-thread locale is enabled.**  
**\[Thread A\] CRT locale is set to "C"**  
**\[Thread A\] locale::global is set to "C"**  
**\[Thread main\] Per\-thread locale is NOT enabled.**  
**\[Thread main\] CRT locale is set to "French\_France.1252"**  
**\[Thread main\] locale::global is set to "C"**   
## 使用例  
 この例では、メイン スレッドによって 2 つの子スレッドが生成されます。  最初のスレッドであるスレッド A は、`_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` を呼び出してスレッド個別のロケールを有効化します。  次のスレッドであるスレッド B は、メイン スレッドと同様、スレッド個別のロケールを有効化しません。  次にスレッド B は、標準 C\+\+ ライブラリの [locale::global](../Topic/locale::global.md) メソッドを使用してロケールを変更します。  
  
 スレッド B ではスレッド個別のロケールが有効化されていないため、スレッド B およびメイン スレッドの C ランタイム ライブラリ関数で "フランス語" ロケールの使用が開始されます。  スレッド A ではスレッド個別のロケールが有効化されているため、スレッド A の C ランタイム ライブラリ関数は引き続き "C" ロケールを使用します。  しかし、[locale::global](../Topic/locale::global.md) メソッドによってロケールが "グローバルに" 変更されているため、すべてのスレッドのすべての標準 C\+\+ ライブラリ オブジェクトで "フランス語" ロケールの使用が開始されます。  
  
```  
// multithread_locale_4.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
BOOL configThreadLocaleCalled = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    configThreadLocaleCalled = TRUE;  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!configThreadLocaleCalled)  
        Sleep(100);  
    locale::global(locale("french"));  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[Thread B\] Per\-thread locale is NOT enabled.**  
**\[Thread B\] CRT locale is set to "French\_France.1252"**  
**\[Thread B\] locale::global is set to "French\_France.1252"**  
**\[Thread A\] Per\-thread locale is enabled.**  
**\[Thread A\] CRT locale is set to "C"**  
**\[Thread A\] locale::global is set to "French\_France.1252"**  
**\[Thread main\] Per\-thread locale is NOT enabled.**  
**\[Thread main\] CRT locale is set to "French\_France.1252"**  
**\[Thread main\] locale::global is set to "French\_France.1252"**   
## 参照  
 [旧形式のコードのためのマルチスレッド サポート \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [\_beginthread、\_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md)   
 [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../preprocessor/setlocale.md)   
 [国際化](../c-runtime-library/internationalization.md)   
 [ロケール](../c-runtime-library/locale.md)   
 [\<clocale\>](../standard-library/clocale.md)   
 [\<locale\>](../standard-library/locale.md)   
 [locale クラス](../standard-library/locale-class.md)