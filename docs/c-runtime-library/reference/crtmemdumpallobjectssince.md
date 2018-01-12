---
title: _CrtMemDumpAllObjectsSince | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
dev_langs: C++
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d71b5d13b5616717c0b3fc0ac6eae0fc1ca8b551
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince
プログラムの実行開始時以降または指定されたヒープ状態以降のヒープ内のオブジェクトについての情報をダンプします (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void _CrtMemDumpAllObjectsSince(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `state`  
 ダンプの開始点となるヒープ状態へのポインターまたは **NULL**。  
  
## <a name="remarks"></a>コメント  
 `_CrtMemDumpAllObjectsSince` 関数は、ヒープに割り当てられたオブジェクトのデバッグ ヘッダー情報をユーザーが判読できる形式でダンプします。 ダンプ情報は、割り当ての追跡とメモリの問題の検出のためにアプリケーションで使用できます。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtMemDumpAllObjectsSince` の呼び出しは前処理で削除されます。  
  
 `_CrtMemDumpAllObjectsSince` は `state` パラメーターの値を使用して、ダンプ操作の開始点を判断します。 指定したヒープ状態からダンプを開始するには、`state` パラメーターが **_CrtMemState** 構造体へのポインターである必要があります。この構造体は、`_CrtMemDumpAllObjectsSince` が呼び出される前に、[_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) によってデータを設定されていなければなりません。 `state` が **NULL** である場合、関数はプログラムの実行開始時からダンプを始めます。  
  
 アプリケーションが [_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md) を呼び出してダンプ フック関数をインストールした場合、`_CrtMemDumpAllObjectsSince` が `_CLIENT_BLOCK` 型のブロックについての情報をダンプするたびに、アプリケーションによって提供されたダンプ関数も呼び出されます。 既定では、内部 C ランタイム ブロック (`_CRT_BLOCK`) は、メモリ ダンプ操作に含まれません。 これらのブロックを含めるには、[_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 関数を使用して、**_crtDbgFlag** の `_CRTDBG_CHECK_CRT_DF` ビットをオンにします。 また、解放済みまたは無視としてマークされているブロック (**_FREE_BLOCK**、**_IGNORE_BLOCK**) は、メモリ ダンプに含まれません。  
  
 ヒープ状態関数と `_CrtMemState` 構造体の詳細については、「[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
 `_CrtMemDumpAllObjectsSince` の使用例については、「[crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)