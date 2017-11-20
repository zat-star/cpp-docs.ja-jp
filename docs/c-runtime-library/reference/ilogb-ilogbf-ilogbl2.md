---
title: "ilogb、ilogbf、ilogbl2 | Microsoft Docs"
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
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f0b2e084e27b951676fddfb20b53d5f74944089e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb、ilogbf、ilogbl
指定した値を、バイアスをかけない 2 進数の指数として表す整数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
int ilogb(  
   double x  
);  
  
int ilogb(  
   float x  
); //C++ only  
  
int ilogb(  
   long double x  
); //C++ only  
  
int ilogbf(  
   float x  
);  
  
int ilogbl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 指定した値。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、`x` の 2 進数による指数を、符号付き `int` の値として返します。  
  
 それ以外の場合、\<math.h > で定義されている次の値のいずれかを返します。  
  
|入力|結果|  
|-----------|------------|  
|±0|FP_ILOGB0|  
|±inf、±nan、不定値|FP_ILOGBNAN|  
  
 エラーは、[_matherr](../../c-runtime-library/reference/matherr.md) で指定されたとおりに報告されます。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、float 型および long double 型を受け取って返す `ilogb` のオーバーロードを呼び出すことができます。 C プログラムでは、`ilogb` は常に double を受け取って返します。  
  
 この関数を呼び出すことは、これに相当する `logb` 関数を呼び出してから、戻り値を `int` へキャストすることに似ています。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|C ヘッダー|C++ ヘッダー|  
|-------------|--------------|------------------|  
|`ilogb`、`ilogbf`、`ilogbl`|\<math.h>|\<cmath>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [logb、logbf、logbl、_logb、_logbf](../../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)