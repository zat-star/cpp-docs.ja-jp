---
title: "is_volatile クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::is_volatile"
  - "std.tr1.is_volatile"
  - "is_volatile"
  - "std.is_volatile"
  - "std::is_volatile"
  - "type_traits/std::is_volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_volatile クラス [TR1]"
  - "is_volatile"
ms.assetid: 54922e8a-db4e-4cae-8931-b3352f0b8d3b
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_volatile クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が volatile かどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_volatile;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 `Ty` が `volatile-qualified` の場合、型述語のインスタンスは true を保持します。  
  
## 使用例  
  
```  
// std_tr1__type_traits__is_volatile.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_volatile<trivial> == " << std::boolalpha   
        << std::is_volatile<trivial>::value << std::endl;   
    std::cout << "is_volatile<volatile trivial> == " << std::boolalpha   
        << std::is_volatile<volatile trivial>::value << std::endl;   
    std::cout << "is_volatile<int> == " << std::boolalpha   
        << std::is_volatile<int>::value << std::endl;   
    std::cout << "is_volatile<volatile int> == " << std::boolalpha   
        << std::is_volatile<volatile int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_volatile\<trivial\> \=\= false**  
**is\_volatile\<volatile trivial\> \=\= true**  
**is\_volatile\<int\> \=\= false**  
**is\_volatile\<volatile int\> \=\= true**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_const クラス](../Topic/is_const%20Class.md)