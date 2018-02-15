---
title: feholdexcept2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- feholdexcept
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
- feholdexcept
- fenv/feholdexcept
dev_langs:
- C++
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbfef5db5871740744e370d7e1ac86cf7abac8ac
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="feholdexcept"></a>feholdexcept
指定したオブジェクトに現在の浮動小数点環境を格納し、浮動小数点状態フラグをクリアし、可能であれば、浮動小数点環境を無停止モードにします。  
  
## <a name="syntax"></a>構文  
  
```  
int feholdexcept(  
   fenv_t *penv  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `penv`  
 浮動小数点環境のコピーを含む `fenv_t` オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 関数が正常に停止以外の浮動小数点例外処理を有効にできない場合にのみ 0 を返します。  
  
## <a name="remarks"></a>コメント  
 `feholdexcept` 関数は、`penv` が示す `fenv_t` オブジェクトの現在の浮動小数点環境の状態を格納し、浮動小数点例外に対する実行を中断しないように環境を設定するために使用されます。 これは無停止モードと呼ばれます。  このモードは、[fesetenv](fesetenv1.md) または [feupdateenv](../../c-runtime-library/reference/feupdateenv.md) を使用して環境が復元されるまで継続します。  
  
 この関数は、1 つまたは複数の浮動小数点例外を呼び出し元から隠す必要があるサブルーチンの開始時に使用できます。 例外をレポートするには、[feclearexcept](../../c-runtime-library/reference/feclearexcept1.md) を使用して不要な例外をクリアし、`feupdateenv` を呼び出して無停止モードを終了します。  
  
 この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`feholdexcept`|\<fenv.h>|\<cfenv>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [fesetenv](fesetenv1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)