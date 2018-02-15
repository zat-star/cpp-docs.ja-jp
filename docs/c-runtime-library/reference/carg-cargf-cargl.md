---
title: "carg、cargf、cargl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- carg
- cargf
- cargl
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
- carg
- cargf
- cargl
- complex/carg
- complex/cargf
- complex/cargl
dev_langs:
- C++
helpviewer_keywords:
- carg function
- cargf function
- cargl function
ms.assetid: 610d6a93-b929-46ab-a966-b77db0b804be
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9341fd3e480fd27f91ccd1ebb1158a7a300f0ead
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="carg-cargf-cargl"></a>carg、cargf、cargl
負の実軸に沿って分岐線法を使用して、複素数の引数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
double carg(   
   _Dcomplex z   
);  
float carg(   
   _Fcomplex z   
);  // C++ only  
long double carg(   
   _Lcomplex z   
);  // C++ only  
float cargf(   
   _Fcomplex z   
);  
long double cargl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `z`  
 複素数。  
  
## <a name="return-value"></a>戻り値  
 `z` の引数 (フェーズとも呼ばれます)。 結果は、間隔には [-π、+ π] です。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、`_Fcomplex` または `_Lcomplex` の値を受け取って `float` または `long double` の値を返す `carg` のオーバーロードを呼び出すことができます。 C プログラムでは、`carg` は常に `_Dcomplex` 値を受け取って `double` 値を返します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|  
|-------------|--------------|------------------|  
|`carg`、               `cargf`、`cargl`|\<complex.h>|\<ccomplex>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm、normf、norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [creal、crealf、creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj、cprojf、cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [conj、conjf、conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag、cimagf、cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [cabs、cabsf、cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)