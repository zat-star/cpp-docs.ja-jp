---
title: "trunc、truncf、truncl | Microsoft Docs"
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
- trunc
- truncf
- truncl
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
- trunc
- truncf
- truncl
- math/trunc
- math/truncf
- math/truncl
dev_langs: C++
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b2a78deabb758a7d8fe8b0da61899bf7ad11dd8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="trunc-truncf-truncl"></a>trunc、truncf、truncl
指定した浮動小数点以下に最も近い整数を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
double trunc(  
   double x  
);  
  
float trunc(  
   float x  
); //C++ only  
  
long double trunc(  
   long double x  
); //C++ only  
  
float trunc(  
   float x  
); //C++ only  
  
long double truncl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 切り捨てる値。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は `x` をゼロ方向に丸めた整数値を返します。  
  
 それ以外の場合は、次のいずれかを返します。  
  
|問題点|リターン|  
|-----------|------------|  
|`x` = ±INFINITY|x|  
|`x` =  ±0|x|  
|`x` = NaN|NaN|  
  
 エラーは、[_matherr](../../c-runtime-library/reference/matherr.md) で指定されたとおりに報告されます。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、float 型および long double 型を受け取って返す `trunc` のオーバーロードを呼び出すことができます。 C プログラムでは、`trunc` は常に double を受け取って返します。  
  
 浮動小数点の最大値はちょうど整数であるため、この関数は単独ではオーバーフローしません。 ただし、整数型に値を返すことによって、関数のオーバーフローが発生する場合があります。  
  
 浮動小数点から整数に暗黙的に変換することで切り捨てることもできますが、これは対象の型に格納できる値に限ります。  
  
## <a name="requirements"></a>要件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`trunc`、`truncf`、`truncl`|\<math.h>|\<cmath>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [floor、floorf、floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [ceil、ceilf、ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round、roundf、roundl](../../c-runtime-library/reference/round-roundf-roundl.md)