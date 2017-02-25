---
title: "extent クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.extent"
  - "extent"
  - "std::tr1::extent"
  - "std.extent"
  - "std::extent"
  - "type_traits/std::extent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extent クラス [TR1]"
  - "extent"
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# extent クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

配列の次元を取得します。  
  
## 構文  
  
```  
template<class Ty, unsigned I = 0>  
    struct extent;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
 `I`  
 照会する配列の範囲。  
  
## 解説  
 `Ty` が少なくとも `I` 次元の配列型である場合、この型クエリは `I` で指定される次元の要素数を保持します。  `Ty` が配列型ではないか、配列のランク \(次元数\) が `I` 未満である場合、または `I` がゼロで `Ty` の型が "`U` の不明な範囲の配列" である場合、この型クエリは 0 を保持します。  
  
## 使用例  
  
```  
// std_tr1__type_traits__extent.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "extent 0 == "   
        << std::extent<int[5][10]>::value << std::endl;   
    std::cout << "extent 1 == "   
        << std::extent<int[5][10], 1>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **範囲 0 \=\= 5**  
**範囲 1 \=\= 10**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_all\_extents クラス](../standard-library/remove-all-extents-class.md)   
 [remove\_extent クラス](../standard-library/remove-extent-class.md)