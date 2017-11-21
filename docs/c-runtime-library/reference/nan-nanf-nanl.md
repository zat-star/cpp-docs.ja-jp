---
title: "nan、nanf、nanl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- nanf
- nan
- nanl
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
- nan
- nanl
- nanf
dev_langs: C++
helpviewer_keywords:
- nan function
- nanf function
- nanl function
ms.assetid: 790e9158-80ab-43e0-8f5a-096198553fd9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7e2b813f2e04871a29715c02a2635f741fb4e50b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="nan-nanf-nanl"></a>nan、nanf、nanl
簡易な NaN 値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
double nan(  
   const char* input   
);  
float nanf(  
   const char* input   
);  
long double nanl(  
   const char* input   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `input`  
 文字列値。  
  
## <a name="return-value"></a>戻り値  
 `nan` 関数は、簡易な NaN 値を返します。  
  
## <a name="remarks"></a>コメント  
 `nan` 関数は、簡易な (非シグナル) NaN に対応する浮動小数点値を返します。 `input` の値は無視されます。 出力で NaN が表現される方法の詳細については、「[printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`nan`、`nanf`、`nanl`|\<math.h>|\<cmath>|  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [_finite、_finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [_fpclass、_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)   
 [isnan、_isnan、_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)