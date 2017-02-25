---
title: "terminate (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "terminate"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "terminate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "例外処理, 終了"
  - "terminate 関数"
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# terminate (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザーが `set_terminate`を使用して指定する関数または呼び出し `abort`。  
  
## 構文  
  
```  
void terminate( void );  
```  
  
## 解説  
 `terminate` 関数は C\+\+ 例外処理との使用され、次の場合に呼び出され、M:  
  
-   対応する catch ハンドラーはスローされた C\+\+ 例外の場合に発生することはできません。  
  
-   例外はスタック アンワインド中にデストラクター関数によってスローされます。  
  
-   スタックが例外をスローした後破損しています。  
  
 `terminate` の 呼び出し `abort` 既定で。  独自の終了関数を記述し、引数として関数の名前 `set_terminate` を呼び出して、この既定を変更できます。  `terminate` は 最後の関数を `set_terminate`に引数としてから呼び出します。  詳細については、「[未処理の C\+\+ 例外](../../cpp/unhandled-cpp-exceptions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`terminate`|\<eh.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_terminate.cpp  
// compile with: /EHsc  
#include <eh.h>  
#include <process.h>  
#include <iostream>  
using namespace std;  
  
void term_func();  
  
int main()  
{  
    int i = 10, j = 0, result;  
    set_terminate( term_func );  
    try  
    {  
        if( j == 0 )  
            throw "Divide by zero!";  
        else  
            result = i/j;  
    }  
    catch( int )  
    {  
        cout << "Caught some integer exception.\n";  
    }  
    cout << "This should never print.\n";  
}  
  
void term_func()  
{  
    cout << "term_func() was called by terminate().\n";  
  
    // ... cleanup tasks performed here  
  
    // If this function does not exit, abort is called.  
  
    exit(-1);  
}  
```  
  
  **term\_func\(\) は terminate\(\)で呼び出されました。**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [unexpected](../Topic/unexpected%20\(CRT\).md)