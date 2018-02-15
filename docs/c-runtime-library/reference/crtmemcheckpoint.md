---
title: _CrtMemCheckpoint | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
dev_langs:
- C++
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37333b2b4621b9434a9fe1a924162957d5ea824f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint
デバッグ ヒープの現在の状態を取得し、アプリケーションが指定した `_CrtMemState` 構造体に格納します (デバッグ バージョンだけ)。  
  
## <a name="syntax"></a>構文  
  
```  
void _CrtMemCheckpoint(  
   _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `state`  
 メモリのチェックポイントを格納する `_CrtMemState` 構造体へのポインター。  
  
## <a name="remarks"></a>コメント  
 `_CrtMemCheckpoint` 関数は、指定された時点のデバッグ ヒープの状態のスナップショットを作成します。 [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) などの他のヒープ状態関数は、このスナップショットを使用してメモリ リークおよびその他の問題を検出できます。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtMemState` の呼び出しは前処理で削除されます。  
  
 `_CrtMemState` パラメーターには、Crtdbg.h で定義されている `state` 構造体の割り当て済みインスタンスへのポインターを渡す必要があります。 チェックポイントの作成時に `_CrtMemCheckpoint` でエラーが発生すると、 `_CRT_WARN` デバッグ レポートが生成され、問題が表示されます。  
  
 ヒープ状態関数と `_CrtMemState` 構造体について詳しくは、「 [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
 チェックポイントの作成時に `state` が `NULL`の場合は、「 [Parameter Validation](../../c-runtime-library/parameter-validation.md)」をご覧ください。 実行の継続が許可された場合、この関数は [errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) を `EINVAL` に設定して処理を戻します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtMemCheckpoint`|\<crtdbg.h>、\<errno.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
 **ライブラリ:** UCRT のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md)