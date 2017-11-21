---
title: "log1p、log1pf、log1pl2 | Microsoft Docs"
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
- log1p
- log1pf
- log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 14d0228b24a97c2b7113cf9ceccf337c15ef904c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="log1p-log1pf-log1pl"></a>log1p、log1pf、log1pl
1 に指定された値を加えた値の自然対数を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
double log1p(  
   double x  
);  
  
float log1p(  
   float x  
); //C++ only  
  
long double log1p(  
   long double x  
); //C++ only  
  
float log1pf(  
   float x  
);  
  
long double log1pl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 浮動小数点引数。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、(`x`+1) の自然対数 (底 e) を返します。  
  
 それ以外の場合は、次のいずれかの値を返します。  
  
|入力|結果|SEH 例外|errno|  
|-----------|------------|-------------------|-----------|  
|+inf|+inf|||  
|非正規化数|入力と同じ値。|UNDERFLOW||  
|±0|入力と同じ値。|||  
|-1|-inf|DIVBYZERO|ERANGE|  
|< -1|nan|INVALID|EDOM|  
|-inf|nan|INVALID|EDOM|  
|±SNaN|入力と同じ値。|INVALID||  
|±QNaN、不定値|入力と同じ値。|||  
  
 `x` = -1 の場合、`errno` 値は ERANGE に設定されます。 `errno`値に設定されて EDOM `x` <-1 です。  
  
## <a name="remarks"></a>コメント  
 x が 0 に近い場合は、log(`x`+1) を使用するよりも `log1p` 関数の方が正確です。  
  
 C++ ではオーバーロードが可能であるため、float 型および long double 型を受け取って返す `log1p` のオーバーロードを呼び出すことができます。 C プログラムでは、`log1p` は常に double を受け取って返します。  
  
 `x` が自然数の場合、この関数は (`x`-1) の階乗の対数を返します。  
  
## <a name="requirements"></a>要件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`log1p`、`log1pf`、`log1pl`|\<math.h>|\<cmath>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log2、log2f、log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)   
 [log、logf、log10、log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)