---
title: "iscsym、iscsymf、__iscsym、__iswcsym、__iscsymf、__iswcsymf、_iscsym_l、_iswcsym_l、_iscsymf_l、_iswcsymf_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _iswcsym_l
- __iswcsym
- __iscsym
- _iswcsymf_l
- _iscsym_l
- __iswcsymf
- __iscsymf
- _iscsymf_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _iswcsym_l
- _iswcsymf_l
- iscsymf
- iswcsymf
- __iswcsym
- __iswcsymf
- iscsym
- iswcsym
- __iscsym
- _iscsym_l
- _iscsymf_l
- __iscsymf
- ctype/iscsym
- ctype/iscsymf
- ctype/__iscsym
- ctype/__iscsymf
- ctype/__iscsym_l
- ctype/__iscsymf_l
- ctype/__iswcsym
- ctype/__iswcsymf
- ctype/__iswcsym_l
- ctype/__iswcsymf_l
dev_langs: C++
helpviewer_keywords:
- iscsymf_l function
- iswsym_l function
- _iswcsym_l function
- iscsym_l function
- _iscsymf_l function
- _iswcsymf_l function
- _iscsym_l function
- __iscsym function
- __iswcsymf function
- iswsymf_l function
- __iscsymf function
- __iswcsym function
- iscsym function
- iscsymf function
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3567e6843fc3350d92c6575d320885298140ed50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="iscsym-iscsymf-iscsym-iswcsym-iscsymf-iswcsymf-iscsyml-iswcsyml-iscsymfl-iswcsymfl"></a>iscsym、iscsymf、__iscsym、__iswcsym、__iscsymf、__iswcsymf、_iscsym_l、_iswcsym_l、_iscsymf_l、_iswcsymf_l

整数が識別子に使用できる文字を表すかどうかを判別します。

## <a name="syntax"></a>構文

```C
int __iscsym(
   int c
);
int __iswcsym(
   wint_t c
);
int __iscsymf(
   int c
);
int __iswcsymf(
   wint_t c
);
int _iscsym_l(
   int c,
   _locale_t locale
);
int _iswcsym_l(
   wint_t c,
   _locale_t locale
);
int _iscsymf_l(
   int c,
   _locale_t locale
);
int _iswcsymf_l(
   wint_t c,
   _locale_t locale
);
#define iscsym __iscsym
#define iscsymf __iscsymf
```

### <a name="parameters"></a>パラメーター

*c*  
テストする整数。 *c*関数のナロー文字バージョンについては、0 ~ 255 の範囲内で指定する必要があります。

*locale*  
使用するロケール。

## <a name="return-value"></a>戻り値

両方`__iscsym`と`__iswcsym`場合は、0 以外の値を返す*c*が文字、アンダー スコア、または数字。 両方`__iscsymf`と`__iswcsymf`場合は、0 以外の値を返す*c*が文字またはアンダー スコア。 これらの各ルーチン 0 を返します*c*テスト条件を満たしていません。 これらの関数のバージョン、`_l`使用する点を除いて、サフィックスは同じ、*ロケール*そのロケールに依存する動作に現在のロケールの代わりに渡されました。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="remarks"></a>コメント

これらのルーチンは、プリプロセッサ マクロ _CTYPE_DISABLE_MACROS が定義されていない場合、マクロとして定義されます。 これらのルーチンのマクロ バージョンを使用する際には、引数を複数回評価できます。 引数リスト内で副作用がある式を使用するときにはご注意ください。

旧バージョンと互換性のため、`iscsym`と`iscsymf`マクロとして定義される場合にのみ[&#95; &#95;STDC &#95; #95](../../preprocessor/predefined-macros.md)が定義されていないか、0 として定義されてそれ以外の場合は未定義です。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`iscsym`、`iscsymf`、`__iscsym`、`__iswcsym`、`__iscsymf`、`__iswcsymf`、`_iscsym_l`、`_iswcsym_l`、`_iscsymf_l`、`_iswcsymf_l`|C: \<ctype.h><br /><br /> C++: \<cctype> または \<ctype.h>|

`iscsym`、`iscsymf`、`__iscsym`、`__iswcsym`、`__iscsymf`、`__iswcsymf`、`_iscsym_l`、`_iswcsym_l`、`_iscsymf_l`、`_iswcsymf_l` ルーチンは Microsoft 固有です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>参照

[文字分類](../../c-runtime-library/character-classification.md)   
[ロケール](../../c-runtime-library/locale.md)   
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)