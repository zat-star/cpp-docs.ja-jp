---
title: "nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf、nexttowardl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
dev_langs:
- C++
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4fe078e00b28f09284f3b91ad93ee1393bea108
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf、nexttowardl
次の表現可能な浮動小数点値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 開始する浮動小数点値。  
  
 `y`  
 移動する浮動小数点値。  
  
## <a name="return-value"></a>戻り値  
 `x` の後の戻り値の型の、次の表現可能な浮動小数点値を `y` の方向に返します。 `x`=`y` の場合、この関数は、戻り値の型に変換された `y` を、例外をトリガーすることなく返します。 `x` が `y` と等しくない場合、結果は非正規化値または 0 となり、FE_UNDERFLOW および FE_INEXACT 浮動小数点例外状態が設定され、正しい結果が返されます。 `x` または `y` が NAN の場合、戻り値は入力 NAN のいずれかとなります。 `x` が有限であり、結果が無限、または型で表現できない場合、正しく署名された infinity または NAN が返され、FE_OVERFLOW と FE_INEXACT 浮動小数点例外の状態が設定され、`errno` が ERANGE に設定されます。  
  
## <a name="remarks"></a>コメント  
 `nextafter` と `nexttoward` の関数ファミリは、`y` のパラメーターの型を除いて同等です。 `x` と `y` が等しい場合、戻り値は戻り値の型に変換された `y` になります。  
  
 C++ ではオーバーロードが可能であるため、\<cmath> を含めると、`float` 型と `long double` 型を返す `nextafter` と `nexttoward` のオーバーロードを呼び出すことができます。 C プログラムでは、`nextafter` および `nexttoward` は常に `double` を返します。  
  
 `_nextafter` と `_nextafterf` の関数は、Microsoft 固有の関数です。 `_nextafterf` 関数は、x64 用にコンパイルするときにのみ使用できます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|  
|-------------|---------------------------|-------------------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<math.h>|\<math.h> または \<cmath>|  
|`_nextafter`|\<float.h>|\<float.h> または \<cfloat>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [isnan、_isnan、_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)