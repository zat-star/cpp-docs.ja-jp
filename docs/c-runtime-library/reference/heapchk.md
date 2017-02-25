---
title: "_heapchk | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_heapchk"
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
  - "_heapchk"
  - "heapchk"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_heapchk 関数"
  - "一貫性チェック (ヒープの)"
  - "デバッグ [CRT], ヒープ関連の問題"
  - "heapchk 関数"
  - "ヒープ, チェック (一貫性を)"
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _heapchk
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープの一貫性チェックを実行します。  
  
## 構文  
  
```  
int _heapchk( void );  
```  
  
## 戻り値  
 `_heapchk` は、Malloc.h に定義されている次の整数のマニフェスト定数のいずれかを返します。  
  
 `_HEAPBADBEGIN`  
 最初のヘッダー情報は、悪かったりが見つかりません。  
  
 `_HEAPBADNODE`  
 不適切なノードがありましたまたはヒープは傷つきます。  
  
 `_HEAPBADPTR`  
 ヒープへのポインターが無効です。  
  
 `_HEAPEMPTY`  
 ヒープを初期化されませんでした。  
  
 `_HEAPOK`  
 ヒープは、一貫しているようです。  
  
 また、エラーが発生した場合、`_heapchk` は `errno` を `ENOSYS` に設定します。  
  
## 解説  
 `_heapchk` 関数ではヒープの最小の一貫性をチェックし、ヒープに関する問題をデバッグします。  オペレーティング システムが `_heapchk` \(たとえば、Windows 98\) をサポートする、関数の戻り値 `_HEAPOK` は `ENOSYS`に `errno` を設定します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_heapchk`|\<malloc.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_heapchk.c  
// This program checks the heap for  
// consistency and prints an appropriate message.  
  
#include <malloc.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  heapstatus;  
   char *buffer;  
  
   // Allocate and deallocate some memory  
   if( (buffer = (char *)malloc( 100 )) != NULL )  
      free( buffer );  
  
   // Check heap status  
   heapstatus = _heapchk();  
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf(" OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf(" OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
}  
```  
  
  **わかりました\-ヒープでも十分です**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [\_heapadd](../../c-runtime-library/heapadd.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_heapset](../../c-runtime-library/heapset.md)   
 [\_heapwalk](../Topic/_heapwalk.md)