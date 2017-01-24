---
title: "_CrtIsValidHeapPointer | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtIsValidHeapPointer"
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
  - "CrtlsValidHeapPointer"
  - "_CrtIsValidHeapPointer"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtIsValidHeapPointer 関数"
  - "CrtIsValidHeapPointer 関数"
ms.assetid: caf597ce-1b05-4764-9f37-0197a982bec5
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtIsValidHeapPointer
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定したポインターが、必ずしも呼び出し元の CRT ライブラリではなく、任意の C ランタイム ライブラリによって割り当てられたヒープ内にあることを検証します。  これにより、Visual Studio 2010 以前のバージョンの CRT では、指定したポインターがローカル ヒープにあることを検証します \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
  
        int _CrtIsValidHeapPointer(   
   const void *userData   
);  
```  
  
#### パラメーター  
 `userData`  
 割り当てられたメモリ ブロックの先頭へのポインター。  
  
## 戻り値  
 `_CrtIsValidHeapPointer` は、指定されたポインターがすべての CRT ライブラリ インスタンスによって共有されるヒープ内にある場合は TRUE を返します。  これにより、Visual Studio 2010 以前のバージョンの CRT では、指定したポインターがローカル ヒープにある場合は、TRUE を返します。  それ以外の場合、関数は FALSE を返します。  
  
## 解説  
 この関数を使用しないことをお勧めします。  Visual Studio 2010 CRT ライブラリ以降、すべての CRT ライブラリでは 1 つの OS ヒープ \(*プロセス ヒープ*\) を共有します。  `_CrtIsValidHeapPointer` 関数は、ポインターが CRT ヒープで割り当てられたかどうかを報告しますが、呼び出し元の CRT ライブラリによるものかどうかは報告しません。  たとえば、Visual Studio 2010 バージョンの CRT ライブラリを使用して割り当てられたブロックがあるとします。  Visual Studio 2012 バージョンの CRT ライブラリによってエクスポートされた `_CrtIsValidHeapPointer` 関数がポインターをテストする場合、TRUE を返します。  これは便利なテストではなくなりました。  Visual Studio 2010 以前のバージョンの CRT ライブラリでは、この関数は、特定のメモリ アドレスがローカル ヒープ内にあることを確認するために使用されます。  ローカル ヒープとは、C ランタイム ライブラリの特定のインスタンスによって作成および管理されるヒープを指します。  ダイナミック リンク ライブラリ \(DLL\) にランタイム ライブラリへの静的なリンクが含まれている場合、DLL はランタイム ヒープの独自のインスタンスを持つため、アプリケーションのローカル ヒープとは別の独自のヒープを持ちます。  [\_DEBUG](../Topic/_DEBUG.md) が未定義の場合、`_CrtIsValidHeapPointer` の呼び出しはプリプロセスで削除されます。  
  
 この関数は TRUE または FALSE を返すため、[\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) 系マクロに渡すことによって、デバッグ用の単純なエラー処理機構を作成できます。  指定されたアドレスがローカル ヒープ内にない場合に、アサーションの失敗を発生させるには、次のように記述します。  
  
```  
_ASSERTE( _CrtIsValidHeapPointer( userData ) );  
```  
  
 `_CrtIsValidHeapPointer` を他のデバッグ関数およびマクロと共に使用する方法の詳細については、「[レポート用マクロの使用](../Topic/Macros%20for%20Reporting.md)」を参照してください。  デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法の詳細については、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_CrtIsValidHeapPointer`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## 使用例  
 次の例では、Visual Studio 2010 以前の C ランタイム ライブラリで使用される場合に、メモリが有効かどうかをテストする方法を示します。  この例は、従来の CRT ライブラリ コードのユーザー向けに提供されます。  
  
```  
// crt_isvalid.c  
/*  
 * This program allocates a block of memory using _malloc_dbg  
 * and then tests the validity of this memory by calling   
 * _CrtIsMemoryBlock,_CrtIsValidPointer, and _CrtIsValidHeapPointer.  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
#define  TRUE   1  
#define  FALSE  0  
  
int main( void )  
{  
        char *my_pointer;  
  
        /*   
         * Call _malloc_dbg to include the filename and line number  
         * of our allocation request in the header information  
         */  
        my_pointer = (char *)_malloc_dbg( sizeof(char) * 10,   
        _NORMAL_BLOCK, __FILE__, __LINE__ );  
  
        // Ensure that the memory got allocated correctly  
        _CrtIsMemoryBlock((const void *)my_pointer, sizeof(char) * 10,   
        NULL, NULL, NULL );  
  
         // Test for read/write accessibility  
        if (_CrtIsValidPointer((const void *)my_pointer,   
        sizeof(char) * 10, TRUE))  
                printf("my_pointer has read and write accessibility.\n");  
        else  
                printf("my_pointer only has read access.\n");  
  
        // Make sure my_pointer is within the local heap  
        if (_CrtIsValidHeapPointer((const void *)my_pointer))  
                printf("my_pointer is within the local heap.\n");  
        else  
                printf("my_pointer is not located within the local"  
                       " heap.\n");  
  
        free(my_pointer);  
}  
```  
  
## 出力  
  
```  
my_pointer has read and write accessibility.  
my_pointer is within the local heap.  
```  
  
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)