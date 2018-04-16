---
title: _get_doserrno | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _get_doserrno
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
- _get_doserrno
- get_doserrno
dev_langs:
- C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ccda58f0de7a22a5fe54e70e512cb4ae88d063e0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="getdoserrno"></a>_get_doserrno
`errno` 値に変換される前に、オペレーティング システムから返されたエラー値を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _get_doserrno(   
   int * pValue   
);   
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pValue`  
 `_doserrno` グローバル マクロの現在の値が格納される整数へのポインター。  
  
## <a name="return-value"></a>戻り値  
 `_get_doserrno` が成功した場合は 0 を返します。失敗した場合はエラー コードを返します。 `pValue` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_doserrno` グローバル マクロは、プロセス実行が開始される前に、CRT の初期化中に 0 に設定されます。 オペレーティング システム エラーを返すシステム レベルの関数呼び出しによって返されたオペレーティング システム エラー値に設定され、実行中に 0 にリセットされることはありません。 関数によって返されたエラー値をチェックするコードを記述する場合は、関数呼び出しの前に [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md) を使用して `_doserrno` を必ずクリアしてください。 別の関数呼び出しによって `_doserrno` が上書きされる可能性があるため、関数呼び出しの直後に `_get_doserrno` を使用して値をチェックします。  
  
 移植可能なエラー コードにするには、`_get_doserrno` ではなく [_get_errno](../../c-runtime-library/reference/get-errno.md) をお勧めします。  
  
 `_doserrno` に使用できる値は \<errno.h> で定義されています。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_get_doserrno`|\<stdlib.h>、\<cstdlib> (C++)|\<errno.h>、\<cerrno> (C++)|  
  
 `_get_doserrno` は Microsoft 拡張機能です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md)   
 [errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)