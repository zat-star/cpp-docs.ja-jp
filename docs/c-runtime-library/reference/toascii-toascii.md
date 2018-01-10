---
title: "toascii、__toascii | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __toascii
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
dev_langs: C++
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25e11878772b4c8f7afb07f7297ca80a2a5a0130
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="toascii-toascii"></a>toascii、__toascii

切り捨てにより文字を 7 ビット ASCII に変換します。

## <a name="syntax"></a>構文

```C
int __toascii(
   int c
);
#define toascii __toascii
```

### <a name="parameters"></a>パラメーター

*c*  
変換する文字。

## <a name="return-value"></a>戻り値

`__toascii`値を変換*c*を 7 ビット ASCII の範囲し、結果を返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>コメント

`__toascii` ルーチンは、特定の文字を下位 7 ビットに切り捨てることで、ASCII 文字に変換します。 その他の変換は適用されません。

`__toascii` ルーチンは、プリプロセッサ マクロ _CTYPE_DISABLE_MACROS が定義されていない場合、マクロとして定義されます。 旧バージョンと互換性のため、`toascii`マクロとして定義される場合にのみ[&#95; &#95;STDC &#95; #95](../../preprocessor/predefined-macros.md)が定義されていないか、0 として定義されてそれ以外の場合は定義されません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`toascii`, `__toascii`|C: \<ctype.h><br /><br /> C++: \<cctype> または \<ctype.h>|

`toascii` マクロは POSIX 拡張であり、`__toascii` は POSIX 拡張の Microsoft 固有の実装です。 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。

## <a name="see-also"></a>参照

[データ変換](../../c-runtime-library/data-conversion.md)   
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)   
[to 系関数](../../c-runtime-library/to-functions.md)