---
title: offsetof マクロ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
- offsetof
dev_langs:
- C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 686de81ecfd4216f3011c93d3bf9be1bfdc55365
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="offsetof-macro"></a>offsetof マクロ

親構造体の先頭からメンバーのオフセットを取得します。

## <a name="syntax"></a>構文

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>パラメーター

*structName*<br/>
親データ構造体の名前。

*メンバー名*<br/>
オフセットを決定する親データ構造体のメンバーの名前。

## <a name="return-value"></a>戻り値

**offsetof**親データ構造体の先頭から指定されたメンバーのバイト数でオフセットを返します。 ビット フィールドには定義されません。

## <a name="remarks"></a>コメント

**Offsetof**マクロのオフセットのバイトで返します*memberName*で指定された構造体の先頭から*structName*型の値として**size_t**です。 持つ型を指定することができます、**構造体**キーワード。

> [!NOTE]
> **offsetof**関数ではないと、C のプロトタイプを使用して説明することはできません。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**offsetof**|\<stddef.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
