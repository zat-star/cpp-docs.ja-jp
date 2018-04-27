---
title: wctype | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- wctype
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
apitype: DLLExport
f1_keywords:
- wctype
dev_langs:
- C++
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbad04d3c56015ddea10a058ae8b262d7f94d40f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="wctype"></a>wctype

ワイド文字のコードの分類規則を決定します。

## <a name="syntax"></a>構文

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>パラメーター

*プロパティ*<br/>
プロパティ文字列。

## <a name="return-value"></a>戻り値

場合、 **LC_CTYPE**の現在のロケールのカテゴリは名前プロパティの文字列に一致する分類規則を定義していない*プロパティ*0 が返されます。 それ以外の場合、[towctrans](towctrans.md) への後続の呼び出しに対する 2 番目の引数として使用するのに適した 0 以外の値を返します。

## <a name="remarks"></a>コメント

この関数では、ワイド文字のコードの分類規則を決定します。 次の呼び出しのペアの動作はすべてのロケールで同じです (ただし、実装によって、"C" ロケールであっても追加の分類規則を定義できます)。

|関数|同等なもの|
|--------------|-------------|
|iswalnum(c)|iswctype (c、wctype ("alnum"))|
|iswalpha(c)|iswctype (c、wctype (「アルファ」))|
|iswcntrl(c)|iswctype (c、wctype (「コントロール」))|
|iswdigit(c)|iswctype (c、wctype (「桁」))|
|iswgraph(c)|iswctype (c、wctype (「グラフ」))|
|iswlower(c)|iswctype (c、wctype (「低」))|
|iswprint(c)|iswctype (c、wctype ("print"))|
|iswpunct(c)|iswctype (c、wctype ("punct"))|
|iswspace(c)|iswctype (c、wctype (「空間」))|
|iswupper(c)|iswctype (c、wctype ("upper"))|
|iswxdigit(c)|iswctype (c、wctype ("xdigit"))|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
