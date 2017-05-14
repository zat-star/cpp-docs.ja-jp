---
title: "clog、clogf、clogl | Microsoft Docs"
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
- clog
- clogf
- clogl
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
- clog
- clogf
- clogl
- complex/clog
- complex/clogf
- complex/clogl
dev_langs:
- C++
helpviewer_keywords:
- clog function
- clogf function
- clogl function
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 2778a27aa2859d7abb5f247e71397af6aa8b0da6
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="clog-clogf-clogl"></a>clog、clogf、clogl
負の実軸に沿って分岐線法を使用して、複素数の自然対数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
_Dcomplex clog(   
   _Dcomplex z   
);  
_Fcomplex clog(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex clog(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex clogf(   
   _Fcomplex z   
);  
_Lcomplex clogl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `z`  
 対数の底。  
  
## <a name="return-value"></a>戻り値  
 `z` の自然対数。 結果は実数軸に沿っておよび間隔で範囲指定された [-iπ、+ iπ] 虚数部の軸に沿ったです。  
  
 戻り値には次のようなものがあります。  
  
|z パラメーター|戻り値|  
|-----------------|------------------|  
|正|z の底 10 の対数|  
|0|- ∞|  
|負|NaN|  
|NaN|NaN|  
|+ ∞|+ ∞|  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、`clog` および `_Fcomplex` の値を受け取って返す `_Lcomplex` のオーバーロードを呼び出すことができます。 C プログラムでは、 `clog` は常に `_Dcomplex` 値を受け取って返します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|C ヘッダー|C++ ヘッダー|  
|-------------|--------------|------------------|  
|`clog`、               `clogf`、`clogl`|\<complex.h>|\<ccomplex>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp、cexpf、cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [cpow、cpowf、cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [clog10、clog10f、clog10l](../../c-runtime-library/reference/clog10-clog10f-clog10l.md)
