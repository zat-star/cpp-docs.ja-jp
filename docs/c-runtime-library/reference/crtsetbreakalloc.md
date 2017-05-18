---
title: _CrtSetBreakAlloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetBreakAlloc
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
- CrtSetBreakAlloc
- _CrtSetBreakAlloc
dev_langs:
- C++
helpviewer_keywords:
- CrtSetBreakAlloc function
- _CrtSetBreakAlloc function
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: b33d7b6125d9b399f5d36635a3dd80de3bbea4c5
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="crtsetbreakalloc"></a>_CrtSetBreakAlloc
指定されたオブジェクト割り当て順序番号にブレークポイントを設定します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
  
      long _CrtSetBreakAlloc(   
   long lBreakAlloc   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *lBreakAlloc*  
 ブレークポイントを設定する割り当て順序番号。  
  
## <a name="return-value"></a>戻り値  
 ブレークポイントが設定されていた、以前のオブジェクト割り当て順序番号を返します。  
  
## <a name="remarks"></a>コメント  
 `_CrtSetBreakAlloc` を使用すると、アプリケーションはメモリ割り当ての特定の位置でブレークし、要求元をさかのぼって調べることにより、メモリ リークの検出を実行できます。 関数は、メモリ ブロックがヒープ上に割り当てられたときに決められた、シーケンシャルなオブジェクト割り当て順序番号を使用します。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtSetBreakAlloc` の呼び出しは前処理で削除されます。  
  
 オブジェクト割り当て順序番号は、Crtdbg.h で定義されている **_CrtMemBlockHeader** 構造体の *lRequest* フィールドに格納されます。 いずれかのデバッグ ダンプ関数を使用してメモリ ブロックの情報を出力すると、この番号が {36} のように中かっこで囲まれて表示されます。  
  
 `_CrtSetBreakAlloc` を他のメモリ管理関数と共に使用する方法の詳細については、「[ヒープ割り当て要求の追跡](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtSetBreakAlloc`|\<crtdbg.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
  
```  
// crt_setbrkal.c  
// compile with: -D_DEBUG /MTd -Od -Zi -W3 /c /link -verbose:lib -debug  
  
/*  
 * In this program, a call is made to the _CrtSetBreakAlloc routine  
 * to verify that the debugger halts program execution when it reaches  
 * a specified allocation number.  
 */  
  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        long allocReqNum;  
        char *my_pointer;  
  
        /*   
         * Allocate "my_pointer" for the first  
         * time and ensure that it gets allocated correctly  
         */  
        my_pointer = malloc(10);  
        _CrtIsMemoryBlock(my_pointer, 10, &allocReqNum, NULL, NULL);  
  
        /*   
         * Set a breakpoint on the allocation request  
         * number for "my_pointer"  
         */  
        _CrtSetBreakAlloc(allocReqNum+2);  
  
        /*   
         * Alternate freeing and reallocating "my_pointer"  
         * to verify that the debugger halts program execution  
         * when it reaches the allocation request  
         */  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)
