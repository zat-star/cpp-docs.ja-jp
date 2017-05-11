---
title: "_fpclass、_fpclassf | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fpclass
- _fpclassf
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
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
dev_langs:
- C++
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 13
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
ms.openlocfilehash: 9f061841ea6f4050945caeb2cacb9acfdce77c44
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="fpclass-fpclassf"></a>_fpclass、_fpclassf
引数の浮動小数点の分類を示す値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 テストする浮動小数点値。  
  
## <a name="return-value"></a>戻り値  
 `_fpclass` 関数と `_fpclassf` 関数は、引数 `x` の浮動小数点の分類を示す整数値を返します。 分類には、\<float.h> で定義された次のいずれかの値が含まれる場合があります。  
  
|値|説明|  
|-----------|-----------------|  
|`_FPCLASS_SNAN`|シグナル型 NaN|  
|`_FPCLASS_QNAN`|クワイエット型 NaN|  
|`_FPCLASS_NINF`|負の無限大 (INF)|  
|`_FPCLASS_NN`|正規化された負の 0 以外の値|  
|`_FPCLASS_ND`|正規化されない負の値|  
|`_FPCLASS_NZ`|負の 0 (- 0)|  
|`_FPCLASS_PZ`|正のゼロ (+0)|  
|`_FPCLASS_PD`|正規化された正の値|  
|`_FPCLASS_PN`|正規化された正の 0 以外の値|  
|`_FPCLASS_PINF`|正の無限大 (+INF)|  
  
## <a name="remarks"></a>コメント  
 `_fpclass` 関数および `_fpclassf` 関数は、Microsoft 固有の関数です。 [fpclassify](../../c-runtime-library/reference/fpclassify.md) によく似ていますが、引数に関するより詳細な情報を返します。 `_fpclassf` 関数は、x64 プラットフォーム用にコンパイルするときにのみ使用できます。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_fpclass`|\<float.h>|  
  
 互換性と適合性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [isnan、_isnan、_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)
