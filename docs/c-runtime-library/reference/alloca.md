---
title: "_alloca | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_alloca"
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
  - "_alloca"
  - "alloca"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_alloca 関数"
  - "alloca 関数"
  - "メモリの割り当て, スタック"
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _alloca
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スタックにメモリを割り当てます。  この関数は、より安全なバージョンが空いたらできません。; [\_malloca](../../c-runtime-library/reference/malloca.md)を参照してください。  
  
## 構文  
  
```  
void *_alloca(   
   size_t size   
);  
```  
  
#### パラメーター  
 \[入力\] `size`  
 スタックから割り当てられるバイト。  
  
## 戻り値  
 `_alloca` ルーチンは、割り当てられたメモリ領域への `void` ポインターを返します。戻り値が指すメモリ領域は、どの型のオブジェクトを格納する場合でも、適切にアラインメントされます。  `size` が 0 の場合、`_alloca` は長さが項目を割り当て、そのアイテムへの有効なポインターを返します。  
  
 領域の割り当てが実行できない場合は、スタック オーバーフロー例外が発生します。  スタック オーバーフロー例外は C\+\+ の例外ではなく、構造化例外です。  C\+\+ の例外処理機能ではなく、[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md) \(SEH\) を使用する必要があります。  
  
## 解説  
 `_alloca` は プログラム スタックから `size` バイトを割り当てます。  割り当てられた領域が自動的にではなく、割り当てがスコープ外に成功した場合にのみ\) 呼び出し関数が終了するときに解放されます。  したがって、[フリー](../../c-runtime-library/reference/free.md)への引数として `_alloca` をポインター値を渡さないでください。  
  
 例外ハンドラー \(EH\) で `_alloca` を明示的に呼び出す場合は制限があります。  x86 クラスのプロセッサで動作する EH ルーチンは、自身のメモリ フレーム内で処理されるため、外側の関数のスタック ポインターが示す現在位置を基にしたメモリ領域ではタスクを実行しません。  一般的な実装には、Windows NT 構造化例外処理 \(SEH: structured exception handling\) や C\+\+ catch 節の式などがあります。  このため、次のようなシナリオで `_alloca` を明示的に呼び出すと、呼び出した EH ルーチンへ戻る時点でプログラム エラーとなります。  
  
-   Windows NT SEH 例外のフィルター式: `__except` \(`_alloca ()`\)  
  
-   Windows NT SEH 最終例外ハンドラー : `__finally`\(`_alloca ()` \)  
  
-   C\+\+ EH catch 句式  
  
 ただし、`_alloca` は、EH ルーチン内から直接呼び出すか、または事前にリストされた EH シナリオのいずれかで呼び出されるアプリケーション供給のコールバックから、直接呼び出すことができます。  
  
> [!IMPORTANT]
>  Windows XP では、try\/catch ブロック内で `_alloca` を呼び出した場合、その catch ブロック内で [\_resetstkoflw](../Topic/_resetstkoflw.md) を呼び出す必要があります。  
  
 上記の制限に加えて、[\/clr \(Common Language Runtime Compilation\)](../../build/reference/clr-common-language-runtime-compilation.md) オプションを使用する場合、`_alloca` が `__except` ブロックで使用することはできません。  詳細については、「[\/clr の制約](../../build/reference/clr-restrictions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_alloca`|\<malloc.h\>|  
  
## 使用例  
  
```  
// crt_alloca.c  
// This program demonstrates the use of  
// _alloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size = 1000;  
    int     errcode = 0;  
    void    *pData = NULL;  
  
    // Note: Do not use try/catch for _alloca,  
    // use __try/__except, since _alloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try {  
        // An unbounded _alloca can easily result in a   
        // stack overflow.  
        // Checking for a size < 1024 bytes is recommended.  
        if (size > 0 && size < 1024)  
        {  
            pData = _alloca( size );  
            printf_s( "Allocated %d bytes of stack at 0x%p",  
                      size, pData);  
        }  
        else  
        {  
            printf_s("Tried to allocate too many bytes.\n");  
        }  
    }  
  
    // If an exception occured with the _alloca function  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_alloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf_s("Could not reset the stack!\n");  
            _exit(1);  
        }  
    };  
}  
```  
  
  **スタックの 0x0012FB50 で 1000 バイト割り当て**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_resetstkoflw](../Topic/_resetstkoflw.md)   
 [\_malloca](../../c-runtime-library/reference/malloca.md)