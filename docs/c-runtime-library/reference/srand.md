---
title: srand | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: srand
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords: srand
dev_langs: C++
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 205dcb2ba7d61dff1286fd926e3f10cf2a162e9a
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2018
---
# <a name="srand"></a>srand

によって使用される擬似乱数ジェネレーターのシード開始値を設定、`rand`関数。

## <a name="syntax"></a>構文

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>パラメーター

*シード*  
擬似乱数ジェネレーターのシード

## <a name="remarks"></a>コメント

`srand` 関数は、現在のスレッドに一連の整数の擬似乱数を生成するための開始点を設定します。 結果の同じシーケンスを作成するコード ジェネレーターを再初期化を呼び出して、`srand`関数を使用して、同じ*シード*引数を再度です。 その他の値の*シード*ジェネレーター、擬似乱数シーケンスのさまざまな開始位置を設定します。 `rand` は、生成される擬似乱数を取得します。 呼び出す`rand`への呼び出しの前に`srand`呼び出すことと同じシーケンスを生成`srand`で*シード*1 として渡されます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`srand`|\<stdlib.h>|

互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。

## <a name="example"></a>例

「[rand](../../c-runtime-library/reference/rand.md)」の例をご覧ください。

## <a name="see-also"></a>参照

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)  
[rand](../../c-runtime-library/reference/rand.md)  
