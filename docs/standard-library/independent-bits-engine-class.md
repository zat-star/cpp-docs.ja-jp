---
title: "independent_bits_engine クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.independent_bits_engine"
  - "std::tr1::independent_bits_engine"
  - "tr1::independent_bits_engine"
  - "tr1.independent_bits_engine"
  - "independent_bits_engine"
  - "random/std::tr1::independent_bits_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "independent_bits_engine クラス"
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# independent_bits_engine クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ベースのエンジンから返された値のビットを再パックすることで、指定したビット数で数値のランダム シーケンスを生成します。  
  
## 構文  
  
```  
template<class Engine, size_t W, class UIntType> class independent_bits_engine;  
```  
  
#### パラメーター  
 `Engine`  
 ベースのエンジンの型。  
  
 `W`  
 **ワード サイズ**。  生成される各数値のサイズ \(ビット数\)。  **前提条件**: `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `UIntType`  
 結果を表す符号なし整数型。  使用可能な型については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
## メンバー  
  
||||  
|-|-|-|  
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|  
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|  
  
 エンジンのメンバーの詳細については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
## 解説  
 このテンプレート クラスは、ベースのエンジンから返された値のビットを再パックして `W` ビットの値にすることで値を生成する*エンジン アダプター*を表します。  
  
## 必要条件  
 **ヘッダー:** \<random\>  
  
 **名前空間:** std  
  
## 参照  
 [\<random\>](../standard-library/random.md)