---
title: _set_new_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _set_new_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_new_handler
- set_new_handler
dev_langs:
- C++
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d82d37e13e941f98d51f2f171b9fb6f1b8071058
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="setnewhandler"></a>_set_new_handler
`new` 演算子がメモリの割り当てに失敗した場合は、独自のエラー処理機構に制御を移します。  
  
## <a name="syntax"></a>構文  
  
```  
_PNH _set_new_handler(  
   _PNH pNewHandler   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pNewHandler`  
 アプリケーションによって提供されたメモリ処理関数へのポインター。 引数が 0 の場合、新しいハンドラーは削除されます。  
  
## <a name="return-value"></a>戻り値  
 `_set_new_handler` によって登録された前の例外処理関数へのポインターを返し、前の関数を後で復元できるようにします。 前の関数が設定されていない場合には、戻り値を使用して既定の動作を復元することができます。この値は `NULL` になります。  
  
## <a name="remarks"></a>コメント  
 C++ の `_set_new_handler` 関数は、`new` 演算子がメモリの割り当てに失敗した場合に制御を取得する例外処理関数を指定します。 `new` が失敗した場合、ランタイム システムは `_set_new_handler` への引数として渡された例外処理関数を自動的に呼び出します。 New.h に定義される `_PNH` は、`int` 型を返す関数へのポインターで、`size_t` 型の引数を取ります。 `size_t` を使用して、割り当てられる領域の量を指定します。  
  
 既定のハンドラーはありません。  
  
 `_set_new_handler` は本質的に、ガベージ コレクション スキームです。 ランタイム システムは、関数がゼロ以外の値を返すたびに割り当てを再試行し、関数がゼロを返すと失敗します。  
  
 プログラム内に `_set_new_handler` 関数が出現すると、引数リストに指定されている例外処理関数がランタイム システムに登録されます。  
  
```  
#include <new.h>  
int handle_program_memory_depletion( size_t )  
{  
   // Your code  
}  
int main( void )  
{  
   _set_new_handler( handle_program_memory_depletion );  
   int *pi = new int[BIG_NUMBER];  
}  
```  
  
 最後に `_set_new_handler` 関数に渡された関数のアドレスを保存して、後で再開することができます。  
  
```  
_PNH old_handler = _set_new_handler( my_handler );  
   // Code that requires my_handler  
   _set_new_handler( old_handler )  
   // Code that requires old_handler  
```  
  
 C++ の [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) 関数は、[malloc](../../c-runtime-library/reference/malloc.md) 用の新しいハンドラー モードを設定します。 新しいハンドラー モードは、エラーが発生したときに、`malloc` が `_set_new_handler` によって設定された新しいハンドラー ルーチンを呼び出すかどうかを指定します。 既定では、`malloc` は、メモリの割り当てエラーの際に新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドすると、`malloc` がメモリの割り当てに失敗したときに、`malloc` 演算子が同じ理由で失敗したときと同じ方法で、`new` によって新しいハンドラー ルーチンを呼び出すことができます。 既定の動作を上書きするには、次の関数を呼び出します。  
  
```  
_set_new_mode(1)  
```  
  
 この呼び出しはプログラムの最初の方で指定するか、Newmode.obj にリンクします。  
  
 ユーザー定義する場合`operator new`は提供された場合、エラー発生時に新しいハンドラー関数が自動的に呼び出されません。  
  
 詳細については、「*C++ 言語リファレンス*」の「[new](../../cpp/new-operator-cpp.md)」および「[delete](../../cpp/delete-operator-cpp.md)」を参照してください。  
  
 すべての動的にリンクされる DLL または実行可能ファイルに対して存在する `_set_new_handler` ハンドラーは単一です。自分で `_set_new_handler` を呼び出しても別の DLL または実行可能ファイルによってハンドラーが置き換えられる場合や、別の DLL または実行可能ファイルによって設定されたハンドラーを自分が置き換える場合もそうです。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_set_new_handler`|\<new.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 この例では、割り当てが失敗した場合に、MyNewHandler に制御が移ります。 MyNewHandler に渡される引数は、要求されたバイト数です。 MyNewHandler から返される値は、割り当てを再試行する必要があるかどうかを示すフラグです。ゼロ以外の値は割り当てを再試行すべきことを示し、ゼロの値は割り当てが失敗したことを示します。  
  
```  
// crt_set_new_handler.cpp  
// compile with: /c  
#include <stdio.h>  
#include <new.h>  
#define BIG_NUMBER 0x1fffffff  
  
int coalesced = 0;  
  
int CoalesceHeap()  
{  
   coalesced = 1;  // Flag RecurseAlloc to stop   
   // do some work to free memory  
   return 0;  
}  
// Define a function to be called if new fails to allocate memory.  
int MyNewHandler( size_t size )  
{  
   printf("Allocation failed. Coalescing heap.\n");  
  
   // Call a function to recover some heap space.  
   return CoalesceHeap();  
}  
  
int RecurseAlloc() {  
   int *pi = new int[BIG_NUMBER];  
   if (!coalesced)  
      RecurseAlloc();  
   return 0;  
}  
  
int main()  
{  
   // Set the failure handler for new to be MyNewHandler.  
   _set_new_handler( MyNewHandler );  
   RecurseAlloc();  
}  
```  
  
```Output  
Allocation failed. Coalescing heap.  
  
This application has requested the Runtime to terminate it in an unusual way.  
Please contact the application's support team for more information.  
```  
  
## <a name="see-also"></a>参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)