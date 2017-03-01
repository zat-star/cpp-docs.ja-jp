---
title: "Concurrency::fast_math 名前空間関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4a01f48a7d087281ab1e9222d1077e92ab8b0d6c
ms.openlocfilehash: 0545a57c492f5c1872c71c04c99b54f86b644102
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyfastmath-namespace-functions"></a>Concurrency::fast_math 名前空間の関数
||||  
|-|-|-|  
|[acos 関数](#acos)|[acosf 関数](#acosf)|[asin 関数](#asin)|  
|[asinf 関数](#asinf)|[atan 関数](#atan)|[atan2 関数](#atan2)|  
|[atan2f 関数](#atan2f)|[atanf 関数](#atanf)|[ceil 関数](#ceil)|  
|[ceilf 関数](#ceilf)|[cos 関数](#cos)|[cosf 関数](#cosf)|  
|[cosh 関数](#cosh)|[coshf 関数](#coshf)|[exp 関数](#exp)|  
|[exp2 関数](#exp2)|[exp2f 関数](#exp2f)|[expf 関数](#expf)|  
|[fabs 関数](#fabs)|[fabsf 関数](#fabsf)|[floor 関数](#floor)|  
|[floorf 関数](#floorf)|[fmax 関数](#fmax)|[fmaxf 関数](#fmaxf)|  
|[fmin 関数](#fmin)|[fminf 関数](#fminf)|[fmod 関数](#fmod)|  
|[fmodf 関数](#fmodf)|[frexp 関数](#frexp)|[frexpf 関数](#frexpf)|  
|[isfinite 関数](#isfinite)|[isinf 関数](#isinf)|[isnan 関数](#isnan)|  
|[ldexp 関数](#ldexp)|[ldexpf 関数](#ldexpf)|[log 関数](#log)|  
|[log10 関数](#log10)|[log10f 関数](#log10f)|[log2 関数](#log2)|  
|[log2f 関数](#log2f)|[logf 関数](#logf)|[modf 関数](#modf)|  
|[modff 関数](#modff)|[pow 関数します。](#pow)|[powf 関数](#powf)|  
|[round 関数](#round)|[roundf 関数](#roundf)|[rsqrt 関数](#rsqrt)|  
|[rsqrtf 関数](#rsqrtf)|[signbit 関数](#signbit)|[signbitf 関数](#signbitf)|  
|[sin 関数](#sin)|[sincos 関数](#sincos)|[sincosf 関数](#sincosf)|  
|[sinf 関数](#sinf)|[sinh 関数](#sinh)|[sinhf 関数](#sinhf)|  
|[sqrt 関数](#sqrt)|[sqrtf 関数](#sqrtf)|[tan 関数](#tan)|  
|[tanf 関数](#tanf)|[tanh 関数](#tanh)|[tanhf 関数](#tanhf)|  
|[trunc 関数](#trunc)|[truncf 関数](#truncf)|  
  
##  <a name="a-nameacosa--acos-function"></a><a name="acos"></a>acos 関数  
 引数の逆余弦を計算します。  
  
```  
inline float acos(float _X) restrict(amp);
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
  
##  <a name="a-nameasina--asin-function"></a><a name="asin"></a>asin 関数  
 引数の逆正弦を計算します。  
  
```  
inline float asin(float _X) restrict(amp);
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
  
##  <a name="a-nameatana--atan-function"></a><a name="atan"></a>atan 関数  
 引数の逆正接を計算します。  
  
```  
inline float atan(float _X) restrict(amp);
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
  
##  <a name="a-nameceila--ceil-function"></a><a name="ceil"></a>ceil 関数  
 引数の切り上げを計算します。  
  
```  
inline float ceil(float _X) restrict(amp);
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
  
##  <a name="a-namecosa--cos-function"></a><a name="cos"></a>cos 関数   
 引数の余弦を計算します。  
  
```  
inline float cos(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線余弦の値を返します  
  
##  <a name="a-nameexpa--exp-function"></a><a name="exp"></a>exp 関数  
 e を底とする引数のべき乗を計算します。  
  
```  
inline float exp(float _X) restrict(amp);
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
  
##  <a name="a-namefabsa--fabs-function"></a><a name="fabs"></a>fabs 関数  
 引数の絶対値を返します。  
  
```  
inline float fabs(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 整数値  
  
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
  
##  <a name="a-namefloora--floor-function"></a><a name="floor"></a>floor 関数  
 引数の切り捨てを計算します。  
  
```  
inline float floor(float _X) restrict(amp);
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
  
##  <a name="a-namefmaxa--fmax-function"></a><a name="fmax"></a>fmax 関数  
 引数の最大数値を判断します。  
  
```  
inline float max(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 整数値  
  
 `_Y`  
 整数値  
  
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
inline float min(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 整数値  
  
 `_Y`  
 整数値  
  
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
  
##  <a name="a-namefmoda--fmod-function"></a><a name="fmod"></a>fmod 関数  
 _X/_Y の浮動小数点の剰余を計算します。  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X/_Y の浮動小数点の剰余を返します  
  
##  <a name="a-namefmodfa--fmodf-function"></a><a name="fmodf"></a>fmodf 関数  
 _X/_Y の浮動小数点の剰余を計算します。  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X/_Y の浮動小数点の剰余を返します  
  
##  <a name="a-namefrexpa--frexp-function"></a><a name="frexp"></a>frexp 関数  
 _X の仮数と指数を取得します。  
  
```  
inline float frexp(
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
  
##  <a name="a-nameisfinitea--isfinite-function"></a><a name="isfinite"></a>isfinite 関数  
 引数に有限値が存在するかどうかを判断します。  
  
```  
inline int isfinite(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数が NaN 値を持つ場合にのみ、0 以外の値を返します  
  
##  <a name="a-nameldexpa--ldexp-function"></a><a name="ldexp"></a>ldexp 関数  
 仮数と指数から実数を計算します。  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値、mentissa  
  
 `_Exp`  
 整数の指数  
  
### <a name="return-value"></a>戻り値  
 _X * 2^_Exp を返します  
  
##  <a name="a-nameldexpfa--ldexpf-function"></a><a name="ldexpf"></a>ldexpf 関数  
 仮数と指数から実数を計算します。  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値、mentissa  
  
 `_Exp`  
 整数の指数  
  
### <a name="return-value"></a>戻り値  
 _X * 2^_Exp を返します  
  
##  <a name="a-nameloga--log-function"></a><a name="log"></a>log 関数  
 e を底とする引数の対数を計算します。  
  
```  
inline float log(float _X) restrict(amp);
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
  
##  <a name="a-namelog2a--log2-function"></a><a name="log2"></a>log2 関数  
 2 を底とする引数の対数を計算します。  
  
```  
inline float log2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の基本&2; の対数を返します  
  
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
 _X を小数部と整数部に分割します。  
  
```  
inline float modf(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Ip`  
  
### <a name="return-value"></a>戻り値  
 _X の符号付き小数部を返します  
  
##  <a name="a-namemodffa--modff-function"></a><a name="modff"></a>modff 関数  
 _X を小数部と整数部に分割します。  
  
```  
inline float modff(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Ip`  
  
### <a name="return-value"></a>戻り値  
 _X の符号付き小数部を返します  
  
##  <a name="a-namepowa--pow-function"></a><a name="pow"></a>pow 関数します。  
 _X の _Y 乗を計算します。  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 基本浮動小数点の値  
  
 `_Y`  
 浮動小数点値、指数  
  
### <a name="return-value"></a>戻り値  
 _X の _Y 乗の値を返します  
  
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
  
##  <a name="a-namerounda--round-function"></a><a name="round"></a>round 関数  
 _X を最も近い整数値に丸めます。  
  
```  
inline float round(float _X) restrict(amp);
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
  
##  <a name="a-namesignbita--signbit-function"></a><a name="signbit"></a>signbit 関数  
 _X の符号が負の値であるかどうかを決定します。  
  
```  
inline int signbit(float _X) restrict(amp);
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
    float* _S,  
    float* _C) restrict(amp);
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
    float* _S,  
    float* _C) restrict(amp);
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
  
##  <a name="a-namesqrta--sqrt-function"></a><a name="sqrt"></a>sqrt 関数  
 引数の squre ルートを計算します。  
  
```  
inline float sqrt(float _X) restrict(amp);
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
  
##  <a name="a-nametrunca--trunc-function"></a><a name="trunc"></a>trunc 関数  
 引数を整数コンポーネントに切り捨てます。  
  
```  
inline float trunc(float _X) restrict(amp);
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
 [Concurrency::fast_math Namespace](concurrency-fast-math-namespace.md)

