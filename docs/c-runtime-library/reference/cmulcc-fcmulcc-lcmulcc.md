---
title: _Cmulcc、_FCmulcc、_LCmulcc |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- _Cmulcc
- _FCmulcc
- _LCmulcc
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
- _Cmulcc
- _FCmulcc
- _LCmulcc
- complex/_Cmulcc
- complex/_FCmulcc
- complex/_LCmulcc
dev_langs:
- C++
helpviewer_keywords:
- _Cmulcc function
- _FCmulcc function
- _LCmulcc function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d6e0158543a90135cb10e76f7c8df0102f5c6a68
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2018
---
# <a name="cmulcc-fcmulcc-lcmulcc"></a>_Cmulcc、_FCmulcc、_LCmulcc

2 つの複素数を乗算します。

## <a name="syntax"></a>構文

```C
_Dcomplex _Cmulcc( _Dcomplex x, _Dcomplex y );
_Fcomplex _FCmulcc( _Fcomplex x, _Fcomplex y );
_Lcomplex _LCmulcc( _Lcomplex x, _Lcomplex y );
```

### <a name="parameters"></a>パラメーター

*x*<br/>
乗算する複雑なオペランドの 1 つです。

*y*<br/>
その他の複雑なオペランドを乗算します。

## <a name="return-value"></a>戻り値

A **_Dcomplex**、 **_Fcomplex**、または**_Lcomplex**の複素数の複雑な製品を表す構造*x*と*y*です。

## <a name="remarks"></a>コメント

組み込みの算術演算子は、複合型の Microsoft による実装では動作しないため、 **_Cmulcc**、 **_FCmulcc**、および**_LCmulcc**関数複合型の乗算を簡略化します。

## <a name="requirements"></a>要件

|ルーチン|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|`_Cmulcc`,`_FCmulcc`, `_LCmulcc`|\<complex.h>|\<ccomplex>|

これらの関数は、Microsoft 固有です。 種類**_Dcomplex**、 **_Fcomplex**、および**_Lcomplex**未実装 C99 ネイティブ型に対応する Microsoft 固有の仕様は、**二重 _complex型**、 **float _complex型**、および**long double _complex型**、それぞれします。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](../../c-runtime-library/reference/cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcr、_FCmulcr、_LCmulcr](../../c-runtime-library/reference/cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm、normf、norml](../../c-runtime-library/reference/norm-normf-norml1.md)<br/>
[cproj、cprojf、cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)<br/>
[creal、crealf、creall](../../c-runtime-library/reference/creal-crealf-creall.md)<br/>
[cimag、cimagf、cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)<br/>
