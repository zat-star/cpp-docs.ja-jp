---
title: "is_convertible クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_convertible"
  - "std.tr1.is_convertible"
  - "std::tr1::is_convertible"
  - "std.is_convertible"
  - "std::is_convertible"
  - "type_traits/std::is_convertible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_convertible クラス [TR1]"
  - "is_convertible"
ms.assetid: 75614008-1894-42ea-bd57-974399628536
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_convertible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

一方の型をもう一方の型に変換できるかどうかをテストします。  
  
## 構文  
  
```  
template<class From, class To>  
    struct is_convertible;  
```  
  
#### パラメーター  
 `From`  
 変換前の型。  
  
 `Ty`  
 変換後の型。  
  
## 解説  
 `To to = from;` という式が正しい形式である場合、型述語のインスタンスは true を保持します \(`from` は型 `From` のオブジェクト\)。  
  
## 使用例  
  
```  
// std_tr1__type_traits__is_convertible.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha   
        << std::is_convertible<trivial, int>::value << std::endl;   
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha   
        << std::is_convertible<trivial, trivial>::value << std::endl;   
    std::cout << "is_convertible<char, int> == " << std::boolalpha   
        << std::is_convertible<char, int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_convertible\<trivial, int\> \=\= false**  
**is\_convertible\<trivial, trivial\> \=\= true**  
**is\_convertible\<char, int\> \=\= true**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_base\_of クラス](../standard-library/is-base-of-class.md)