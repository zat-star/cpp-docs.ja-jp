---
title: fesetenv |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fesetenv
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fesetenv
- fenv/fesetenv
dev_langs:
- C++
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 466d37a55cbd0d4fdf3e1fc0eed085cb9fcb5b6a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="fesetenv"></a>fesetenv

現在の浮動小数点環境を設定します。

## <a name="syntax"></a>構文

```C
int fesetenv(
   const fenv_t *penv
);
```

### <a name="parameters"></a>パラメーター

*penv*<br/>
ポインター、 **fenv_t**オブジェクトとして含まれている浮動小数点環境設定への呼び出しによって[分かって](fegetenv1.md)または[feholdexcept](feholdexcept2.md)です。 使用して、既定のスタートアップの浮動小数点環境を指定することも、 **FE_DFL_ENV**マクロです。

## <a name="return-value"></a>戻り値

環境が正常に設定された場合は 0 を返します。 それ以外の場合は、0 以外の値を返します。

## <a name="remarks"></a>コメント

**Fesetenv**関数に格納されている値から現在の浮動小数点環境の設定、 **fenv_t**によって指されるオブジェクト*penv*です。 浮動小数点環境とは、浮動小数点計算に影響する一連の状態フラグと制御モードです。 浮動小数点例外の丸めモードと状態フラグが含まれます。  場合*penv*は**FE_DFL_ENV**が有効なを指していませんまたは**fenv_t**オブジェクト、それ以降の動作は未定義です。

この関数を呼び出す例外状態フラグを設定するのには、 *penv*オブジェクトが、それらの例外は発生しません。

この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
