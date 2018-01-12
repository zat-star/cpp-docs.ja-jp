---
title: fegetexceptflag2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: fegetexceptflag
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
- fegetexceptflag
- fenv/fegetexceptflag
dev_langs: C++
helpviewer_keywords: fegetexceptflag function
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c55016a8d22b577197818f89a0ee71b4ca14367d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fegetexceptflag"></a>fegetexceptflag
指定した浮動小数点例外フラグの現在の状態を格納します。  
  
## <a name="syntax"></a>構文  
  
```  
int fegetexceptflag(   
   fexcept_t* pstatus,   
   int excepts   
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstatus`  
 `excepts` で指定された例外フラグの現在の値を含む `fexcept_t` オブジェクトへのポインター。  
  
 `excepts`  
 `pstatus` に格納する浮動小数点例外フラグ。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は 0 を返します。 それ以外の場合は、0 以外の値を返します。  
  
## <a name="remarks"></a>コメント  
 `fegetexceptflag` 関数は、`pstatus` が示す `fexcept_t` オブジェクトの `excepts` で指定された浮動小数点例外状態フラグの現在の状態を格納します。  `pstatus` は有効な `fexcept_t` オブジェクトを示す必要があります。そうしないと、その後の動作は未定義になります。 `fegetexceptflag` 関数は、\<fenv.h> に定義されている次の例外処理マクロをサポートしています。  
  
|例外処理マクロ|説明|  
|---------------------|-----------------|  
|FE_DIVBYZERO|前の浮動小数点演算で特異点エラーまたは極エラーが発生しました。無限大の値が作成されました。|  
|FE_INEXACT|前の浮動小数点演算の格納結果は強制的に丸められました。|  
|FE_INVALID|前の浮動小数点演算でドメイン エラーが発生しました。|  
|FE_OVERFLOW|範囲エラーが発生しました。前の浮動小数点演算結果は大きすぎて表現できませんでした。|  
|FE_UNDERFLOW|前の浮動小数点演算結果は小さすぎて最大有効桁数で表現できませんでした。|  
|FE_ALLEXCEPT|すべてのサポートされる浮動小数点例外のビット演算 OR。|  
  
 `excepts` 引数は、0、サポートされる浮動小数点例外処理マクロ、または複数のマクロのビット演算 OR の場合があります。 他の引数値の結果は未定義です。  
  
 この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`fegetexceptflag`|\<fenv.h>|\<cfenv>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)