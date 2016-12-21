---
title: "calloc | Microsoft Docs"
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
  - "calloc"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "calloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "メモリ割り当て、配列"
  - "calloc 関数"
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# calloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

0 に初期化される要素とメモリの配列を割り当てます。  
  
## 構文  
  
```  
void *calloc(   
   size_t num,  
   size_t size   
);  
```  
  
#### パラメーター  
 `num`  
 要素の数。  
  
 `size`  
 各要素のバイト数。  
  
## 戻り値  
 `calloc` は 割り当てられた領域へのポインターを返します。  戻り値が指す記憶領域が適切にどの型のオブジェクトを格納するために配置されることが保証されます。  `void`以外の型へのポインターを取得するには、戻り値の型キャストを使用してください。  
  
## 解説  
 `calloc` 関数は `num` 要素の配列、長さの `size` バイトのストレージ領域を割り当てます。  各要素は 0 に初期化されます。  
  
 `calloc` を実行したときに、メモリの割り当てに失敗した場合、または要求されたメモリ量が `_HEAP_MAXREQ` を超える場合は、`errno` が `ENOMEM` に設定されます。  これにより、およびそのほかのエラー コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 new ハンドラー モードを設定するには、C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) 関数を使用する`calloc` の 呼び出し `malloc`。  新しいハンドラー モードは、エラーが発生したときに、`malloc` が [\_set\_new\_handler](../Topic/_set_new_handler.md) によって設定された新しいハンドラー ルーチンを呼び出すかどうかを指定します。  既定では、`malloc` は、メモリの割り当てエラーの際に新しいハンドラー ルーチンを呼び出しません。  この既定の動作をオーバーライドすると、`calloc` がメモリの割り当てに失敗したときに、`new` 演算子が同じ理由で失敗したときと同じ方法で、`malloc` によって新しいハンドラー ルーチンを呼び出すことができます。  既定の動作をオーバーライドするには、次の関数を呼び出します。  
  
```  
_set_new_mode(1)  
```  
  
 この呼び出しはプログラムの最初の方で指定するか、NEWMODE.OBJ にリンクします \(「[リンク オプション](../Topic/Link%20Options.md)」を参照してください\)。  
  
 アプリケーションが C ランタイム ライブラリのデバッグ バージョンとリンクすると、`calloc` は [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md)に解決されます。  ヒープのデバッグ中にどのように管理されるかを詳細については、「[CRT のデバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  
  
 `calloc` は グローバル変数を変更せずに関数が保証され、返されたポインターが、エイリアス化されたことを意味するマークされた `__declspec(noalias)` と `__declspec(restrict)`です。  詳細については、「[noalias](../../cpp/noalias.md) と [restrict](../../cpp/restrict.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`calloc`|\<stdlib.h\> および \<malloc.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_calloc.c  
// This program uses calloc to allocate space for  
// 40 long integers. It initializes each element to zero.  
  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   long *buffer;  
  
   buffer = (long *)calloc( 40, sizeof( long ) );  
   if( buffer != NULL )  
      printf( "Allocated 40 long integers\n" );  
   else  
      printf( "Can't allocate memory\n" );  
   free( buffer );  
}  
```  
  
  **40 の長整数代入**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)