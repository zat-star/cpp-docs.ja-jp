---
title: "fabs、fabsf、fabsl | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fabsf
- fabs
- fabsl
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
- fabs
- fabsf
- fabsl
- "math\fabs"
- "math\fabsf"
- "math\fabsl"
dev_langs:
- C++
helpviewer_keywords:
- absolute values
- fabsf function
- calculating absolute values
- fabs function
- fabsl function
ms.assetid: 23bca210-f408-4f5e-b46b-0ccaaec31e36
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 707e75f1036421d5392d2e7ecb2273760088e22c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="fabs-fabsf-fabsl"></a>fabs、fabsf、fabsl
浮動小数点引数の絶対値を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
double fabs(   
   double x   
);  
float fabs(  
   float x   
); // C++ only  
long double fabs(  
   long double x  
); // C++ only  
float fabsf(   
   float x   
);  
long double fabsl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 浮動小数点値。  
  
## <a name="return-value"></a>戻り値  
 `fabs` 関数は、引数 `x` の絶対値を返します。 エラーの戻り値はありません。  
  
|入力|SEH 例外|Matherr 例外|  
|-----------|-------------------|-----------------------|  
|± QNAN、IND|none|_DOMAIN|  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、\<cmath> ヘッダーを指定した場合、`fabs` のオーバーロードを呼び出すことができます。 C プログラムでは、`fabs` は常に double を受け取って返します。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須の C ヘッダー|必須の C++ ヘッダー|  
|--------------|-----------------------|---------------------------|  
|`fabs`、`fabsf`、`fabsl`|\<math.h>|\<cmath> または \<math.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 [abs](../../c-runtime-library/reference/abs-labs-llabs-abs64.md) 関数の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [abs、labs、llabs、_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [_cabs](../../c-runtime-library/reference/cabs.md)   