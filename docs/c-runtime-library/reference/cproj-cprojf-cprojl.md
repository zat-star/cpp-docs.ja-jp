---
title: "cproj、cprojf、cprojl | Microsoft Docs"
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
- cproj
- cprojf
- cprojl
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
- cproj
- cprojf
- cprojl
- complex/cproj
- complex/cprojf
- complex/cprojl
dev_langs: C++
helpviewer_keywords:
- cproj function
- cprojf function
- cprojl function
ms.assetid: 32b49623-13bf-4cae-802e-7912d75030fe
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 086abc1446302145eb2749cec10fb07c9d81014a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cproj-cprojf-cprojl"></a>cproj、cprojf、cprojl
リーマン球面上への複素数の射影を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
_Dcomplex cproj(   
   _Dcomplex z   
);  
_Fcomplex cproj(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex cproj(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex cprojf(   
   _Fcomplex z   
);  
_Lcomplex cprojl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `z`  
 複素数。  
  
## <a name="return-value"></a>戻り値  
 リーマン球面への `z` の射影。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、`cproj` および `_Fcomplex` の値を受け取って返す `_Lcomplex` のオーバーロードを呼び出すことができます。 C プログラムでは、 `cproj` は常に `_Dcomplex` 値を受け取って返します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|  
|-------------|--------------|------------------|  
|`cproj`、               `cprojf`、`cprojl`|\<complex.h>|\<ccomplex>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm、normf、norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [creal、crealf、creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [conj、conjf、conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag、cimagf、cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [carg、cargf、cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)   
 [cabs、cabsf、cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)