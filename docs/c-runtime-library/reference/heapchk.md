---
title: _heapchk | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _heapchk
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _heapchk
- heapchk
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- consistency checking of heaps
- heapchk function
- heaps, checking consistency
- _heapchk function
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 790d887009137ccc9115484b2ace57302c94d851
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="heapchk"></a>_heapchk
ヒープに対して整合性チェックを実行します。  
  
## <a name="syntax"></a>構文  
  
```  
int _heapchk( void );  
```  
  
## <a name="return-value"></a>戻り値  
 `_heapchk` は、Malloc.h に定義されている次の整数のマニフェスト定数のいずれかを返します。  
  
 `_HEAPBADBEGIN`  
 初期ヘッダー情報が無効であるか見つかりません。  
  
 `_HEAPBADNODE`  
 不適切なノードが検出されたか、ヒープが破損しています。  
  
 `_HEAPBADPTR`  
 ヒープへのポインターが無効です。  
  
 `_HEAPEMPTY`  
 ヒープが初期化されていません。  
  
 `_HEAPOK`  
 ヒープは一貫性があると思われます。  
  
 また、エラーが発生した場合、`_heapchk` は `errno` を `ENOSYS` に設定します。  
  
## <a name="remarks"></a>コメント  
 `_heapchk` 関数を使用すると、ヒープの最小限の一貫性をチェックしてヒープ関連の問題をデバッグできます。 オペレーティング システムで `_heapchk` がサポートされていない場合 (Windows 98 など)、この関数は `_HEAPOK` を返し、`errno` を `ENOSYS` に設定します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_heapchk`|\<malloc.h>|\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
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
  
```Output  
OK - heap is fine  
```  
  
## <a name="see-also"></a>参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_heapset](../../c-runtime-library/heapset.md)   
 [_heapwalk](../../c-runtime-library/reference/heapwalk.md)