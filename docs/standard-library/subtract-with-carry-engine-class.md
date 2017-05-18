---
title: "subtract_with_carry_engine クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- subtract_with_carry_engine
- random/std::subtract_with_carry_engine
- random/std::subtract_with_carry_engine::default_seed
- random/std::subtract_with_carry_engine::discard
- random/std::subtract_with_carry_engine::min
- random/std::subtract_with_carry_engine::max
- random/std::subtract_with_carry_engine::seed
dev_langs:
- C++
helpviewer_keywords:
- subtract_with_carry_engine class
ms.assetid: 94a055f2-a620-4a22-ac34-c156924bab31
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 3bfa6cd48bad52958dbc0f9563e46f11bf516d39
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="subtractwithcarryengine-class"></a>subtract_with_carry_engine クラス
キャリー付き減算 (ラグ付きフィボナッチ法) アルゴリズムでランダム シーケンスを生成します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class UIntType, size_t W, size_t S, size_t R>  
class subtract_with_carry_engine;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `UIntType`  
 結果を表す符号なし整数型。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。  
  
 `W`  
 **ワード サイズ**。 状態シーケンスの各ワードのサイズ (ビット数)。 **前提条件**: `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `S`  
 **短いラグ**。 整数値の数。 **前提条件**: `0 < S < R`  
  
 `R`  
 **長いラグ**。 生成される数列の中の繰り返しを決定します。  
  
## <a name="members"></a>メンバー  
  
||||  
|-|-|-|  
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|  
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|  
|`default_seed` は、`19780503u` として定義されているメンバー定数で、`subtract_with_carry_engine::seed` および単一値コンストラクターの既定のパラメーター値として使用されます。|||  
  
 エンジンのメンバーの詳細については、[\<random>](../standard-library/random.md) をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `substract_with_carry_engine` テンプレート クラスは、[linear_congruential_engine](../standard-library/linear-congruential-engine-class.md) を改良したものです。 これらのエンジンはいずれも、[mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md) ほど高速ではなく、結果も高品質ではありません。  
  
 このエンジンは、漸化式 (*周期*) `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M` を使用して、ユーザー指定の符号なし整数型の値を生成します。ここで、`x(i - S) - x(i - R) - cy(i - 1) < 0` の場合 `cy(i)` は値 `1` を、そうでない場合は `0` を持ち、`M` は値 `2`<sup>W</sup> を持ちます。エンジンの状態は、キャリー インジケーター + `R` の値になります。 `R` が `operator()` 回以上呼び出された場合、これらの値は最後の `R` の値で構成され、それ以外の場合は、返された `N` の値とシードの最後の `R - N` の値で構成されます。  
  
 テンプレート引数 `UIntType` には、最大 `M - 1` の値を保持するのに十分な大きさが必要です。  
  
 このエンジンから直接ジェネレーターを構築できますが、定義済みの typedef のいずれかを使用することもできます。  
  
 `ranlux24_base`: `ranlux24` のベースとして使用されます。                   
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`  
  
 `ranlux48_base`: `ranlux48` のベースとして使用されます。                   
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`  
  
 キャリー付き減算エンジンのアルゴリズムの詳細については、Wikipedia の記事「[Lagged Fibonacci generator](http://go.microsoft.com/fwlink/LinkId=402445)」(Lagged Fibonacci 法) を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<random>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [\<random>](../standard-library/random.md)


