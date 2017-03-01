---
title: "Concurrency::precise_math 名前空間関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 73273a58f73860c77810a6ab59def560962f9539
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyprecisemath-namespace-functions"></a>Concurrency::precise_math 名前空間の関数
||||  
|-|-|-|  
|[acos 関数](#acos)|[acosf 関数](#acosf)|[acosh 関数](#acosh)|  
|[acoshf 関数](#acoshf)|[asin 関数](#asin)|[asinf 関数](#asinf)|  
|[asinh 関数](#asinh)|[asinhf 関数](#asinhf)|[atan 関数](#atan)|  
|[atan2 関数](#atan2)|[atan2f 関数](#atan2f)|[atanf 関数](#atanf)|  
|[atanh 関数](#atanh)|[atanhf 関数](#atanhf)|[cbrt 関数](#cbrt)|  
|[cbrtf 関数](#cbrtf)|[ceil 関数](#ceil)|[ceilf 関数](#ceilf)|  
|[copysign 関数](#copysign)|[copysignf 関数](#copysignf)|[cos 関数](#cos)|  
|[cosf 関数](#cosf)|[cosh 関数](#cosh)|[coshf 関数](#coshf)|  
|[cospi 関数](#cospi)|[cospif 関数](#cospif)|[erf 関数](#erf)|  
|[erfc 関数](#erfc)|[erfcf 関数](#erfcf)|[erfcinv 関数](#erfcinv)|  
|[erfcinvf 関数](#erfcinvf)|[erff 関数](#erff)|[erfinv 関数](#erfinv)|  
|[erfinvf 関数](#erfinvf)|[exp 関数](#exp)|[exp10 関数](#exp10)|  
|[exp10f 関数](#exp10f)|[exp2 関数](#exp2)|[exp2f 関数](#exp2f)|  
|[expf 関数](#expf)|[expm1 関数](#expm1)|[expm1f 関数](#expm1f)|  
|[fabs 関数](#fabs)|[fabsf 関数](#fabsf)|[floor 関数](#floor)| 
|[fdim 関数](#fdim)|[fdimf 関数](#fdimf)|| 
|[floorf 関数](#floorf)|[fma 関数](#fma)|[fmaf 関数](#fmaf)|
[fmax 関数](#fmax)|[fmaxf 関数](#fmaxf)|| 
|[fmin 関数](#fmin)|[fminf 関数](#fminf)|[fmod 関数](#fmod)|  
|[fmodf 関数](#fmodf)|[fpclassify 関数](#fpclassify)|[frexp 関数](#frexp)|  
|[frexpf 関数](#frexpf)|[hypot 関数](#hypot)|[hypotf 関数](#hypotf)|  
|[ilogb 関数](#ilogb)|[ilogbf 関数](#ilogbf)|[isfinite 関数](#isfinite)|  
|[isinf 関数](#isinf)|[isnan 関数](#isnan)|[isnormal 関数](#isnormal)|  
|[ldexp 関数](#ldexp)|[ldexpf 関数](#ldexpf)|[lgamma 関数](#lgamma)|  
|[lgammaf 関数](#lgammaf)|[log 関数](#log)|[log10 関数](#log10)|  
|[log10f 関数](#log10f)|[log1p 関数](#log1p)|[log1pf 関数](#log1pf)|  
|[log2 関数](#log2)|[log2f 関数](#log2f)|[logb 関数](#logb)|  
|[logbf 関数](#logbf)|[logf 関数](#logf)|[modf 関数](#modf)|  
|[modff 関数](#modff)|[nan 関数](#nan)|[nanf 関数](#nanf)|  
|[nearbyint 関数](#nearbyint)|[nearbyintf 関数](#nearbyintf)|[nextafter 関数](#nextafter)|  
|[nextafterf 関数](#nextafterf)|[phi 関数](#phi)|[phif 関数](#phif)|  
|[pow 関数します。](#pow)|[powf 関数](#powf)|[probit 関数](#probit)|  
|[probitf 関数](#probitf)|[rcbrt 関数](#rcbrt)|[rcbrtf 関数](#rcbrtf)|  
|[remainder 関数](#remainder)|[remainderf 関数](#remainderf)|[remquo 関数](#remquo)|  
|[remquof 関数](#remquof)|[round 関数](#round)|[roundf 関数](#roundf)|  
|[rsqrt 関数](#rsqrt)|[rsqrtf 関数](#rsqrtf)|[scalb 関数](#scalb)|  
|[scalbf 関数](#scalbf)|[scalbn 関数](#scalbn)|[scalbnf 関数](#scalbnf)|  
|[signbit 関数](#signbit)|[signbitf 関数](#signbitf)|[sin 関数](#sin)|  
|[sincos 関数](#sincos)|[sincosf 関数](#sincosf)|[sinf 関数](#sinf)|  
|[sinh 関数](#sinh)|[sinhf 関数](#sinhf)|[sinpi 関数](#sinpi)|  
|[sinpif 関数](#sinpif)|[sqrt 関数](#sqrt)|[sqrtf 関数](#sqrtf)|  
|[tan 関数](#tan)|[tanf 関数](#tanf)|[tanh 関数](#tanh)|  
|[tanhf 関数](#tanhf)|[tanpi 関数](#tanpi)|[tanpif 関数](#tanpif)|  
|[tgamma 関数](#tgamma)|[tgammaf 関数](#tgammaf)|[trunc 関数](#trunc)|  
|[truncf 関数](#truncf)|  
  
##  <a name="a-nameacosa--acos-function"></a><a name="acos"></a>acos 関数  
 引数の逆余弦を計算します。  
  
```  
inline float acos(float _X) restrict(amp);

 
inline double acos(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆余弦の値を返します  
  
##  <a name="a-nameacosfa--acosf-function"></a><a name="acosf"></a>acosf 関数  
 引数の逆余弦を計算します。  
  
```  
inline float acosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆余弦の値を返します  
  
##  <a name="a-nameacosha--acosh-function"></a><a name="acosh"></a>acosh 関数  
 引数の逆ハイパーボリック コサインを計算します。  
  
```  
inline float acosh(float _X) restrict(amp);

 
inline double acosh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線逆余弦の値を返します  
  
##  <a name="a-nameacoshfa--acoshf-function"></a><a name="acoshf"></a>acoshf 関数  
 引数の逆ハイパーボリック コサインを計算します。  
  
```  
inline float acoshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線逆余弦の値を返します  
  
##  <a name="a-nameasina--asin-function"></a><a name="asin"></a>asin 関数  
 引数の逆正弦を計算します。  
  
```  
inline float asin(float _X) restrict(amp);

 
inline double asin(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆正弦値を返します  
  
##  <a name="a-nameasinfa--asinf-function"></a><a name="asinf"></a>asinf 関数  
 引数の逆正弦を計算します。  
  
```  
inline float asinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆正弦値を返します  
  
##  <a name="a-nameasinha--asinh-function"></a><a name="asinh"></a>asinh 関数  
 引数の双曲線逆正弦を計算します。  
  
```  
inline float asinh(float _X) restrict(amp);

 
inline double asinh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線逆正弦値を返します  
  
##  <a name="a-nameasinhfa--asinhf-function"></a><a name="asinhf"></a>asinhf 関数  
 引数の双曲線逆正弦を計算します。  
  
```  
inline float asinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線逆正弦値を返します  
  
##  <a name="a-nameatana--atan-function"></a><a name="atan"></a>atan 関数  
 引数の逆正接を計算します。  
  
```  
inline float atan(float _X) restrict(amp);

 
inline double atan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆正接値を返します  
  
##  <a name="a-nameatan2a--atan2-function"></a><a name="atan2"></a>atan2 関数  
 _Y/_X の逆正接を計算します。  
  
```  
inline float atan2(
    float _Y,  
    float _X) restrict(amp);

 
inline double atan2(
    double _Y,  
    double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Y`  
 浮動小数点値  
  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _Y/_X の逆正接値を返します  
  
##  <a name="a-nameatan2fa--atan2f-function"></a><a name="atan2f"></a>atan2f 関数  
 _Y/_X の逆正接を計算します。  
  
```  
inline float atan2f(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Y`  
 浮動小数点値  
  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _Y/_X の逆正接値を返します  
  
##  <a name="a-nameatanfa--atanf-function"></a><a name="atanf"></a>atanf 関数  
 引数の逆正接を計算します。  
  
```  
inline float atanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆正接値を返します  
  
##  <a name="a-nameatanha--atanh-function"></a><a name="atanh"></a>atanh 関数  
 引数の双曲線逆正接を計算します。  
  
```  
inline float atanh(float _X) restrict(amp);

 
inline double atanh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆双曲線正接の値を返します  
  
##  <a name="a-nameatanhfa--atanhf-function"></a><a name="atanhf"></a>atanhf 関数  
 引数の双曲線逆正接を計算します。  
  
```  
inline float atanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆双曲線正接の値を返します  
  
##  <a name="a-namecbrta--cbrt-function"></a><a name="cbrt"></a>cbrt 関数  
 引数の実際の立方根を計算します。  
  
```  
inline float cbrt(float _X) restrict(amp);

 
inline double cbrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の実際の立方根を返します  
  
##  <a name="a-namecbrtfa--cbrtf-function"></a><a name="cbrtf"></a>cbrtf 関数  
 引数の実際の立方根を計算します。  
  
```  
inline float cbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の実際の立方根を返します  
  
##  <a name="a-nameceila--ceil-function"></a><a name="ceil"></a>ceil 関数  
 引数の切り上げを計算します。  
  
```  
inline float ceil(float _X) restrict(amp);

 
inline double ceil(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の切り上げ値を返します  
  
##  <a name="a-nameceilfa--ceilf-function"></a><a name="ceilf"></a>ceilf 関数  
 引数の切り上げを計算します。  
  
```  
inline float ceilf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の切り上げ値を返します  
  
##  <a name="a-namecopysigna--copysign-function"></a><a name="copysign"></a>copysign 関数  
 引数の絶対値 _X と _Y の符号を持つ値が生成されます。  
  
```  
inline float copysign(
    float _X,  
    float _Y) restrict(amp);

 
inline double copysign(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の絶対値 _X と _Y の符号を持つ値を返します  
  
##  <a name="a-namecopysignfa--copysignf-function"></a><a name="copysignf"></a>copysignf 関数  
 引数の絶対値 _X と _Y の符号を持つ値が生成されます。  
  
```  
inline float copysignf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の絶対値 _X と _Y の符号を持つ値を返します  
  
##  <a name="a-namecosa--cos-function"></a><a name="cos"></a>cos 関数  
 引数の余弦を計算します。  
  
```  
inline float cos(float _X) restrict(amp);

 
inline double cos(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の余弦の値を返します  
  
##  <a name="a-namecosfa--cosf-function"></a><a name="cosf"></a>cosf 関数  
 引数の余弦を計算します。  
  
```  
inline float cosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の余弦の値を返します  
  
##  <a name="a-namecosha--cosh-function"></a><a name="cosh"></a>cosh 関数  
 引数の双曲線余弦の値を計算します。  
  
```  
inline float cosh(float _X) restrict(amp);

 
inline double cosh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線余弦の値を返します  
  
##  <a name="a-namecoshfa--coshf-function"></a><a name="coshf"></a>coshf 関数  
 引数の双曲線余弦の値を計算します。  
  
```  
inline float coshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線余弦の値を返します  
  
##  <a name="a-namecospia--cospi-function"></a><a name="cospi"></a>cospi 関数  
 Pi の余弦の値が計算されます * _X  
  
```  
inline float cospi(float _X) restrict(amp);

 
inline double cospi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 Pi の余弦の値を返す * _X  
  
##  <a name="a-namecospifa--cospif-function"></a><a name="cospif"></a>cospif 関数  
 Pi の余弦の値が計算されます * _X  
  
```  
inline float cospif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 Pi の余弦の値を返す * _X  
  
##  <a name="a-nameerfa--erf-function"></a><a name="erf"></a>erf 関数  
 _X のエラー関数を計算します。  
  
```  
inline float erf(float _X) restrict(amp);

 
inline double erf(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の誤差関数を返します  
  
##  <a name="a-nameerfca--erfc-function"></a><a name="erfc"></a>erfc 関数  
 _X の相補誤差関数を計算します。  
  
```  
inline float erfc(float _X) restrict(amp);

 
inline double erfc(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の相補誤差関数を返します  
  
##  <a name="a-nameerfcfa--erfcf-function"></a><a name="erfcf"></a>erfcf 関数  
 _X の相補誤差関数を計算します。  
  
```  
inline float erfcf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の相補誤差関数を返します  
  
##  <a name="a-nameerfcinva--erfcinv-function"></a><a name="erfcinv"></a>erfcinv 関数  
 _X の逆の相補誤差関数を計算します。  
  
```  
inline float erfcinv(float _X) restrict(amp);

 
inline double erfcinv(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の逆の相補誤差関数を返します  
  
##  <a name="a-nameerfcinvfa--erfcinvf-function"></a><a name="erfcinvf"></a>erfcinvf 関数  
 _X の逆の相補誤差関数を計算します。  
  
```  
inline float erfcinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の逆の相補誤差関数を返します  
  
##  <a name="a-nameerffa--erff-function"></a><a name="erff"></a>erff 関数  
 _X のエラー関数を計算します。  
  
```  
inline float erff(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の誤差関数を返します  
  
##  <a name="a-nameerfinva--erfinv-function"></a><a name="erfinv"></a>erfinv 関数  
 _X の逆エラー関数を計算します。  
  
```  
inline float erfinv(float _X) restrict(amp);

 
inline double erfinv(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の逆関数します。  
  
##  <a name="a-nameerfinvfa--erfinvf-function"></a><a name="erfinvf"></a>erfinvf 関数  
 _X の逆エラー関数を計算します。  
  
```  
inline float erfinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の逆関数します。  
  
##  <a name="a-nameexp10a--exp10-function"></a><a name="exp10"></a>exp10 関数  
 底&10; する引数のべき乗を計算します。  
  
```  
inline float exp10(float _X) restrict(amp);

 
inline double exp10(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 底&10; する引数のべき乗を返します。  
  
##  <a name="a-nameexp10fa--exp10f-function"></a><a name="exp10f"></a>exp10f 関数  
 底&10; する引数のべき乗を計算します。  
  
```  
inline float exp10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 底&10; する引数のべき乗を返します。  
  
##  <a name="a-nameexpm1a--expm1-function"></a><a name="expm1"></a>expm1 関数  
 e を底とする引数のべき乗マイナス 1 を計算します。  
  
```  
inline float expm1(float exponent) restrict(amp);

 
inline double expm1(double exponent) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `exponent`  
 指数項*n*算術式の`e` <sup>n</sup>ここで、`e`自然対数の底です。  
  
### <a name="return-value"></a>戻り値  
 e を底とする引数のべき乗マイナス 1 を返します。  
  
##  <a name="a-nameexpm1fa--expm1f-function"></a><a name="expm1f"></a>expm1f 関数  
 e を底とする引数のべき乗マイナス 1 を計算します。  
  
```  
inline float expm1f(float exponent) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `exponent`  
 指数項*n*算術式の`e` <sup>n</sup>ここで、`e`自然対数の底です。  
  
### <a name="return-value"></a>戻り値  
 e を底とする引数のべき乗マイナス 1 を返します。  
  
##  <a name="a-nameexpa--exp-function"></a><a name="exp"></a>exp 関数  
 e を底とする引数のべき乗を計算します。  
  
```  
inline float exp(float _X) restrict(amp);

 
inline double exp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 E を底とする引数のべき乗を返します。  
  
##  <a name="a-nameexpfa--expf-function"></a><a name="expf"></a>expf 関数  
 e を底とする引数のべき乗を計算します。  
  
```  
inline float expf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 E を底とする引数のべき乗を返します。  
  
##  <a name="a-nameexp2a--exp2-function"></a><a name="exp2"></a>exp2 関数  
 2 を底とする引数のべき乗を計算します。  
  
```  
inline float exp2(float _X) restrict(amp);

 
inline double exp2(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 2 を底とする引数のべき乗を返します。  
  
##  <a name="a-nameexp2fa--exp2f-function"></a><a name="exp2f"></a>exp2f 関数  
 2 を底とする引数のべき乗を計算します。  
  
```  
inline float exp2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 2 を底とする引数のべき乗を返します。  
  
##  <a name="a-namefabsa--fabs-function"></a><a name="fabs"></a>fabs 関数  
 引数の絶対値を返します。  
  
```  
inline float fabs(float _X) restrict(amp);

 
inline double fabs(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の絶対値を返します。  
  
##  <a name="a-namefabsfa--fabsf-function"></a><a name="fabsf"></a>fabsf 関数  
 引数の絶対値を返します。  
  
```  
inline float fabsf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の絶対値を返します。  

## <a name="a-namefdima-fdim-function"></a><a name="fdim"></a>fdim 関数  
引数間の正の値の差を計算します。
```  
inline float fdim(
   float _X,
   float _Y
) restrict(amp);
inline double fdim(
   double _X,
   double _Y
) restrict(amp);
``` 
### <a name="parameters"></a>パラメーター
`_X`浮動小数点値`_Y`浮動小数点値


### <a name="return-value"></a>戻り値
_X と _Y _X の _Y; より大きい場合の違いそれ以外の場合、+0。
 
## <a name="a-namefdimfa-fdimf-function"></a><a name="fdimf"></a>fdimf 関数
引数間の正の値の差を計算します。
```
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```
### <a name="parameters"></a>パラメーター
`_X`浮動小数点値`_Y`浮動小数点値

### <a name="return-value"></a>戻り値
_X と _Y _X の _Y; より大きい場合の違いそれ以外の場合、+0。 
  
##  <a name="a-namefloora--floor-function"></a><a name="floor"></a>floor 関数  
 引数の切り捨てを計算します。  
  
```  
inline float floor(float _X) restrict(amp);

 
inline double floor(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の切り捨て値を返します  
  
##  <a name="a-namefloorfa--floorf-function"></a><a name="floorf"></a>floorf 関数  
 引数の切り捨てを計算します。  
  
```  
inline float floorf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の切り捨て値を返します  

## <a name="a-namefma-fma-function"></a><a name="fma">fma 関数  
1 番目と&2; 番目に指定された引数の積を計算し、その結果に&3; 番目に指定された引数を加えます。全体の計算は単一の操作として実行されます。
```
inline float fma(
   float _X,
   float _Y,
   float _Z
) restrict(amp);

inline double fma(
   double _X,
   double _Y,
   double _Z
) restrict(amp);
```
### <a name="parameters"></a>パラメーター
`_X`最初の浮動小数点引数。
`_Y`2 番目の浮動小数点引数。
`_Z`3 番目の浮動小数点引数。

### <a name="return-value"></a>戻り値
式の結果 (_X * _Y) + _Z します。 全体の計算は単一の操作として実行されます。つまり、サブ式は無限の精度で計算され、最終結果だけが丸められます。 

## <a name="a-namefmafa-fmaf-function"></a><a name="fmaf"></a>fmaf 関数  
1 番目と&2; 番目に指定された引数の積を計算し、その結果に&3; 番目に指定された引数を加えます。全体の計算は単一の操作として実行されます。
```
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```  
### <a name="parameters"></a>パラメーター
`_X`最初の浮動小数点引数。
`_Y`2 番目の浮動小数点引数。
`_Z`3 番目の浮動小数点引数。

### <a name="return-value"></a>戻り値
式の結果 (_X * _Y) + _Z します。 全体の計算は単一の操作として実行されます。つまり、サブ式は無限の精度で計算され、最終結果だけが丸められます。
  
##  <a name="a-namefmaxa--fmax-function"></a><a name="fmax"></a>fmax 関数  
 引数の最大数値を判断します。  
  
```  
inline float fmax(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmax(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の最大数値を返します。  
  
##  <a name="a-namefmaxfa--fmaxf-function"></a><a name="fmaxf"></a>fmaxf 関数  
 引数の最大数値を判断します。  
  
```  
inline float fmaxf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の最大数値を返します。  
  
##  <a name="a-namefmina--fmin-function"></a><a name="fmin"></a>fmin 関数  
 引数の最小数値を判断します。  
  
```  
inline float fmin(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmin(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の最小数値を返します。  
  
##  <a name="a-namefminfa--fminf-function"></a><a name="fminf"></a>fminf 関数  
 引数の最小数値を判断します。  
  
```  
inline float fminf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の最小数値を返します。  
  
##  <a name="a-namefmoda--fmod-function-c-amp"></a><a name="fmod"></a>fmod 関数 (C++ AMP)  
 2 番目の指定された引数で除算した&1; 番目の指定された引数の剰余を計算します。  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmod(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 最初の浮動小数点引数。  
  
 `_Y`  
 2 番目の浮動小数点引数。  
  
### <a name="return-value"></a>戻り値  
 残りの部分`_X`で割った値`_Y`; の値である、 `_X`  -  `_Y` *n*ここで、 *n*整数は、ようにの大きさ`_X`  -  `_Y` *n*の絶対値よりも小さい`_Y`します。  
  
##  <a name="a-namefmodfa--fmodf-function"></a><a name="fmodf"></a>fmodf 関数  
 2 番目の指定された引数で除算した&1; 番目の指定された引数の剰余を計算します。  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 最初の浮動小数点引数。  
  
 `_Y`  
 2 番目の浮動小数点引数。  
  
### <a name="return-value"></a>戻り値  
 残りの部分`_X`で割った値`_Y`; の値である、 `_X`  -  `_Y` *n*ここで、 *n*整数は、ようにの大きさ`_X`  -  `_Y` *n*の絶対値よりも小さい`_Y`します。  
  
##  <a name="a-namefpclassifya--fpclassify-function"></a><a name="fpclassify"></a>fpclassify 関数  
 引数の値を NaN、無限、通常、ある、0 と分類します。  
  
```  
inline int fpclassify(float _X) restrict(amp);

 
inline int fpclassify(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の値を適切な数の分類マクロの値を返します。  
  
##  <a name="a-namefrexpa--frexp-function"></a><a name="frexp"></a>frexp 関数  
 _X の仮数と指数を取得します。  
  
```  
inline float frexp(
    float _X,  
    _Out_ int* _Exp) restrict(amp);

 
inline double frexp(
    double _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Exp`  
 浮動小数点値の _X の整数の指数を返します  
  
### <a name="return-value"></a>戻り値  
 仮数 _X を返します  
  
##  <a name="a-namefrexpfa--frexpf-function"></a><a name="frexpf"></a>frexpf 関数  
 _X の仮数と指数を取得します。  
  
```  
inline float frexpf(
    float _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Exp`  
 浮動小数点値の _X の整数の指数を返します  
  
### <a name="return-value"></a>戻り値  
 仮数 _X を返します  
  
##  <a name="a-namehypota--hypot-function"></a><a name="hypot"></a>hypot 関数  
 _X と _Y の平方和の平方根を計算します。  
  
```  
inline float hypot(
    float _X,  
    float _Y) restrict(amp);

 
inline double hypot(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X と _Y の平方和の平方根を返します  
  
##  <a name="a-namehypotfa--hypotf-function"></a><a name="hypotf"></a>hypotf 関数  
 _X と _Y の平方和の平方根を計算します。  
  
```  
inline float hypotf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X と _Y の平方和の平方根を返します  
  
##  <a name="a-nameilogba--ilogb-function"></a><a name="ilogb"></a>ilogb 関数  
 符号付き整数値として _X の指数部を抽出します。  
  
```  
inline int ilogb(float _X) restrict(amp);

 
inline int ilogb(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 符号付き整数値として _X の指数を返します  
  
##  <a name="a-nameilogbfa--ilogbf-function"></a><a name="ilogbf"></a>ilogbf 関数  
 符号付き整数値として _X の指数部を抽出します。  
  
```  
inline int ilogbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 符号付き整数値として _X の指数を返します  
  
##  <a name="a-nameisfinitea--isfinite-function"></a><a name="isfinite"></a>isfinite 関数  
 引数に有限値が存在するかどうかを判断します。  
  
```  
inline int isfinite(float _X) restrict(amp);

 
inline int isfinite(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数は有限値を持つ場合にのみ、0 以外の値を返します  
  
##  <a name="a-nameisinfa--isinf-function"></a><a name="isinf"></a>isinf 関数  
 引数が無限値であるかどうかを判断します。  
  
```  
inline int isinf(float _X) restrict(amp);

 
inline int isinf(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数が無限の値を持つ場合にのみ、0 以外の値を返します  
  
##  <a name="a-nameisnana--isnan-function"></a><a name="isnan"></a>isnan 関数  
 引数が NaN であるかどうかを判断します。  
  
```  
inline int isnan(float _X) restrict(amp);

 
inline int isnan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数が NaN 値を持つ場合にのみ、0 以外の値を返します  
  
##  <a name="a-nameisnormala--isnormal-function"></a><a name="isnormal"></a>isnormal 関数  
 引数が通常のかどうかを判断します。  
  
```  
inline int isnormal(float _X) restrict(amp);

 
inline int isnormal(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数は、標準の値を持つ場合にのみ、0 以外の値を返します  
  
##  <a name="a-nameldexpa--ldexp-function"></a><a name="ldexp"></a>ldexp 関数  
 指定された仮数と指数から実数を計算します。  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);

 
inline double ldexp(
    double _X,  
    double _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点の値、仮数  
  
 `_Exp`  
 整数値、指数  
  
### <a name="return-value"></a>戻り値  
 _X * 2^_Exp を返します  
  
##  <a name="a-nameldexpfa--ldexpf-function"></a><a name="ldexpf"></a>ldexpf 関数  
 指定された仮数と指数から実数を計算します。  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点の値、仮数  
  
 `_Exp`  
 整数値、指数  
  
### <a name="return-value"></a>戻り値  
 _X * 2^_Exp を返します  
  
##  <a name="a-namelgammaa--lgamma-function"></a><a name="lgamma"></a>lgamma 関数  
 ガンマ値、引数の絶対値の自然対数を計算します。  
  
```  
inline float lgamma(
    float _X,  
    _Out_ int* _Sign) restrict(amp);

 
inline double lgamma(
    double _X,  
    _Out_ int* _Sign) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Sign`  
 正弦を返します。  
  
### <a name="return-value"></a>戻り値  
 ガンマ値、引数の絶対値の自然対数を返します  
  
##  <a name="a-namelgammafa--lgammaf-function"></a><a name="lgammaf"></a>lgammaf 関数  
 ガンマ値、引数の絶対値の自然対数を計算します。  
  
```  
inline float lgammaf(
    float _X,  
    _Out_ int* _Sign) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Sign`  
 正弦を返します。  
  
### <a name="return-value"></a>戻り値  
 ガンマ値、引数の絶対値の自然対数を返します  
  
##  <a name="a-nameloga--log-function"></a><a name="log"></a>log 関数  
 e を底とする引数の対数を計算します。  
  
```  
inline float log(float _X) restrict(amp);

 
inline double log(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の e を底と対数を返します  
  
##  <a name="a-namelog10a--log10-function"></a><a name="log10"></a>log10 関数  
 10 を底とする引数の対数を計算します。  
  
```  
inline float log10(float _X) restrict(amp);

 
inline double log10(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の底&10; の対数を返します  
  
##  <a name="a-namelog10fa--log10f-function"></a><a name="log10f"></a>log10f 関数  
 10 を底とする引数の対数を計算します。  
  
```  
inline float log10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の底&10; の対数を返します  
  
##  <a name="a-namelog1pa--log1p-function"></a><a name="log1p"></a>log1p 関数  
 1 と引数の e を底と対数を計算します。  
  
```  
inline float log1p(float _X) restrict(amp);

 
inline double log1p(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 1 と引数の e を底と対数を返します  
  
##  <a name="a-namelog1pfa--log1pf-function"></a><a name="log1pf"></a>log1pf 関数  
 1 と引数の e を底と対数を計算します。  
  
```  
inline float log1pf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 1 と引数の e を底と対数を返します  
  
##  <a name="a-namelog2a--log2-function"></a><a name="log2"></a>log2 関数  
 2 を底とする引数の対数を計算します。  
  
```  
inline float log2(float _X) restrict(amp);

 
inline double log2(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の底&10; の対数を返します  
  
##  <a name="a-namelog2fa--log2f-function"></a><a name="log2f"></a>log2f 関数  
 2 を底とする引数の対数を計算します。  
  
```  
inline float log2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の底&10; の対数を返します  
  
##  <a name="a-namelogba--logb-function"></a><a name="logb"></a>logb 関数  
 浮動小数点形式での符号付き整数値として、_X の指数部を抽出します。  
  
```  
inline float logb(float _X) restrict(amp);

 
inline double logb(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の符号付き指数を返します  
  
##  <a name="a-namelogbfa--logbf-function"></a><a name="logbf"></a>logbf 関数  
 浮動小数点形式での符号付き整数値として、_X の指数部を抽出します。  
  
```  
inline float logbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の符号付き指数を返します  
  
##  <a name="a-namelogfa--logf-function"></a><a name="logf"></a>logf 関数  
 e を底とする引数の対数を計算します。  
  
```  
inline float logf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の e を底と対数を返します  
  
##  <a name="a-namemodfa--modf-function"></a><a name="modf"></a>modf 関数  
 指定された引数を小数部と整数部に分割します。  
  
```  
inline float modf(
    float _X,  
    _Out_ float* _Iptr) restrict(amp);

 
inline double modf(
    double _X,  
    _Out_ double* _Iptr) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Iptr` (out パラメーター)  
 浮動小数点値としての、`_X` の整数部分。  
  
### <a name="return-value"></a>戻り値  
 `_X` の符号付の小数部分。  
  
##  <a name="a-namemodffa--modff-function"></a><a name="modff"></a>modff 関数  
 指定された引数を小数部と整数部に分割します。  
  
```  
inline float modff(
    float _X,  
    _Out_ float* _Iptr) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Iptr`  
 浮動小数点値としての、`_X` の整数部分。  
  
### <a name="return-value"></a>戻り値  
 `_X` の符号付き小数部を返します。  
  
##  <a name="a-namenana--nan-function"></a><a name="nan"></a>nan 関数  
 簡易な NaN を返します  
  
```  
inline double nan(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 整数値  
  
### <a name="return-value"></a>戻り値  
 _X に示されている内容で、使用可能な場合は、簡易な NaN を返します  
  
##  <a name="a-namenanfa--nanf-function"></a><a name="nanf"></a>nanf 関数  
 簡易な NaN を返します  
  
```  
inline float nanf(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 整数値  
  
### <a name="return-value"></a>戻り値  
 _X に示されている内容で、使用可能な場合は、簡易な NaN を返します  
  
##  <a name="a-namenearbyinta--nearbyint-function"></a><a name="nearbyint"></a>nearbyint 関数  
 現在の丸めの方向を使用して、浮動小数点形式の整数値への引数を丸めます。  
  
```  
inline float nearbyint(float _X) restrict(amp);

 
inline double nearbyint(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 丸められた整数値を返します。  
  
##  <a name="a-namenearbyintfa--nearbyintf-function"></a><a name="nearbyintf"></a>nearbyintf 関数  
 現在の丸めの方向を使用して、浮動小数点形式の整数値への引数を丸めます。  
  
```  
inline float nearbyintf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 丸められた整数値を返します。  
  
##  <a name="a-namenextaftera--nextafter-function"></a><a name="nextafter"></a>nextafter 関数  
 _Y 方向での _X の後、関数の型で次に表示できる値を確認します  
  
```  
inline float nextafter(
    float _X,  
    float _Y) restrict(amp);

 
inline double nextafter(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _Y 方向での _X の後で、関数の型で次に表示できる値を返します  
  
##  <a name="a-namenextafterfa--nextafterf-function"></a><a name="nextafterf"></a>nextafterf 関数  
 _Y 方向での _X の後、関数の型で次に表示できる値を確認します  
  
```  
inline float nextafterf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _Y 方向での _X の後で、関数の型で次に表示できる値を返します  
  
##  <a name="a-namephia--phi-function"></a><a name="phi"></a>phi 関数  
 引数の累積分布関数を返します  
  
```  
inline float phi(float _X) restrict(amp);

 
inline double phi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の累積分布関数を返します  
  
##  <a name="a-namephifa--phif-function"></a><a name="phif"></a>phif 関数  
 引数の累積分布関数を返します  
  
```  
inline float phif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の累積分布関数を返します  
  
##  <a name="a-namepowa--pow-function"></a><a name="pow"></a>pow 関数します。  
 _X の _Y 乗を計算します。  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);

 
inline double pow(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 基本浮動小数点の値  
  
 `_Y`  
 浮動小数点値、指数  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-namepowfa--powf-function"></a><a name="powf"></a>powf 関数  
 _X の _Y 乗を計算します。  
  
```  
inline float powf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 基本浮動小数点の値  
  
 `_Y`  
 浮動小数点値、指数  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-nameprobita--probit-function"></a><a name="probit"></a>probit 関数  
 引数の逆累積分布関数を返します  
  
```  
inline float probit(float _X) restrict(amp);

 
inline double probit(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆累積分布関数を返します  
  
##  <a name="a-nameprobitfa--probitf-function"></a><a name="probitf"></a>probitf 関数  
 引数の逆累積分布関数を返します  
  
```  
inline float probitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆累積分布関数を返します  
  
##  <a name="a-namercbrta--rcbrt-function"></a><a name="rcbrt"></a>rcbrt 関数  
 引数の平方根の逆数を返します。  
  
```  
inline float rcbrt(float _X) restrict(amp);

 
inline double rcbrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の平方根の逆数を返します。  
  
##  <a name="a-namercbrtfa--rcbrtf-function"></a><a name="rcbrtf"></a>rcbrtf 関数  
 引数の平方根の逆数を返します。  
  
```  
inline float rcbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の平方根の逆数を返します。  
  
##  <a name="a-nameremaindera--remainder-function"></a><a name="remainder"></a>remainder 関数  
 剰余を計算します _X REM _Y。  
  
```  
inline float remainder(
    float _X,  
    float _Y) restrict(amp);

 
inline double remainder(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X REM _Y を返します  
  
##  <a name="a-nameremainderfa--remainderf-function"></a><a name="remainderf"></a>remainderf 関数  
 剰余を計算します _X REM _Y。  
  
```  
inline float remainderf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X REM _Y を返します  
  
##  <a name="a-nameremquoa--remquo-function"></a><a name="remquo"></a>remquo 関数  
 2 番目の指定された引数で除算した&1; 番目の指定された引数の剰余を計算します。 また、1 番目に指定された引数の有効桁数を&2; 番目に指定された引数の有効桁で割った商を計算し、3 番目の引数で指定された位置を使用して商を返します。  
  
```  
inline float remquo(
    float _X,  
    float _Y,  
    _Out_ int* _Quo) restrict(amp);

 
inline double remquo(
    double _X,  
    double _Y,  
    _Out_ int* _Quo) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 最初の浮動小数点引数。  
  
 `_Y`  
 2 番目の浮動小数点引数。  
  
 `_Quo` (out パラメーター)  
 `_X` の小数部ビットを `_Y` の小数部ビットで割った商を返すために使用される整数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 `_X` を `_Y` で割った剰余を返します。  
  
##  <a name="a-nameremquofa--remquof-function"></a><a name="remquof"></a>remquof 関数  
 2 番目の指定された引数で除算した&1; 番目の指定された引数の剰余を計算します。 また、1 番目に指定された引数の有効桁数を&2; 番目に指定された引数の有効桁で割った商を計算し、3 番目の引数で指定された位置を使用して商を返します。  
  
```  
inline float remquof(
    float _X,  
    float _Y,  
    _Out_ int* _Quo) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 最初の浮動小数点引数。  
  
 `_Y`  
 2 番目の浮動小数点引数。  
  
 `_Quo` (out パラメーター)  
 `_X` の小数部ビットを `_Y` の小数部ビットで割った商を返すために使用される整数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 `_X` を `_Y` で割った剰余を返します。  
  
##  <a name="a-namerounda--round-function"></a><a name="round"></a>round 関数  
 _X を最も近い整数値に丸めます。  
  
```  
inline float round(float _X) restrict(amp);

 
inline double round(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の最も近い整数値を返します  
  
##  <a name="a-nameroundfa--roundf-function"></a><a name="roundf"></a>roundf 関数  
 _X を最も近い整数値に丸めます。  
  
```  
inline float roundf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の最も近い整数値を返します  
  
##  <a name="a-namersqrta--rsqrt-function"></a><a name="rsqrt"></a>rsqrt 関数  
 引数の平方根の逆数を返します。  
  
```  
inline float rsqrt(float _X) restrict(amp);

 
inline double rsqrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の平方根の逆数を返します。  
  
##  <a name="a-namersqrtfa--rsqrtf-function"></a><a name="rsqrtf"></a>rsqrtf 関数  
 引数の平方根の逆数を返します。  
  
```  
inline float rsqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の平方根の逆数を返します。  
  
##  <a name="a-namescalba--scalb-function"></a><a name="scalb"></a>scalb 関数  
 電源 _Y に FLT_RADIX により _X を乗算します。  
  
```  
inline float scalb(
    float _X,  
    float _Y) restrict(amp);

 
inline double scalb(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X を返す * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namescalbfa--scalbf-function"></a><a name="scalbf"></a>scalbf 関数  
 電源 _Y に FLT_RADIX により _X を乗算します。  
  
```  
inline float scalbf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X を返す * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namescalbna--scalbn-function"></a><a name="scalbn"></a>scalbn 関数  
 電源 _Y に FLT_RADIX により _X を乗算します。  
  
```  
inline float scalbn(
    float _X,  
    int _Y) restrict(amp);

 
inline double scalbn(
    double _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 整数値  
  
### <a name="return-value"></a>戻り値  
 _X を返す * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namescalbnfa--scalbnf-function"></a><a name="scalbnf"></a>scalbnf 関数  
 電源 _Y に FLT_RADIX により _X を乗算します。  
  
```  
inline float scalbnf(
    float _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 整数値  
  
### <a name="return-value"></a>戻り値  
 _X を返す * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namesignbita--signbit-function"></a><a name="signbit"></a>signbit 関数  
 _X の符号が負の値であるかどうかを決定します。  
  
```  
inline int signbit(float _X) restrict(amp);

 
inline int signbit(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の符号が負の値場合にのみ、0 以外の値を返します  
  
##  <a name="a-namesignbitfa--signbitf-function"></a><a name="signbitf"></a>signbitf 関数  
 _X の符号が負の値であるかどうかを決定します。  
  
```  
inline int signbitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の符号が負の値場合にのみ、0 以外の値を返します  
  
##  <a name="a-namesina--sin-function"></a><a name="sin"></a>sin 関数  
 引数の正弦値を計算します。  
  
```  
inline float sin(float _X) restrict(amp);

 
inline double sin(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の正弦値を返します  
  
##  <a name="a-namesinfa--sinf-function"></a><a name="sinf"></a>sinf 関数  
 引数の正弦値を計算します。  
  
```  
inline float sinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の正弦値を返します  
  
##  <a name="a-namesincosa--sincos-function"></a><a name="sincos"></a>sincos 関数  
 _X の正弦と余弦の値を計算します  
  
```  
inline void sincos(
    float _X,  
    _Out_ float* _S,  
    _Out_ float* _C) restrict(amp);

 
inline void sincos(
    double _X,  
    _Out_ double* _S,  
    _Out_ double* _C) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_S`  
 _X の正弦値を返します  
  
 `_C`  
 _X の余弦の値を返します  
  
##  <a name="a-namesincosfa--sincosf-function"></a><a name="sincosf"></a>sincosf 関数  
 _X の正弦と余弦の値を計算します  
  
```  
inline void sincosf(
    float _X,  
    _Out_ float* _S,  
    _Out_ float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_S`  
 _X の正弦値を返します  
  
 `_C`  
 _X の余弦の値を返します  
  
##  <a name="a-namesinha--sinh-function"></a><a name="sinh"></a>sinh 関数  
 引数の双曲線正弦の値を計算します。  
  
```  
inline float sinh(float _X) restrict(amp);

 
inline double sinh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線正弦の値を返します  
  
##  <a name="a-namesinhfa--sinhf-function"></a><a name="sinhf"></a>sinhf 関数  
 引数の双曲線正弦の値を計算します。  
  
```  
inline float sinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線正弦の値を返します  
  
##  <a name="a-namesinpia--sinpi-function"></a><a name="sinpi"></a>sinpi 関数  
 Pi のサイン (正弦) 値を計算 * _X  
  
```  
inline float sinpi(float _X) restrict(amp);

 
inline double sinpi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 Pi のサイン (正弦) 値を返す * _X  
  
##  <a name="a-namesinpifa--sinpif-function"></a><a name="sinpif"></a>sinpif 関数  
 Pi のサイン (正弦) 値を計算 * _X  
  
```  
inline float sinpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 Pi のサイン (正弦) 値を返す * _X  
  
##  <a name="a-namesqrta--sqrt-function"></a><a name="sqrt"></a>sqrt 関数  
 引数の squre ルートを計算します。  
  
```  
inline float sqrt(float _X) restrict(amp);

 
inline double sqrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の squre ルートを返します  
  
##  <a name="a-namesqrtfa--sqrtf-function"></a><a name="sqrtf"></a>sqrtf 関数  
 引数の squre ルートを計算します。  
  
```  
inline float sqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の squre ルートを返します  
  
##  <a name="a-nametana--tan-function"></a><a name="tan"></a>tan 関数  
 引数の正接値を計算します。  
  
```  
inline float tan(float _X) restrict(amp);

 
inline double tan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の正接値を返します  
  
##  <a name="a-nametanfa--tanf-function"></a><a name="tanf"></a>tanf 関数  
 引数の正接値を計算します。  
  
```  
inline float tanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の正接値を返します  
  
##  <a name="a-nametanha--tanh-function"></a><a name="tanh"></a>tanh 関数  
 引数の双曲線正接の値を計算します。  
  
```  
inline float tanh(float _X) restrict(amp);

 
inline double tanh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線正接の値を返します  
  
##  <a name="a-nametanhfa--tanhf-function"></a><a name="tanhf"></a>tanhf 関数  
 引数の双曲線正接の値を計算します。  
  
```  
inline float tanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線正接の値を返します  
  
##  <a name="a-nametanpia--tanpi-function"></a><a name="tanpi"></a>tanpi 関数  
 Pi の正接値を計算 * _X  
  
```  
inline float tanpi(float _X) restrict(amp);

 
inline double tanpi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 Pi の正接値を返します * _X  
  
##  <a name="a-nametanpifa--tanpif-function"></a><a name="tanpif"></a>tanpif 関数  
 Pi の正接値を計算 * _X  
  
```  
inline float tanpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 Pi の正接値を返します * _X  
  
##  <a name="a-nametgammaa--tgamma-function"></a><a name="tgamma"></a>tgamma 関数  
 _X のガンマ関数を計算します。  
  
```  
inline float tgamma(float _X) restrict(amp);

 
inline double tgamma(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X のガンマ関数の結果を返します  
  
##  <a name="a-nametgammafa--tgammaf-function"></a><a name="tgammaf"></a>tgammaf 関数  
 _X のガンマ関数を計算します。  
  
```  
inline float tgammaf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X のガンマ関数の結果を返します  
  
##  <a name="a-nametrunca--trunc-function"></a><a name="trunc"></a>trunc 関数  
 引数を整数コンポーネントに切り捨てます。  
  
```  
inline float trunc(float _X) restrict(amp);

 
inline double trunc(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の整数部分を返します  
  
##  <a name="a-nametruncfa--truncf-function"></a><a name="truncf"></a>truncf 関数  
 引数を整数コンポーネントに切り捨てます。  
  
```  
inline float truncf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の整数部分を返します  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::precise_math Namespace](concurrency-precise-math-namespace.md)

