---
title: feclearexcept1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: feclearexcept
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
- feclearexcept
- fenv/feclearexcept
dev_langs: C++
helpviewer_keywords: feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 327c2b70a1c5afd26953f830217d0a9c05e4d4e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="feclearexcept"></a>feclearexcept
引数で指定された浮動小数点例外フラグのクリアを試みます。  
  
## <a name="syntax"></a>構文  
  
```  
int feclearexcept(  
   int excepts  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `excepts`  
 クリアする例外状態フラグ。  
  
## <a name="return-value"></a>戻り値  
 `excepts` がゼロの場合、または指定したすべての例外が正常にクリアされた場合は、0 を返します。 それ以外の場合は、0 以外の値を返します。  
  
## <a name="remarks"></a>コメント  
 `feclearexcept` 関数は、`excepts` で指定された浮動小数点例外状態フラグのクリアを試みます。 この関数は、fenv.h に定義されている次の例外処理マクロをサポートしています。  
  
|例外処理マクロ|説明|  
|---------------------|-----------------|  
|FE_DIVBYZERO|前の浮動小数点演算で特異点エラーまたは極エラーが発生しました。無限大の値が作成されました。|  
|FE_INEXACT|前の浮動小数点演算の格納結果は強制的に丸められました。|  
|FE_INVALID|前の浮動小数点演算でドメイン エラーが発生しました。|  
|FE_OVERFLOW|範囲エラーが発生しました。前の浮動小数点演算結果は大きすぎて表現できませんでした。|  
|FE_UNDERFLOW|前の浮動小数点演算結果は小さすぎて最大有効桁数で表現できませんでした。|  
|FE_ALLEXCEPT|すべてのサポートされる浮動小数点例外のビット演算 OR。|  
  
 `excepts` の引数は 0、またはサポートされる例外処理マクロの 1 つまたは複数のビット演算 OR の場合があります。 他の引数値の結果は未定義です。  
  
## <a name="requirements"></a>必要条件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`feclearexcept`|\<fenv.h>|\<cfenv>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)