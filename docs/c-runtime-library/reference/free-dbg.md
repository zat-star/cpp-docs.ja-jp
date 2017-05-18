---
title: _free_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _free_dbg
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
- _free_dbg
- free_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: da04eb912452b14250704bb2aba2af35fd30d409
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="freedbg"></a>_free_dbg
ヒープ内のメモリ ブロックを解放します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `userData`  
 解放される、割り当てられていたメモリ ブロックへのポインター。  
  
 `blockType`  
 解放される、割り当てられていたメモリ ブロックの型。`_CLIENT_BLOCK`、`_NORMAL_BLOCK`、または `_IGNORE_BLOCK`。  
  
## <a name="remarks"></a>コメント  
 `_free_dbg` 関数は、[free](../../c-runtime-library/reference/free.md) 関数のデバッグ バージョンです。 [_DEBUG](../../c-runtime-library/debug.md) が定義されない場合、`_free_dbg` への各呼び出しは `free` への呼び出しになります。 `free` と `_free_dbg` は、どちらもベース ヒープのメモリ ブロックを解放しますが、`_free_dbg` は 2 つのデバッグ機能を提供します。解放されたブロックをヒープのリンク リストに保持してメモリ不足の状況をシミュレートする機能と、特定の種類の割り当てを解放するためのブロック型パラメーターです。  
  
 `_free_dbg` は、解放操作を実行する前に、指定されたすべてのファイルおよびブロックの位置の有効性チェックを実行します。 アプリケーションは、この情報を提供する必要はありません。 メモリ ブロックが解放されると、デバッグ ヒープ マネージャーはユーザー部分の前後のバッファーの整合性を自動的にチェックし、それらのバッファーが上書きされていた場合はエラー レポートを発行します。 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) フラグの `_CRTDBG_DELAY_FREE_MEM_DF` ビット フィールドが設定されている場合、解放されたブロックは値 0xDD 値を設定され、`_FREE_BLOCK` ブロック型を割り当てられ、ヒープのメモリ ブロックのリンク リストに保持されます。  
  
 メモリの解放でエラーが発生すると、エラーの性質に関するオペレーティング システムからの情報が `errno` に設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_free_dbg`|\<crtdbg.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 `_free_dbg` の使用例については、「[crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)
