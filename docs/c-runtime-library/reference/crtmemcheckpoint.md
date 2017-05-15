---
title: _CrtMemCheckpoint | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 1904bf5c2632b0913db8e5a9fb838a602615cb45
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

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
  
 `state` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は [errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) を `EINVAL` に設定して処理を戻します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtMemCheckpoint`|\<crtdbg.h>、\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
 **ライブラリ:** UCRT のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md)
