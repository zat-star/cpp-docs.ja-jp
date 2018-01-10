---
title: _aligned_free_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
dev_langs: C++
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ea0dd62e2b76bef5e55fb152eecfc4c12d01fdf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="alignedfreedbg"></a>_aligned_free_dbg
[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリ ブロックを解放します (デバッグのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
void _aligned_free_dbg(  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `memblock`  
 `_aligned_malloc` または `_aligned_offset_malloc` 関数に返されたメモリ ブロックへのポインター。  
  
## <a name="remarks"></a>コメント  
 `_aligned_free_dbg` 関数は、[_aligned_free](../../c-runtime-library/reference/aligned-free.md) 関数のデバッグ バージョンです。 [_DEBUG](../../c-runtime-library/debug.md) が定義されない場合、`_aligned_free_dbg` への各呼び出しは `_aligned_free` への呼び出しになります。 両方`_aligned_free`と`_aligned_free_dbg`はベース ヒープのメモリ ブロックを解放が`_aligned_free_dbg`はデバッグ機能を提供します。 メモリ不足の状況をシミュレートするために、ヒープのリンク リスト内のブロックを解放された保持することです。  
  
 `_aligned_free_dbg` は、解放操作を実行する前に、指定されたすべてのファイルおよびブロックの位置の有効性チェックを実行します。 アプリケーションは、この情報を提供する必要はありません。 メモリ ブロックが解放されると、デバッグ ヒープ マネージャーはユーザー部分の前後のバッファーの整合性を自動的にチェックし、それらのバッファーが上書きされていた場合はエラー レポートを発行します。 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) フラグの `_CRTDBG_DELAY_FREE_MEM_DF` ビット フィールドが設定されている場合、解放されたブロックは値 0xDD 値を設定され、`_FREE_BLOCK` ブロック型を割り当てられ、ヒープのメモリ ブロックのリンク リストに保持されます。  
  
 メモリの解放でエラーが発生すると、エラーの性質に関するオペレーティング システムからの情報が `errno` に設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_aligned_free_dbg`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)