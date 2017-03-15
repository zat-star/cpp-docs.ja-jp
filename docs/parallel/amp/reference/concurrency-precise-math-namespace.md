---
title: "Concurrency::precise_math Namespace |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::precise_math
dev_langs:
- C++
ms.assetid: ba653308-dc28-4384-b2fd-6cd718a72f91
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b64bd3e3702701ae2685d6688d88988dd91dc5d0
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyprecisemath-namespace"></a>Concurrency::precise_math 名前空間
`precise_math` 名前空間の関数は C99 に準拠しています。 単一の精度と各関数の倍精度浮動小数点精度バージョンが含まれています。 たとえば、`acos`倍精度のバージョンと`acosf`単精度のバージョンします。 単精度関数も含め、これらの関数では、アクセラレータの倍精度の拡張のサポートが必要です。 使用することができます、 [accelerator::supports_double_precision データ メンバー](accelerator-class.md#supports_double_precision)を特定のアクセラレータでこれらの関数を実行することを確認します。 

  
## <a name="syntax"></a>構文  
  
```cpp  
namespace precise_math;  
```  
  
#### <a name="parameters"></a>パラメーター  
  
## <a name="members"></a>メンバー  
  
### <a name="functions"></a>関数  
  
|名前|説明|  
|----------|-----------------|  
|[acos 関数](concurrency-precise-math-namespace-functions.md#acos)|オーバーロードされます。 引数の逆余弦を計算します。|  
|[acosf 関数](concurrency-precise-math-namespace-functions.md#acosf)|引数の逆余弦を計算します。|  
|[acosh 関数](concurrency-precise-math-namespace-functions.md#acosh)|オーバーロードされます。 引数の逆ハイパーボリック コサインを計算します。|  
|[acoshf 関数](concurrency-precise-math-namespace-functions.md#acoshf)|引数の逆ハイパーボリック コサインを計算します。|  
|[asin 関数](concurrency-precise-math-namespace-functions.md#asin)|オーバーロードされます。 引数の逆正弦を計算します。|  
|[asinf 関数](concurrency-precise-math-namespace-functions.md#asinf)|引数の逆正弦を計算します。|  
|[asinh 関数](concurrency-precise-math-namespace-functions.md#asinh)|オーバーロードされます。 引数の双曲線逆正弦を計算します。|  
|[asinhf 関数](concurrency-precise-math-namespace-functions.md#asinhf)|引数の双曲線逆正弦を計算します。|  
|[atan 関数](concurrency-precise-math-namespace-functions.md#atan)|オーバーロードされます。 引数の逆正接を計算します。|  
|[atan2 関数](concurrency-precise-math-namespace-functions.md#atan2)|オーバーロードされます。 _Y/_X の逆正接を計算します。|  
|[atan2f 関数](concurrency-precise-math-namespace-functions.md#atan2f)|_Y/_X の逆正接を計算します。|  
|[atanf 関数](concurrency-precise-math-namespace-functions.md#atanf)|引数の逆正接を計算します。|  
|[atanh 関数](concurrency-precise-math-namespace-functions.md#atanh)|オーバーロードされます。 引数の双曲線逆正接を計算します。|  
|[atanhf 関数](concurrency-precise-math-namespace-functions.md#atanhf)|引数の双曲線逆正接を計算します。|  
|[cbrt 関数](concurrency-precise-math-namespace-functions.md#cbrt)|オーバーロードされます。 引数の実際の立方根を計算します。|  
|[cbrtf 関数](concurrency-precise-math-namespace-functions.md#cbrtf)|引数の実際の立方根を計算します。|  
|[ceil 関数](concurrency-precise-math-namespace-functions.md#ceil)|オーバーロードされます。 引数の切り上げを計算します。|  
|[ceilf 関数](concurrency-precise-math-namespace-functions.md#ceilf)|引数の切り上げを計算します。|  
|[copysign 関数](concurrency-precise-math-namespace-functions.md#copysign)|オーバーロードされます。 引数の絶対値 _X と _Y の符号を持つ値が生成されます。|  
|[copysignf 関数](concurrency-precise-math-namespace-functions.md#copysignf)|引数の絶対値 _X と _Y の符号を持つ値が生成されます。|  
|[cos 関数](concurrency-precise-math-namespace-functions.md#cos)|オーバーロードされます。 引数の余弦を計算します。|  
|[cosf 関数](concurrency-precise-math-namespace-functions.md#cosf)|引数の余弦を計算します。|  
|[cosh 関数](concurrency-precise-math-namespace-functions.md#cosh)|オーバーロードされます。 引数の双曲線余弦の値を計算します。|  
|[coshf 関数](concurrency-precise-math-namespace-functions.md#coshf)|引数の双曲線余弦の値を計算します。|  
|[cospi 関数](concurrency-precise-math-namespace-functions.md#cospi)|オーバーロードされます。 Pi の余弦の値が計算されます * _X|  
|[cospif 関数](concurrency-precise-math-namespace-functions.md#cospif)|Pi の余弦の値が計算されます * _X|  
|[erf 関数](concurrency-precise-math-namespace-functions.md#erf)|オーバーロードされます。 _X のエラー関数を計算します。|  
|[erfc 関数](concurrency-precise-math-namespace-functions.md#erfc)|オーバーロードされます。 _X の相補誤差関数を計算します。|  
|[erfcf 関数](concurrency-precise-math-namespace-functions.md#erfcf)|_X の相補誤差関数を計算します。|  
|[erfcinv 関数](concurrency-precise-math-namespace-functions.md#erfcinv)|オーバーロードされます。 _X の逆の相補誤差関数を計算します。|  
|[erfcinvf 関数](concurrency-precise-math-namespace-functions.md#erfcinvf)|_X の逆の相補誤差関数を計算します。|  
|[erff 関数](concurrency-precise-math-namespace-functions.md#erff)|_X のエラー関数を計算します。|  
|[erfinv 関数](concurrency-precise-math-namespace-functions.md#erfinv)|オーバーロードされます。 _X の逆エラー関数を計算します。|  
|[erfinvf 関数](concurrency-precise-math-namespace-functions.md#erfinvf)|_X の逆エラー関数を計算します。|  
|[exp 関数](concurrency-precise-math-namespace-functions.md#exp)|オーバーロードされます。 e を底とする引数のべき乗を計算します。|  
|[exp10 関数](concurrency-precise-math-namespace-functions.md#exp10)|オーバーロードされます。 底&10; する引数のべき乗を計算します。|  
|[exp10f 関数](concurrency-precise-math-namespace-functions.md#exp10f)|底&10; する引数のべき乗を計算します。|  
|[exp2 関数](concurrency-precise-math-namespace-functions.md#exp2)|オーバーロードされます。 2 を底とする引数のべき乗を計算します。|  
|[exp2f 関数](concurrency-precise-math-namespace-functions.md#exp2f)|2 を底とする引数のべき乗を計算します。|  
|[expf 関数](concurrency-precise-math-namespace-functions.md#expf)|e を底とする引数のべき乗を計算します。|  
|[expm1 関数](concurrency-precise-math-namespace-functions.md#expm1)|オーバーロードされます。 e を底とする引数のべき乗マイナス 1 を計算します。|  
|[expm1f 関数](concurrency-precise-math-namespace-functions.md#expm1f)|e を底とする引数のべき乗マイナス 1 を計算します。|  
|[fabs 関数](concurrency-precise-math-namespace-functions.md#fabs)|オーバーロードされます。 引数の絶対値を返します。|  
|[fabsf 関数](concurrency-precise-math-namespace-functions.md#fabsf)|引数の絶対値を返します。|  
|[fdim 関数](concurrency-precise-math-namespace-functions.md#fdim)|オーバーロードされます。 引数の正の値の差を決定します。|  
|[fdimf 関数](concurrency-precise-math-namespace-functions.md#fdimf)|引数の正の値の差を決定します。|  
|[floor 関数](concurrency-precise-math-namespace-functions.md#floor)|オーバーロードされます。 引数の切り捨てを計算します。|  
|[floorf 関数](concurrency-precise-math-namespace-functions.md#floorf)|引数の切り捨てを計算します。|  
|[fma 関数](concurrency-precise-math-namespace-functions.md#fma)|オーバーロードされます。 計算 (_X * _Y) + _Z、1 つの三項演算どおりに丸められました。|  
|[fmaf 関数](concurrency-precise-math-namespace-functions.md#fmaf)|計算 (_X * _Y) + _Z、1 つの三項演算どおりに丸められました。|  
|[fmax 関数](concurrency-precise-math-namespace-functions.md#fmax)|オーバーロードされます。 引数の最大数値を判断します。|  
|[fmaxf 関数](concurrency-precise-math-namespace-functions.md#fmaxf)|引数の最大数値を判断します。|  
|[fmin 関数](concurrency-precise-math-namespace-functions.md#fmin)|オーバーロードされます。 引数の最小数値を判断します。|  
|[fminf 関数](concurrency-precise-math-namespace-functions.md#fminf)|引数の最小数値を判断します。|  
|[fmod 関数 (C++ AMP)](concurrency-precise-math-namespace-functions.md#fmod)|オーバーロードされます。 _X/_Y の浮動小数点の剰余を計算します。|  
|[fmodf 関数](concurrency-precise-math-namespace-functions.md#fmodf)|_X/_Y の浮動小数点の剰余を計算します。|  
|[fpclassify 関数](concurrency-precise-math-namespace-functions.md#fpclassify)|オーバーロードされます。 引数の値を NaN、無限、通常、ある、0 と分類します。|  
|[frexp 関数](concurrency-precise-math-namespace-functions.md#frexp)|オーバーロードされます。 _X の仮数と指数を取得します。|  
|[frexpf 関数](concurrency-precise-math-namespace-functions.md#frexpf)|_X の仮数と指数を取得します。|  
|[hypot 関数](concurrency-precise-math-namespace-functions.md#hypot)|オーバーロードされます。 _X と _Y の平方和の平方根を計算します。|  
|[hypotf 関数](concurrency-precise-math-namespace-functions.md#hypotf)|_X と _Y の平方和の平方根を計算します。|  
|[ilogb 関数](concurrency-precise-math-namespace-functions.md#ilogb)|オーバーロードされます。 符号付き整数値として _X の指数部を抽出します。|  
|[ilogbf 関数](concurrency-precise-math-namespace-functions.md#ilogbf)|符号付き整数値として _X の指数部を抽出します。|  
|[isfinite 関数](concurrency-precise-math-namespace-functions.md#isfinite)|オーバーロードされます。 引数に有限値が存在するかどうかを判断します。|  
|[isinf 関数](concurrency-precise-math-namespace-functions.md#isinf)|オーバーロードされます。 引数が無限値であるかどうかを判断します。|  
|[isnan 関数](concurrency-precise-math-namespace-functions.md#isnan)|オーバーロードされます。 引数が NaN であるかどうかを判断します。|  
|[isnormal 関数](concurrency-precise-math-namespace-functions.md#isnormal)|オーバーロードされます。 引数が通常のかどうかを判断します。|  
|[ldexp 関数](concurrency-precise-math-namespace-functions.md#ldexp)|オーバーロードされます。 仮数と指数から実数を計算します。|  
|[ldexpf 関数](concurrency-precise-math-namespace-functions.md#ldexpf)|仮数と指数から実数を計算します。|  
|[lgamma 関数](concurrency-precise-math-namespace-functions.md#lgamma)|オーバーロードされます。 ガンマ値、引数の絶対値の自然対数を計算します。|  
|[lgammaf 関数](concurrency-precise-math-namespace-functions.md#lgammaf)|ガンマ値、引数の絶対値の自然対数を計算します。|  
|[log 関数](concurrency-precise-math-namespace-functions.md#log)|オーバーロードされます。 e を底とする引数の対数を計算します。|  
|[log10 関数](concurrency-precise-math-namespace-functions.md#log10)|オーバーロードされます。 10 を底とする引数の対数を計算します。|  
|[log10f 関数](concurrency-precise-math-namespace-functions.md#log10f)|10 を底とする引数の対数を計算します。|  
|[log1p 関数](concurrency-precise-math-namespace-functions.md#log1p)|オーバーロードされます。 1 と引数の e を底と対数を計算します。|  
|[log1pf 関数](concurrency-precise-math-namespace-functions.md#log1pf)|1 と引数の e を底と対数を計算します。|  
|[log2 関数](concurrency-precise-math-namespace-functions.md#log2)|オーバーロードされます。 2 を底とする引数の対数を計算します。|  
|[log2f 関数](concurrency-precise-math-namespace-functions.md#log2f)|2 を底とする引数の対数を計算します。|  
|[logb 関数](concurrency-precise-math-namespace-functions.md#logb)|オーバーロードされます。 浮動小数点形式での符号付き整数値として、_X の指数部を抽出します。|  
|[logbf 関数](concurrency-precise-math-namespace-functions.md#logbf)|浮動小数点形式での符号付き整数値として、_X の指数部を抽出します。|  
|[logf 関数](concurrency-precise-math-namespace-functions.md#logf)|e を底とする引数の対数を計算します。|  
|[modf 関数](concurrency-precise-math-namespace-functions.md#modf)|オーバーロードされます。 _X を小数部と整数部に分割します。|  
|[modff 関数](concurrency-precise-math-namespace-functions.md#modff)|_X を小数部と整数部に分割します。|  
|[nan 関数](concurrency-precise-math-namespace-functions.md#nan)|簡易な NaN を返します|  
|[nanf 関数](concurrency-precise-math-namespace-functions.md#nanf)|簡易な NaN を返します|  
|[nearbyint 関数](concurrency-precise-math-namespace-functions.md#nearbyint)|オーバーロードされます。 現在の丸めの方向を使用して、浮動小数点形式の整数値への引数を丸めます。|  
|[nearbyintf 関数](concurrency-precise-math-namespace-functions.md#nearbyintf)|現在の丸めの方向を使用して、浮動小数点形式の整数値への引数を丸めます。|  
|[nextafter 関数](concurrency-precise-math-namespace-functions.md#nextafter)|オーバーロードされます。 _Y 方向での _X の後、関数の型で次に表示できる値を確認します|  
|[nextafterf 関数](concurrency-precise-math-namespace-functions.md#nextafterf)|_Y 方向での _X の後、関数の型で次に表示できる値を確認します|  
|[phi 関数](concurrency-precise-math-namespace-functions.md#phi)|オーバーロードされます。 引数の累積分布関数を返します|  
|[phif 関数](concurrency-precise-math-namespace-functions.md#phif)|引数の累積分布関数を返します|  
|[pow 関数します。](concurrency-precise-math-namespace-functions.md#pow)|オーバーロードされます。 _X の _Y 乗を計算します。|  
|[powf 関数](concurrency-precise-math-namespace-functions.md#powf)|_X の _Y 乗を計算します。|  
|[probit 関数](concurrency-precise-math-namespace-functions.md#probit)|オーバーロードされます。 引数の逆累積分布関数を返します|  
|[probitf 関数](concurrency-precise-math-namespace-functions.md#probitf)|引数の逆累積分布関数を返します|  
|[rcbrt 関数](concurrency-precise-math-namespace-functions.md#rcbrt)|オーバーロードされます。 引数の平方根の逆数を返します。|  
|[rcbrtf 関数](concurrency-precise-math-namespace-functions.md#rcbrtf)|引数の平方根の逆数を返します。|  
|[remainder 関数](concurrency-precise-math-namespace-functions.md#remainder)|オーバーロードされます。 剰余を計算します _X REM _Y。|  
|[remainderf 関数](concurrency-precise-math-namespace-functions.md#remainderf)|剰余を計算します _X REM _Y。|  
|[remquo 関数](concurrency-precise-math-namespace-functions.md#remquo)|オーバーロードされます。 _X REM _Y として同じ剰余を計算します。 整数の商 _X/_Y の下位 23 ビットを計算し、_X/_Y と同じ符号にその値を提供します。 _Quo を指す整数で、この署名付きの値を格納します。|  
|[remquof 関数](concurrency-precise-math-namespace-functions.md#remquof)|_X REM _Y として同じ剰余を計算します。 整数の商 _X/_Y の下位 23 ビットを計算し、_X/_Y と同じ符号にその値を提供します。 _Quo を指す整数で、この署名付きの値を格納します。|  
|[round 関数](concurrency-precise-math-namespace-functions.md#round)|オーバーロードされます。 _X を最も近い整数値に丸めます。|  
|[roundf 関数](concurrency-precise-math-namespace-functions.md#roundf)|_X を最も近い整数値に丸めます。|  
|[rsqrt 関数](concurrency-precise-math-namespace-functions.md#rsqrt)|オーバーロードされます。 引数の平方根の逆数を返します。|  
|[rsqrtf 関数](concurrency-precise-math-namespace-functions.md#rsqrtf)|引数の平方根の逆数を返します。|  
|[scalb 関数](concurrency-precise-math-namespace-functions.md#scalb)|オーバーロードされます。 電源 _Y に FLT_RADIX により _X を乗算します。|  
|[scalbf 関数](concurrency-precise-math-namespace-functions.md#scalbf)|電源 _Y に FLT_RADIX により _X を乗算します。|  
|[scalbn 関数](concurrency-precise-math-namespace-functions.md#scalbn)|オーバーロードされます。 電源 _Y に FLT_RADIX により _X を乗算します。|  
|[scalbnf 関数](concurrency-precise-math-namespace-functions.md#scalbnf)|電源 _Y に FLT_RADIX により _X を乗算します。|  
|[signbit 関数](concurrency-precise-math-namespace-functions.md#signbit)|オーバーロードされます。 _X の符号が負の値であるかどうかを決定します。|  
|[signbitf 関数](concurrency-precise-math-namespace-functions.md#signbitf)|_X の符号が負の値であるかどうかを決定します。|  
|[sin 関数](concurrency-precise-math-namespace-functions.md#sin)|オーバーロードされます。 引数の正弦値を計算します。|  
|[sincos 関数](concurrency-precise-math-namespace-functions.md#sincos)|オーバーロードされます。 _X の正弦と余弦の値を計算します|  
|[sincosf 関数](concurrency-precise-math-namespace-functions.md#sincosf)|_X の正弦と余弦の値を計算します|  
|[sinf 関数](concurrency-precise-math-namespace-functions.md#sinf)|引数の正弦値を計算します。|  
|[sinh 関数](concurrency-precise-math-namespace-functions.md#sinh)|オーバーロードされます。 引数の双曲線正弦の値を計算します。|  
|[sinhf 関数](concurrency-precise-math-namespace-functions.md#sinhf)|引数の双曲線正弦の値を計算します。|  
|[sinpi 関数](concurrency-precise-math-namespace-functions.md#sinpi)|オーバーロードされます。 Pi のサイン (正弦) 値を計算 * _X|  
|[sinpif 関数](concurrency-precise-math-namespace-functions.md#sinpif)|Pi のサイン (正弦) 値を計算 * _X|  
|[sqrt 関数](concurrency-precise-math-namespace-functions.md#sqrt)|オーバーロードされます。 引数の squre ルートを計算します。|  
|[sqrtf 関数](concurrency-precise-math-namespace-functions.md#sqrtf)|引数の squre ルートを計算します。|  
|[tan 関数](concurrency-precise-math-namespace-functions.md#tan)|オーバーロードされます。 引数の正接値を計算します。|  
|[tanf 関数](concurrency-precise-math-namespace-functions.md#tanf)|引数の正接値を計算します。|  
|[tanh 関数](concurrency-precise-math-namespace-functions.md#tanh)|オーバーロードされます。 引数の双曲線正接の値を計算します。|  
|[tanhf 関数](concurrency-precise-math-namespace-functions.md#tanhf)|引数の双曲線正接の値を計算します。|  
|[tanpi 関数](concurrency-precise-math-namespace-functions.md#tanpi)|オーバーロードされます。 Pi の正接値を計算 * _X|  
|[tanpif 関数](concurrency-precise-math-namespace-functions.md#tanpif)|Pi の正接値を計算 * _X|  
|[tgamma 関数](concurrency-precise-math-namespace-functions.md#tgamma)|オーバーロードされます。 _X のガンマ関数を計算します。|  
|[tgammaf 関数](concurrency-precise-math-namespace-functions.md#tgammaf)|_X のガンマ関数を計算します。|  
|[trunc 関数](concurrency-precise-math-namespace-functions.md#trunc)|オーバーロードされます。 引数を整数コンポーネントに切り捨てます。|  
|[truncf 関数](concurrency-precise-math-namespace-functions.md#truncf)|引数を整数コンポーネントに切り捨てます。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_math.h  
  
 **名前空間:** Concurrency  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

