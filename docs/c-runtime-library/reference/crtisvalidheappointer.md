---
title: _CrtIsValidHeapPointer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtIsValidHeapPointer
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
apitype: DLLExport
f1_keywords:
- CrtlsValidHeapPointer
- _CrtIsValidHeapPointer
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsValidHeapPointer function
- CrtIsValidHeapPointer function
ms.assetid: caf597ce-1b05-4764-9f37-0197a982bec5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f888466e0b1625f93c4e1cf66fab0bb85678094
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crtisvalidheappointer"></a>_CrtIsValidHeapPointer
指定したポインターが、必ずしも呼び出し元の CRT ライブラリではなく、任意の C ランタイム ライブラリによって割り当てられたヒープ内にあることを検証します。 これにより、Visual Studio 2010 以前のバージョンの CRT では、指定したポインターがローカル ヒープにあることを検証します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _CrtIsValidHeapPointer(   
   const void *userData   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `userData`  
 割り当てられたメモリ ブロックの先頭へのポインター。  
  
## <a name="return-value"></a>戻り値  
 `_CrtIsValidHeapPointer` は、指定されたポインターがすべての CRT ライブラリ インスタンスによって共有されるヒープ内にある場合は TRUE を返します。 これにより、Visual Studio 2010 以前のバージョンの CRT では、指定したポインターがローカル ヒープにある場合は、TRUE を返します。 それ以外の場合、関数は FALSE を返します。  
  
## <a name="remarks"></a>コメント  
 この関数を使用しないことをお勧めします。 Visual Studio 2010 CRT ライブラリ以降、すべての CRT ライブラリでは 1 つの OS ヒープ (*プロセス ヒープ*) を共有します。 `_CrtIsValidHeapPointer` 関数は、ポインターが CRT ヒープで割り当てられたかどうかを報告しますが、呼び出し元の CRT ライブラリによるものかどうかは報告しません。 たとえば、Visual Studio 2010 バージョンの CRT ライブラリを使用して割り当てられたブロックがあるとします。 Visual Studio 2012 バージョンの CRT ライブラリによってエクスポートされた `_CrtIsValidHeapPointer` 関数がポインターをテストする場合、TRUE を返します。 これは便利なテストではなくなりました。 Visual Studio 2010 以前のバージョンの CRT ライブラリでは、この関数は、特定のメモリ アドレスがローカル ヒープ内にあることを確認するために使用されます。 ローカル ヒープとは、C ランタイム ライブラリの特定のインスタンスによって作成および管理されるヒープを指します。 ダイナミック リンク ライブラリ (DLL) にランタイム ライブラリへの静的なリンクが含まれている場合、DLL はランタイム ヒープの独自のインスタンスを持つため、アプリケーションのローカル ヒープとは別の独自のヒープを持ちます。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtIsValidHeapPointer` の呼び出しは前処理で削除されます。  
  
 この関数は TRUE または FALSE を返すため、[_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 系マクロに渡すことによって、デバッグ用の単純なエラー処理機構を作成できます。 指定されたアドレスがローカル ヒープ内にない場合に、アサーションの失敗を発生させるには、次のように記述します。  
  
```  
_ASSERTE( _CrtIsValidHeapPointer( userData ) );  
```  
  
 `_CrtIsValidHeapPointer` を他のデバッグ関数およびマクロと共に使用する方法の詳細については、「[レポート用マクロ](/visualstudio/debugger/macros-for-reporting)」を参照してください。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtIsValidHeapPointer`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
 次の例では、Visual Studio 2010 以前の C ランタイム ライブラリで使用される場合に、メモリが有効かどうかをテストする方法を示します。 この例は、従来の CRT ライブラリ コードのユーザー向けに提供されます。  
  
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
  
## <a name="output"></a>出力  
  
```  
my_pointer has read and write accessibility.  
my_pointer is within the local heap.  
```  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)