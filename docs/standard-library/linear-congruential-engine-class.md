---
title: "linear_congruential_engine クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.linear_congruential_engine"
  - "random/std::tr1::linear_congruential_engine"
  - "linear_congruential_engine"
  - "std::tr1::linear_congruential_engine"
  - "tr1.linear_congruential_engine"
  - "tr1::linear_congruential_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "linear_congruential_engine クラス"
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# linear_congruential_engine クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

線形合同法アルゴリズムでランダム シーケンスを生成します。  
  
## 構文  
  
```  
template<class UIntType, UIntType A, UIntType C, UIntType M>  
class linear_congruential_engine{  
public:  
    // types  
    typedef UIntType result_type;  
  
    // engine characteristics  
    static constexpr result_type multiplier = a;  
    static constexpr result_type increment = c;  
    static constexpr result_type modulus = m;  
    static constexpr result_type min() { return c == 0u ? 1u: 0u; }  
    static constexpr result_type max() { return m - 1u; }  
    static constexpr result_type default_seed = 1u;  
  
    // constructors and seeding functions  
    explicit linear_congruential_engine(result_type s = default_seed);  
    template<class Sseq> explicit linear_congruential_engine(Sseq& q);  
    void seed(result_type s = default_seed);  
    template<class Sseq> void seed(Sseq& q);  
  
    // generating functions  
    result_type operator()();  
    void discard(unsigned long long z);  
};  
```  
  
#### パラメーター  
 `UIntType`  
 結果を表す符号なし整数型。 使用可能な型を参照してください。 [\<random\>](../standard-library/random.md)します。  
  
 `A`  
 **乗算**。**前提条件**: 「解説」を参照してください。  
  
 `C`  
 **インクリメント**。**前提条件**: 「解説」を参照してください。  
  
 `M`  
 **剰余**。**前提条件**: 「解説」を参照してください。  
  
## メンバー  
  
||||  
|-|-|-|  
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|  
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|  
  
 `default_seed` は、`1u` として定義されているメンバー定数で、`linear_congruential_engine::seed` および単一値コンストラクターの既定のパラメーター値として使用されます。  
  
 エンジンのメンバーの詳細については、次を参照してください。 [\<random\>](../standard-library/random.md)します。  
  
## 解説  
 `linear_congruential_engine` テンプレート クラスは、最も単純なジェネレーター エンジンですが、速度や品質は最高というわけではありません。 このエンジンを改良したものが [substract\_with\_carry\_engine](../Topic/subtract_with_carry_engine%20Class.md) です。 これらのエンジンはいずれも、[mersenne\_twister\_engine](../standard-library/mersenne-twister-engine-class.md) ほど高速ではなく、結果も高品質ではありません。  
  
 このエンジンは、漸化式 \(*周期*\) `x(i) = (A * x(i-1) + C) mod M` を使用して、ユーザー指定の符号なし整数型の値を生成します。  
  
 `M` が 0 の場合、この剰余演算に使用される値は `numeric_limits<result_type>::max() + 1` です。 エンジンの状態は、最後に返された値か、または `operator()` に対して呼び出しが行われなかった場合はシード値になります。  
  
 `M` が 0 以外の場合、テンプレート引数 `A` と `C` の値は `M` 未満である必要があります。  
  
 このエンジンから generator を直接構築できますは、これらの定義済みの typedef のいずれかとして使用できます。  
  
 `minstd_rand0`: 1988年最小標準エンジン \(ルイス、グッドマン、ミラー、1969 年\)。  
  
```  
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;  
```  
  
 `minstd_rand`: 更新済みの最小標準エンジン `minstd_rand0` \(パーク、ミラー、ストックマイヤー、1993 年\)。  
  
```  
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;  
```  
  
 線形合同法エンジン アルゴリズムの詳細については、Wikipedia の記事を参照してください。 [線形合同法](http://go.microsoft.com/fwlink/?LinkId=402446)します。  
  
## 必要条件  
 **ヘッダー:** \<random\>  
  
 **名前空間:** std  
  
## 参照  
 [\<random\>](../standard-library/random.md)