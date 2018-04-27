---
title: nan、nanf、nanl | Microsoft Docs
ms.custom: ''
ms.date: 94/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- nan function
- nanf function
- nanl function
ms.assetid: 790e9158-80ab-43e0-8f5a-096198553fd9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e2fa378cdded71f0f99ad0fbe152d1282c9e6fe4
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="nan-nanf-nanl"></a>nan、nanf、nanl

簡易な NaN 値を返します。

## <a name="syntax"></a>構文

```C
double nan( const char* input );
float nanf( const char* input );
long double nanl( const char* input );
```

### <a name="parameters"></a>パラメーター

*input*<br/>
文字列値。

## <a name="return-value"></a>戻り値

**Nan**関数は、簡易な NaN 値を返します。

## <a name="remarks"></a>コメント

**Nan**静かな (非シグナル) NaN に対応する浮動小数点値を返します。 *入力*値は無視されます。 出力で NaN が表現される方法の詳細については、「[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)」をご覧ください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**nan**、 **nanf**、 **nanl**|\<math.h>|\<cmath> または \<math.h>|

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_finite、_finitef](finite-finitef.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
