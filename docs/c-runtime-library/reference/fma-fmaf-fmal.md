---
title: "fma、fmaf、fmal | Microsoft ドキュメント"
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
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
dev_langs:
- C++
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: 10
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 59238cf511be936b0d882c2f00320ee7422904e0
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="fma-fmaf-fmal"></a>fma、fmaf、fmal
2 つの値を乗算、3 番目の値を追加し、結果を丸めます。中間丸め処理による精度の低下はありません。  
  
## <a name="syntax"></a>構文  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 乗算する 1 番目の値。  
  
 [入力] `y`  
 乗算する 2 番目の値。  
  
 [入力] `z`  
 加算する値。  
  
## <a name="return-value"></a>戻り値  
 `(x * y) + z` を返します。 さらに戻り値は、現在の丸めの形式を使用して丸められます。  
  
 それ以外の場合は、次の値のいずれかを返します。  
  
|問題点|リターン|  
|-----------|------------|  
|`x` = INFINITY、`y` = 0 または<br /><br /> `x` = 0、`y` = INFINITY|NaN|  
|`x` または `y` = exact ± INFINITY、`z` = 逆の符号が付く INFINITY|NaN|  
|`x` または `y` = NaN|NaN|  
|not (`x` = 0, `y`= indefinite) および `z` = NaN<br /><br /> not (`x`=indefinite, `y`=0) および `z` = NaN|NaN|  
|オーバーフロー範囲エラー|±HUGE_VAL、±HUGE_VALF、または ±HUGE_VALL|  
|アンダーフロー範囲エラー|丸めた後の正確な値。|  
  
 エラーは、[_matherr](../../c-runtime-library/reference/matherr.md) で指定されたとおりに報告されます。  
  
## <a name="remarks"></a>コメント  
 C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます`fma`を受け取り、返します**float**と**long double**型です。 C プログラムでは、`fma`常に受け取りを返す、**二重**です。  
  
 この関数は、値を無限の精度とするかのように計算し、最終的な結果を丸めます。  
  
## <a name="requirements"></a>要件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`fma`、`fmaf`、`fmal`|\<math.h>|\<cmath>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder、remainderf、remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo、remquof、remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)
