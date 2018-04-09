---
title: norm、normf、norml |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- norm
- normf
- norml
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
- norm
- normf
- norml
- complex/norm
- complex/normf
- complex/norml
dev_langs:
- C++
helpviewer_keywords:
- norm function
- normf function
- norml function
ms.assetid: 9786ecfe-0019-4553-b378-0af6c691e15c
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28c8e05dfc2cc9e42584324a78ba14f37a9b951d
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2018
---
# <a name="norm-normf-norml"></a>norm、normf、norml

複素数の 2 乗の絶対値を取得します。

## <a name="syntax"></a>構文

```C
double norm( _Dcomplex z );
float normf( _Fcomplex z );
long double norml( _Lcomplex z );
```

```cpp
float norm( _Fcomplex z );  // C++ only
long double norm( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>パラメーター

*z*<br/>
複素数。

## <a name="return-value"></a>戻り値

2 乗の大きさ*z*です。

## <a name="remarks"></a>コメント

C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます`norm`を受け取る**_Fcomplex**または**_Lcomplex**値、および戻り値**float**または**長二重**値。 C プログラムでは、`norm`は常に、 **_Dcomplex**値を返す、**二重**値。

## <a name="requirements"></a>要件

|ルーチン|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|`norm`、`normf`、`norml`|\<complex.h>|\<ccomplex>|

**_Fcomplex**、 **_Dcomplex**、および**_Lcomplex**型が実装されていないネイティブ C99 型に相当する Microsoft 固有の仕様**float _complex型**、**二重 _complex型**、および**long double _complex型**、それぞれします。  互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[creal、crealf、creall](../../c-runtime-library/reference/creal-crealf-creall.md)<br/>
[cproj、cprojf、cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)<br/>
[cimag、cimagf、cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)<br/>
