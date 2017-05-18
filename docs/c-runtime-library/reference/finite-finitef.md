---
title: "_finite、_finitef | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _finite
- _finitef
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
- finite
- _finite
- _finitef
- math/_finite
- math/_finitef
- float/_finite
dev_langs:
- C++
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
caps.latest.revision: 15
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
ms.openlocfilehash: 90eff10a00ecfdfd772acc7caa624ff35dd392d7
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="finite-finitef"></a>_finite、_finitef
浮動小数点値が有限かどうかを決定します。  
  
## <a name="syntax"></a>構文  
  
```  
int _finite(   
   double x   
);  
  
int _finitef(   
   float x   
); /* x64 and ARM/ARM64 only */  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 テストする浮動小数点値。  
  
## <a name="return-value"></a>戻り値  
 両方`_finite`と`_finitef`場合は、0 以外の値を返す引数*x*は有限です。 つまり場合は、-INF < `x` < + INF です。 引数が無限または NAN の場合は、0 を返します。  
  
## <a name="remarks"></a>コメント  
 `_finite` および `_finitef` 関数は、Microsoft 固有の関数です。 `_finitef` 関数は、x86、ARM、または ARM64 プラットフォーム用にコンパイルするときにのみ使用できます。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー (C)|必須ヘッダー (C++)|  
|--------------|---------------------------|-------------------------------|  
|`_finite`|\<float.h> または \<math.h>|\<float.h>、\<math.h>、\<cfloat>、または \<cmath>|  
|`_finitef`|\<math.h>|\<math.h> または \<cmath>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [isnan、_isnan、_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [_fpclass、_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)
