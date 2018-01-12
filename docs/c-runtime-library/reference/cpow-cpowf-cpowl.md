---
title: "cpow、cpowf、cpowl | Microsoft Docs"
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
- cpow
- cpowf
- cpowl
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
- cpow
- cpowf
- cpowl
- complex/cpow
- complex/cpowf
- complex/copwl
dev_langs: C++
helpviewer_keywords:
- cpow function
- cpowf function
- complex/cpowl function
ms.assetid: 83fe2187-22b7-4295-ab16-4d77abdbb80b
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b12c59074585acaf2ec2ce5931ef8001deb1345e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cpow-cpowf-cpowl"></a>cpow、cpowf、cpowl
数値を指定された値で累乗して返します。底と指数は複素数です。 この関数には、負の実数軸に沿った指数の分岐切断線があります。  
  
## <a name="syntax"></a>構文  
  
```  
_Dcomplex cpow(   
   _Dcomplex x, _Dcomplex y   
);  
_Fcomplex cpow(   
   _Fcomplex x, _Fcomplex y   
);  // C++ only  
_Lcomplex cpow(   
   _Lcomplex x, _Lcomplex y   
);  // C++ only  
_Fcomplex cpowf(   
   _Fcomplex x, _Fcomplex y   
);  
_Lcomplex cpowl(   
   _Lcomplex x, _Lcomplex y   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 底。  
  
 `y`  
 指数。  
  
## <a name="return-value"></a>戻り値  
 `x` の値を `y` で累乗した値。負の実数軸に沿って `x` の分岐切断線があります。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、`cpow` および `_Fcomplex` の値を受け取って返す `_Lcomplex` のオーバーロードを呼び出すことができます。 C プログラムでは、 `cpow` は常に `_Dcomplex` 値を受け取って返します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|  
|-------------|--------------|------------------|  
|`cpow`、               `cpowf`、`cpowl`|\<complex.h>|\<ccomplex>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp、cexpf、cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [clog10、clog10f、clog10l](../../c-runtime-library/reference/clog10-clog10f-clog10l.md)   
 [clog、clogf、clogl](../../c-runtime-library/reference/clog-clogf-clogl.md)