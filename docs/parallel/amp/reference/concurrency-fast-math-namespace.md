---
title: "Concurrency::fast_math Namespace |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::fast_math
dev_langs:
- C++
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 293452bf0a01f7f83a8a41bcb511bc57c9d45f26
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyfastmath-namespace"></a>Concurrency::fast_math 名前空間
`fast_math` 名前空間の関数は精度が低く、単精度 (`float`) のみをサポートし、DirectX の組み込み関数を呼び出します。 各関数には、2 種類のバージョン (たとえば、`cos` と `cosf`) があります。 どちらのバージョンも `float` を受け取り、返しますが、それぞれの DirectX の同じ組み込み関数を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
namespace fast_math;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="functions"></a>関数  
  
|名前|説明|  
|----------|-----------------|  
|[cos 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#cos)|引数の逆余弦を計算します。|  
|[cosf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#cosf)|引数の逆余弦を計算します。|  
|[asin 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#asin)|引数の逆正弦を計算します。|  
|[asinf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#asinf)|引数の逆正弦を計算します。|  
|[atan 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#atan)|引数の逆正接を計算します。|  
|[atan2 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#atan2)|_Y/_X の逆正接を計算します。|  
|[atan2f 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#atan2f)|_Y/_X の逆正接を計算します。|  
|[atanf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#atanf)|引数の逆正接を計算します。|  
|[ceil 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#ceil)|引数の切り上げを計算します。|  
|[ceilf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#ceilf)|引数の切り上げを計算します。|  
|[cos 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#cos)|引数の余弦を計算します。|  
|[cosf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#cosf)|引数の余弦を計算します。|  
|[cosh 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#cosh)|引数の双曲線余弦の値を計算します。|  
|[coshf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#coshf)|引数の双曲線余弦の値を計算します。|  
|[exp 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#exp)|e を底とする引数のべき乗を計算します。|  
|[exp2 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#exp2)|2 を底とする引数のべき乗を計算します。|  
|[exp2f 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#exp2f)|2 を底とする引数のべき乗を計算します。|  
|[expf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#expf)|e を底とする引数のべき乗を計算します。|  
|[fabs 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#fabs)|引数の絶対値を返します。|  
|[fabsf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#fabsf)|引数の絶対値を返します。|  
|[floor 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#floor)|引数の切り捨てを計算します。|  
|[floorf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#floorf)|引数の切り捨てを計算します。|  
|[fmax 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#fmax)|引数の最大数値を判断します。|  
|[fmaxf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#fmaxf)|引数の最大数値を判断します。|  
|[fmin 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#fmin)|引数の最小数値を判断します。|  
|[fminf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#fminf)|引数の最小数値を判断します。|  
|[fmod 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#fmod)|_X/_Y の浮動小数点の剰余を計算します。|  
|[fmodf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#fmodf)|_X/_Y の浮動小数点の剰余を計算します。|  
|[frexp 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#frexp)|_X の仮数と指数を取得します。|  
|[frexpf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#frexpf)|_X の仮数と指数を取得します。|  
|[isfinite 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#isfinite)|引数に有限値が存在するかどうかを判断します。|  
|[isinf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#isinf)|引数が無限値であるかどうかを判断します。|  
|[isnan 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#isnan)|引数が NaN であるかどうかを判断します。|  
|[ldexp 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#ldexp)|仮数と指数から実数を計算します。|  
|[ldexpf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#ldexpf)|仮数と指数から実数を計算します。|  
|[log 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#log)|e を底とする引数の対数を計算します。|  
|[log10 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#log10)|10 を底とする引数の対数を計算します。|  
|[log10f 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#log10f)|10 を底とする引数の対数を計算します。|  
|[log2 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#log2)|2 を底とする引数の対数を計算します。|  
|[log2f 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#log2f)|2 を底とする引数の対数を計算します。|  
|[logf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#logf)|e を底とする引数の対数を計算します。|  
|[modf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#modf)|_X を小数部と整数部に分割します。|  
|[modff 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#modff)|_X を小数部と整数部に分割します。|  
|[pow 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#pow)|_X の _Y 乗を計算します。|  
|[powf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#powf)|_X の _Y 乗を計算します。|  
|[round 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#round)|_X を最も近い整数値に丸めます。|  
|[roundf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#roundf)|_X を最も近い整数値に丸めます。|  
|[rsqrt 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#rsqrt)|引数の平方根の逆数を返します。|  
|[rsqrtf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#rsqrtf)|引数の平方根の逆数を返します。|  
|[signbit 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#signbit)|引数の正弦を返します。|  
|[signbitf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#signbitf)|引数の正弦を返します。|  
|[sin 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#sin)|引数の正弦値を計算します。|  
|[sincos 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#sincos)|_X の正弦と余弦の値を計算します|  
|[sincosf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#sincosf)|_X の正弦と余弦の値を計算します|  
|[sinf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#sinf)|引数の正弦値を計算します。|  
|[sinh 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#sinh)|引数の双曲線正弦の値を計算します。|  
|[sinhf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#sinhf)|引数の双曲線正弦の値を計算します。|  
|[sqrt 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#sqrt)|引数の平方根を計算します。|  
|[sqrtf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#sqrtf)|引数の平方根を計算します。|  
|[tan 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#tan)|引数の正接値を計算します。|  
|[tanf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#tanf)|引数の正接値を計算します。|  
|[tanh 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#tanh)|引数の双曲線正接の値を計算します。|  
|[tanhf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#tanhf)|引数の双曲線正接の値を計算します。|  
|[trunc 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#trunc)|引数を整数コンポーネントに切り捨てます。|  
|[truncf 関数 (fast_math)](concurrency-fast-math-namespace-functions.md#truncf)|引数を整数コンポーネントに切り捨てます。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** amp_math.h  
  
 **Namespace:** concurrency::fast_math  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

