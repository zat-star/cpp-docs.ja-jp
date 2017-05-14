---
title: "fdim、fdimf、fdiml | Microsoft ドキュメント"
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
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
dev_langs:
- C++
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
caps.latest.revision: 11
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: f13291a00b97c319ebe69bce6939a95e6c022fd8
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="fdim-fdimf-fdiml"></a>fdim、fdimf、fdiml
1 番目と 2 番目の値の間の正の値の差を求めます。  
  
## <a name="syntax"></a>構文  
  
```  
double fdim(  
   double x,   
   double y  
);  
  
float fdim(  
   float x,   
   float y  
); //C++ only  
  
long double fdim(  
   long double x,   
   long double y  
); //C++ only  
  
float fdimf(  
   float x,   
   float y  
);  
  
long double fdiml(  
   long double x,   
   long double y  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 最初の値。  
  
 [入力] `y`  
 2 番目の値。  
  
## <a name="return-value"></a>戻り値  
 `x` と `y` の間の正の値の差を返します。  
  
|戻り値|シナリオ|  
|------------------|--------------|  
|x-y|x > y の場合|  
|0|x <= y の場合|  
  
 それ以外の場合は、次のエラーのいずれかを返すことがあります。  
  
|問題点|リターン|  
|-----------|------------|  
|オーバーフロー範囲エラー|+HUGE_VAL、+HUGE_VALF、または +HUGE_VALL|  
|アンダーフロー範囲エラー|丸めた後の正確な値|  
|`x` または `y` は NaN|NaN|  
  
 エラーは、[_matherr](../../c-runtime-library/reference/matherr.md) で指定されたとおりに報告されます。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、float 型および long double 型を受け取って返す `fdim` のオーバーロードを呼び出すことができます。 C プログラムでは、`fdim` は常に double を受け取って返します。  
  
 この関数は NaN 処理を除くと同じで、`fmax(x - y, 0)`です。  
  
## <a name="requirements"></a>要件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`fdim`、`fdimf`、`fdiml`|\<math.h>|\<cmath>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmax、fmaxf、fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)   
 [abs、labs、llabs、_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)
