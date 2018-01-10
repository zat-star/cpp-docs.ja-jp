---
title: "cimag、cimagf、cimagl | Microsoft Docs"
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
- cimag
- cimagf
- cimagl
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
- cimagf
- cimagl
- complex/cimag
- complex/cimagf
- complex/cimagl
- cimag
dev_langs: C++
helpviewer_keywords:
- cimag function
- cimagf function
- cimagl function
ms.assetid: 0d8836f5-d61d-44cd-8731-6f75cb776def
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b499786cbcb1516fb9746d69c7e124f14d00f011
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cimag-cimagf-cimagl"></a>cimag、cimagf、cimagl
複素数の虚数部を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
double cimag(   
   _Dcomplex z   
);  
float cimag(   
   _Fcomplex z   
);  // C++  
long double cimag(   
  _Lcomplex z   
);  // C++  
float cimagf(   
   _Fcomplex z   
);  
long double cimagl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `z`  
 複素数。  
  
## <a name="return-value"></a>戻り値  
 `z` の虚数部。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、`_Fcomplex` または `_Lcomplex` の値を受け取って `float` または `long double` の値を返す `cimag` のオーバーロードを呼び出すことができます。 C プログラムでは、`cimag` は常に `_Dcomplex` 値を受け取って `double` 値を返します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|  
|-------------|--------------|------------------|  
|`cimag`、               `cimagf`、`cimagl`|\<complex.h>|\<ccomplex>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm、normf、norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [creal、crealf、creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj、cprojf、cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [conj、conjf、conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [carg、cargf、cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)   
 [cabs、cabsf、cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)