---
title: "nearbyint、nearbyintf、nearbyintl |Microsoft ドキュメント"
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
- nearbyint
- nearbyintf
- nerabyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
dev_langs:
- C++
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d981df622450ef0b52a9b0d81427497a3e180bc
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2018
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint、nearbyintf、nearbyintl
指定の浮動小数点値を整数に丸め、浮動小数点形式でその値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
double nearbyint(  
   double x  
);  
  
float nearbyint(  
   float x  
); //C++ only  
  
long double nearbyint(  
   long double x  
); //C++ only  
  
float nearbyintf(  
   float x  
);  
  
long double nearbyintl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 丸める値。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は、fegetround で定義されている現在の丸め形式を使用して直近の整数に丸められた `x` を返します。 それ以外の場合は、関数から次の値のいずれかが返されます。  
  
|懸案事項|Return|  
|-----------|------------|  
|`x` = ±INFINITY|±INFINITY、未変更の状態|  
|`x` = ±0|±0、未変更の状態|  
|`x` = NaN|NaN|  
  
 [_matherr](../../c-runtime-library/reference/matherr.md) を介してエラーは報告されません。特に、この関数ではいずれの FE_INEXACT 例外も報告されません。  
  
## <a name="remarks"></a>コメント  
 この関数と `rint` の主な違いは、この関数では不正確な浮動小数点例外が発生しない点です。  
  
 浮動小数点の最大値は正確な整数であるため、この関数が単独でオーバーフローすることはありません。むしろ、使用する関数のバージョンによっては、出力で戻り値がオーバーフローすることがあります。  
  
## <a name="requirements"></a>必要条件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`nearbyint`、`nearbyintf`、`nearbyintl`|\<math.h>|\<cmath>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)