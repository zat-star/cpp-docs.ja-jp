---
title: "Concurrency::fast_math 名前空間 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_math/Concurrency::fast_math"
dev_langs: 
  - "C++"
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Concurrency::fast_math 名前空間
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`fast_math` 名前空間の関数は精度が低く、単精度 \(`float`\) のみをサポートし、DirectX の組み込み関数を呼び出します。  各関数には、2 種類のバージョン \(たとえば、`cos` と `cosf`\) があります。  どちらのバージョンも `float` を受け取り、返しますが、それぞれの DirectX の同じ組み込み関数を呼び出します。  
  
## 構文  
  
```  
namespace fast_math;  
```  
  
## メンバー  
  
### 関数  
  
|名前|説明|  
|--------|--------|  
|[cos 関数 \(fast\_math\)](../Topic/cos%20Function%20%20\(fast_math\).md)|引数の逆余弦を計算します。|  
|[cosf 関数 \(fast\_math\)](../Topic/cosf%20Function%20\(fast_math\).md)|引数の逆余弦を計算します。|  
|[asin 関数 \(fast\_math\)](../Topic/asin%20Function%20\(fast_math\).md)|引数の逆正弦を計算します。|  
|[asinf 関数 \(fast\_math\)](../Topic/asinf%20Function%20\(fast_math\).md)|引数の逆正弦を計算します。|  
|[atan 関数 \(fast\_math\)](../Topic/atan%20Function%20\(fast_math\).md)|引数の逆正接を計算します。|  
|[atan2 関数 \(fast\_math\)](../Topic/atan2%20Function%20\(fast_math\).md)|\_Y\/\_X の逆正接を計算します。|  
|[atan2f 関数 \(fast\_math\)](../Topic/atan2f%20Function%20\(fast_math\).md)|\_Y\/\_X の逆正接を計算します。|  
|[atanf 関数 \(fast\_math\)](../Topic/atanf%20Function%20\(fast_math\).md)|引数の逆正接を計算します。|  
|[ceil 関数 \(fast\_math\)](../Topic/ceil%20Function%20\(fast_math\).md)|引数の切り上げを計算します。|  
|[ceilf 関数 \(fast\_math\)](../Topic/ceilf%20Function%20\(fast_math\).md)|引数の切り上げを計算します。|  
|[cos 関数 \(fast\_math\)](../Topic/cos%20Function%20%20\(fast_math\).md)|引数の余弦を計算します。|  
|[cosf 関数 \(fast\_math\)](../Topic/cosf%20Function%20\(fast_math\).md)|引数の余弦を計算します。|  
|[cosh 関数 \(fast\_math\)](../Topic/cosh%20Function%20\(fast_math\).md)|引数の双曲線余弦の値を計算します。|  
|[coshf 関数 \(fast\_math\)](../Topic/coshf%20Function%20\(fast_math\).md)|引数の双曲線余弦の値を計算します。|  
|[exp 関数 \(fast\_math\)](../Topic/exp%20Function%20\(fast_math\).md)|e を底とする引数のべき乗を計算します。|  
|[exp2 関数 \(fast\_math\)](../Topic/exp2%20Function%20\(fast_math\).md)|2 を底とする引数のべき乗を計算します。|  
|[exp2f 関数 \(fast\_math\)](../Topic/exp2f%20Function%20\(fast_math\).md)|2 を底とする引数のべき乗を計算します。|  
|[expf 関数 \(fast\_math\)](../Topic/expf%20Function%20\(fast_math\).md)|e を底とする引数のべき乗を計算します。|  
|[fabs 関数 \(fast\_math\)](../Topic/fabs%20Function%20\(fast_math\).md)|引数の絶対値を返します。|  
|[fabsf 関数 \(fast\_math\)](../Topic/fabsf%20Function%20\(fast_math\).md)|引数の絶対値を返します。|  
|[floor 関数 \(fast\_math\)](../Topic/floor%20Function%20\(fast_math\).md)|引数の切り捨てを計算します。|  
|[floorf 関数 \(fast\_math\)](../Topic/floorf%20Function%20\(fast_math\).md)|引数の切り捨てを計算します。|  
|[fmax 関数 \(fast\_math\)](../Topic/fmax%20Function%20\(fast_math\).md)|引数の最大数値を判断します。|  
|[fmaxf 関数 \(fast\_math\)](../Topic/fmaxf%20Function%20\(fast_math\).md)|引数の最大数値を判断します。|  
|[fmin 関数 \(fast\_math\)](../Topic/fmin%20Function%20\(fast_math\).md)|引数の最小数値を判断します。|  
|[fminf 関数 \(fast\_math\)](../Topic/fminf%20Function%20\(fast_math\).md)|引数の最小数値を判断します。|  
|[fmod 関数 \(fast\_math\)](../Topic/fmod%20Function%20\(fast_math\).md)|\_X\/\_Y の浮動小数点の剰余を計算します。|  
|[fmodf 関数 \(fast\_math\)](../Topic/fmodf%20Function%20\(fast_math\).md)|\_X\/\_Y の浮動小数点の剰余を計算します。|  
|[frexp 関数 \(fast\_math\)](../Topic/frexp%20Function%20\(fast_math\).md)|\_X の仮数と指数を取得します。|  
|[frexpf 関数 \(fast\_math\)](../Topic/frexpf%20Function%20\(fast_math\).md)|\_X の仮数と指数を取得します。|  
|[isfinite 関数 \(fast\_math\)](../Topic/isfinite%20Function%20\(fast_math\).md)|引数に有限値が存在するかどうかを判断します。|  
|[isinf 関数 \(fast\_math\)](../Topic/isinf%20Function%20\(fast_math\).md)|引数が無限値であるかどうかを判断します。|  
|[isnan 関数 \(fast\_math\)](../Topic/isnan%20Function%20\(fast_math\).md)|引数が NaN であるかどうかを判断します。|  
|[ldexp 関数 \(fast\_math\)](../Topic/ldexp%20Function%20\(fast_math\).md)|仮数と指数から実数を計算します。|  
|[ldexpf 関数 \(fast\_math\)](../Topic/ldexpf%20Function%20\(fast_math\).md)|仮数と指数から実数を計算します。|  
|[log 関数 \(fast\_math\)](../Topic/log%20Function%20\(fast_math\).md)|e を底とする引数の対数を計算します。|  
|[log10 関数 \(fast\_math\)](../Topic/log10%20Function%20\(fast_math\).md)|10 を底とする引数の対数を計算します。|  
|[log10f 関数 \(fast\_math\)](../Topic/log10f%20Function%20\(fast_math\).md)|10 を底とする引数の対数を計算します。|  
|[log2 関数 \(fast\_math\)](../Topic/log2%20Function%20\(fast_math\).md)|2 を底とする引数の対数を計算します。|  
|[log2f 関数 \(fast\_math\)](../Topic/log2f%20Function%20\(fast_math\).md)|2 を底とする引数の対数を計算します。|  
|[logf 関数 \(fast\_math\)](../Topic/logf%20Function%20\(fast_math\).md)|e を底とする引数の対数を計算します。|  
|[modf 関数 \(fast\_math\)](../Topic/modf%20Function%20\(fast_math\).md)|\_X を小数部と整数部に分割します。|  
|[modff 関数 \(fast\_math\)](../Topic/modff%20Function%20\(fast_math\).md)|\_X を小数部と整数部に分割します。|  
|[pow 関数 \(fast\_math\)](../Topic/pow%20Function%20\(fast_math\).md)|\_X の \_Y 乗を計算します。|  
|[powf 関数 \(fast\_math\)](../Topic/powf%20Function%20\(fast_math\).md)|\_X の \_Y 乗を計算します。|  
|[round 関数 \(fast\_math\)](../Topic/round%20Function%20\(fast_math\).md)|\_X を最も近い整数値に丸めます。|  
|[roundf 関数 \(fast\_math\)](../Topic/roundf%20Function%20\(fast_math\).md)|\_X を最も近い整数値に丸めます。|  
|[rsqrt 関数 \(fast\_math\)](../Topic/rsqrt%20Function%20\(fast_math\).md)|引数の平方根の逆数を返します。|  
|[rsqrtf 関数 \(fast\_math\)](../Topic/rsqrtf%20Function%20\(fast_math\).md)|引数の平方根の逆数を返します。|  
|[signbit 関数 \(fast\_math\)](../Topic/signbit%20Function%20\(fast_math\).md)|引数の正弦を返します。|  
|[signbitf 関数 \(fast\_math\)](../Topic/signbitf%20Function%20\(fast_math\).md)|引数の正弦を返します。|  
|[sin 関数 \(fast\_math\)](../Topic/sin%20Function%20\(fast_math\).md)|引数の正弦値を計算します。|  
|[sincos 関数 \(fast\_math\)](../Topic/sincos%20Function%20\(fast_math\).md)|\_X の正弦と余弦の値を計算します|  
|[sincosf 関数 \(fast\_math\)](../Topic/sincosf%20Function%20\(fast_math\).md)|\_X の正弦と余弦の値を計算します|  
|[sinf 関数 \(fast\_math\)](../Topic/sinf%20Function%20\(fast_math\).md)|引数の正弦値を計算します。|  
|[sinh 関数 \(fast\_math\)](../Topic/sinh%20Function%20\(fast_math\).md)|引数の双曲線正弦の値を計算します。|  
|[sinhf 関数 \(fast\_math\)](../Topic/sinhf%20Function%20\(fast_math\).md)|引数の双曲線正弦の値を計算します。|  
|[sqrt 関数 \(fast\_math\)](../Topic/sqrt%20Function%20\(fast_math\).md)|引数の平方根を計算します。|  
|[sqrtf 関数 \(fast\_math\)](../Topic/sqrtf%20Function%20\(fast_math\).md)|引数の平方根を計算します。|  
|[tan 関数 \(fast\_math\)](../Topic/tan%20Function%20\(fast_math\).md)|引数の正接値を計算します。|  
|[tanf 関数 \(fast\_math\)](../Topic/tanf%20Function%20\(fast_math\).md)|引数の正接値を計算します。|  
|[tanh 関数 \(fast\_math\)](../Topic/tanh%20Function%20\(fast_math\).md)|引数の双曲線正接の値を計算します。|  
|[tanhf 関数 \(fast\_math\)](../Topic/tanhf%20Function%20\(fast_math\).md)|引数の双曲線正接の値を計算します。|  
|[trunc 関数 \(fast\_math\)](../Topic/trunc%20Function%20\(fast_math\).md)|引数を整数コンポーネントに切り捨てます。|  
|[truncf 関数 \(fast\_math\)](../Topic/truncf%20Function%20\(fast_math\).md)|引数を整数コンポーネントに切り捨てます。|  
  
## 必要条件  
 **ヘッダー:** amp\_math.h  
  
 **名前空間:** Concurrency::fast\_math  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)