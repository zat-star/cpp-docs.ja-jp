---
title: "fmin、fminf、fminl |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fmin
- fminf
- fminl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4e8fd804c63caa1a8558e19cb67b4b3f35ecf180
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fmin-fminf-fminl"></a>fmin、fminf、fminl
指定された 2 つの値のうち、小さい方を特定します。  
  
## <a name="syntax"></a>構文  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 比較する最初の値です。  
  
 `y`  
 比較する 2 番目の値です。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は `x` または `y` の小さい方を返します。  
  
|入力|結果|  
|-----------|------------|  
|`x` は NaN|`y`|  
|`y` は NaN|`x`|  
|`x` と `y` は NaN|NaN|  
  
 この関数では、[_matherr](../../c-runtime-library/reference/matherr.md) が呼び出されず、浮動小数点の例外も発生せず、`errno` の値の変更も行われません。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、float 型および long double 型を受け取って返す `fmin` のオーバーロードを呼び出すことができます。 C プログラムでは、`fmin` は常に double を受け取って返します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`fmin`、`fminf`、`fminl`|C: \<math.h><br />C++: \<math.h> または \<cmath>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)  
 [fmax、fmaxf、fmaxl](fmax-fmaxf-fmaxl.md)  