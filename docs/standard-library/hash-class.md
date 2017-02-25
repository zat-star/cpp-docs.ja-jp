---
title: "hash クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.hash"
  - "xfunctional/std::hash"
  - "hash"
  - "typeindex/std::hash"
  - "std::hash"
  - "std.tr1.hash"
  - "std::tr1::hash"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash クラス"
  - "hash クラス [TR1]"
ms.assetid: e1b500c6-a5c8-4f6f-ad33-7ec52eb8e2e4
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# hash クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値のハッシュ コードを計算します。  
  
## 構文  
  
```  
template<class Ty>  
    struct hash  
        : public unary_function<Ty, size_t> {  
    size_t operator()(Ty _Val) const;  
    };  
```  
  
## 解説  
 このメンバー関数は、ハッシュ関数を定義します。型 `Ty` の値をインデックス値の分布にマッピングするのに適しています。  このメンバー演算子は、`_Val` のハッシュ コードを返します。`unordered_map`、`unordered_multimap`、`unordered_set`、および `unordered_multiset` の各テンプレート クラスでの使用に適しています。  `Ty` には、`string`、`wstring`、`error_code`、`error_condition`、`u16string`、または `u32string` の任意のスカラー型を指定できます。  
  
## 使用例  
  
```  
// std_tr1__functional__hash.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
#include <unordered_set>   
  
int main()   
    {   
    std::unordered_set<int, std::hash<int> > c0;   
    c0.insert(3);   
    std::cout << *c0.find(3) << std::endl;   
  
    return (0);   
    }  
  
```  
  
 **3**   
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [unordered\_multimap クラス](../standard-library/unordered-multimap-class.md)   
 [unordered\_multiset クラス](../standard-library/unordered-multiset-class.md)   
 [\<unordered\_set\>](../standard-library/unordered-set.md)