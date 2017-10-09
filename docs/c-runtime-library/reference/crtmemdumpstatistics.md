---
title: _CrtMemDumpStatistics | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 59379d4916c8414717e886d6fea79e977d31836f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

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
  
 `state` パラメーターは、`_CrtMemState` が呼び出される前に [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) によってデータが格納されたか、[_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) によって返された、`_CrtMemDumpStatistics` 構造体へのポインターである必要があります。 `state` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、何も実行されません。 詳しくは、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
 ヒープ状態関数と `_CrtMemState` 構造体の詳細については、「[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|-------------|---------------------|----------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h>|\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)
