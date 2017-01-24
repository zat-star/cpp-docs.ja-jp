---
title: "_malloca | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_malloca"
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
apitype: "DLLExport"
f1_keywords: 
  - "malloca"
  - "_malloca"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_malloca 関数"
  - "malloca 関数"
  - "メモリの割り当て, スタック"
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _malloca
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スタックにメモリを割り当てます。  この関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[\_alloca](../../c-runtime-library/reference/alloca.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
void *_malloca(   
   size_t size   
);  
```  
  
#### パラメーター  
 `size`  
 スタックから割り当てられるバイト。  
  
## 戻り値  
 `_malloca` ルーチンは、割り当てられたメモリ領域への `void` ポインターを返します。戻り値が指すメモリ領域は、どの型のオブジェクトを格納する場合でも、適切にアラインメントされます。  `size` が 0 の場合、`_malloca` 関数は長さが 0 のアイテムを割り当て、そのアイテムへの有効なポインターを返します。  
  
 領域の割り当てが実行できない場合は、スタック オーバーフロー例外が発生します。  スタック オーバーフロー例外は C\+\+ の例外ではなく、構造化例外です。  C\+\+ の例外処理機能ではなく、[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md) \(SEH\) を使用する必要があります。  
  
## 解説  
 `_malloca` は、要求が `_ALLOCA_S_THRESHOLD` に指定されているバイト数を超える場合に、プログラム スタックまたはヒープから `size` バイトを割り当てます。  `_malloca` と `_alloca` の違いは、`_alloca` がサイズに関係なく常にスタックを割り当てることです。  `_alloca` で割り当てたメモリは `free` を呼び出して解放することが必要なく、また許可もされていないのに対し、`_malloca` では [\_freea](../../c-runtime-library/reference/freea.md) を使用してメモリを開放する必要があります。  デバッグ モードでは、`_malloca` は常にヒープからメモリを割り当てます。  
  
 例外ハンドラー \(EH\) で `_malloca` を明示的に呼び出す場合は制限があります。  x86 クラスのプロセッサで動作する EH ルーチンは、自身のメモリ フレーム内で処理されるため、外側の関数のスタック ポインターが示す現在位置を基にしたメモリ領域ではタスクを実行しません。  一般的な実装には、Windows NT 構造化例外処理 \(SEH: structured exception handling\) や C\+\+ catch 節の式などがあります。  このため、次のようなシナリオで `_malloca` を明示的に呼び出すと、呼び出した EH ルーチンへ戻る時点でプログラム エラーとなります。  
  
-   Windows NT SEH 例外フィルター式 : `__except` \(`_malloca ()` \)  
  
-   Windows NT SEH 最終例外ハンドラー : `__finally`\(`_malloca ()` \)  
  
-   C\+\+ EH catch 句式  
  
 ただし、`_malloca` は、EH ルーチン内から直接呼び出すか、または事前にリストされた EH シナリオのいずれかで呼び出されるアプリケーション供給のコールバックから、直接呼び出すことができます。  
  
> [!IMPORTANT]
>  Windows XP では、try\/catch ブロック内で `_malloca` を呼び出した場合、その catch ブロック内で [\_resetstkoflw](../Topic/_resetstkoflw.md) を呼び出す必要があります。  
  
 上記の制限に加え、[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md) オプションを使用する場合は `__except` ブロックで `_malloca` を使用できません。  詳細については、「[\/clr の制約](../../build/reference/clr-restrictions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_malloca`|\<malloc.h\>|  
  
## 使用例  
  
```  
// crt_malloca_simple.c  
#include <stdio.h>  
#include <malloc.h>  
  
void Fn()  
{  
   char * buf = (char *)_malloca( 100 );  
   // do something with buf  
   _freea( buf );  
}  
  
int main()  
{  
   Fn();  
}  
```  
  
## 使用例  
  
```  
// crt_malloca_exception.c  
// This program demonstrates the use of  
// _malloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size;  
    int     numberRead = 0;  
    int     errcode = 0;  
    void    *p = NULL;  
    void    *pMarker = NULL;  
  
    while (numberRead == 0)  
    {  
        printf_s("Enter the number of bytes to allocate "  
                 "using _malloca: ");  
        numberRead = scanf_s("%d", &size);  
    }  
  
    // Do not use try/catch for _malloca,  
    // use __try/__except, since _malloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try  
    {  
        if (size > 0)  
        {  
            p =  _malloca( size );  
        }  
        else  
        {  
            printf_s("Size must be a positive number.");  
        }  
        _freea( p );  
    }  
  
    // Catch any exceptions that may occur.  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_malloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf("Could not reset the stack!");  
            _exit(1);  
        }  
    };  
}  
```  
  
## 入力  
  
```  
1000  
```  
  
## 出力例  
  
```  
Enter the number of bytes to allocate using _malloca: 1000  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_resetstkoflw](../Topic/_resetstkoflw.md)