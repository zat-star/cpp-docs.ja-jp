---
title: _CrtMemDumpStatistics | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtMemDumpStatistics
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
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 175497b0bd51a8c651af4662991f6b0b85c273f5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics
指定されたヒープ状態のデバッグ ヘッダー情報をユーザーが判読できる形式でダンプします (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
void _CrtMemDumpStatistics(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `state`  
 ダンプするヒープ状態へのポインター。  
  
## <a name="remarks"></a>コメント  
 `_CrtMemDumpStatistics` 関数は、ヒープの指定された状態のデバッグ ヘッダー情報をユーザーが判読できる形式でダンプします。 ダンプ統計情報は、割り当ての追跡とメモリの問題の検出のためにアプリケーションで使用できます。 メモリ状態には、特定のヒープ状態、または 2 つの状態の相違点を含めることができます。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtMemDumpStatistics` の呼び出しは前処理で削除されます。  
  
 `state` パラメーターは、`_CrtMemState` が呼び出される前に [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) によってデータが格納されたか、[_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) によって返された、`_CrtMemDumpStatistics` 構造体へのポインターである必要があります。 チェックポイントの作成時に `state` が `NULL`の場合は、「 [Parameter Validation](../../c-runtime-library/parameter-validation.md)」をご覧ください。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、何も実行されません。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
 ヒープ状態関数と `_CrtMemState` 構造体について詳しくは、「 [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|  
|-------------|---------------------|----------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h>|\<errno.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)