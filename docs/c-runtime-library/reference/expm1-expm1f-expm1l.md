---
title: "expm1、expm1f、expm1l | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- expm1l
- expm1
- expm1f
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
- expm1l
- expm1
- expm1f
dev_langs:
- C++
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e02b2b481e1b773e780623d43ae94d8abe0cba2
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2018
---
# <a name="expm1-expm1f-expm1l"></a>expm1、expm1f、expm1l
e を底とする値のべき乗から 1 を引く計算を行います。  
  
## <a name="syntax"></a>構文  
  
```  
double expm1(   
   double x   
);  
float expm1(  
   float x  
);  // C++ only  
long double expm1(  
   long double x  
);  // C++ only  
float expm1f(  
   float x  
);  
long double expm1l(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 浮動小数点の指数値。  
  
## <a name="return-value"></a>戻り値  
 `expm1` E を表す浮動小数点値を返します<sup>x</sup> - 1、成功した場合。 オーバーフローが発生すると、`expm1` は `HUGE_VAL` を返し、`expm1f` は `HUGE_VALF` を返し、`expm1l` は `HUGE_VALL` を返します。`errno` は `ERANGE` に設定されます。 リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、`expm1` および `float` の値を受け取って返す `long double` のオーバーロードを呼び出すことができます。 C プログラムでは、`expm1` は常に `double` を受け取って返します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`expm1`、`expm1f`、`expm1l`|\<math.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [exp2、exp2f、exp2l](exp2-exp2f-exp2l.md)   
 [pow、powf、powl](../../c-runtime-library/reference/pow-powf-powl.md)