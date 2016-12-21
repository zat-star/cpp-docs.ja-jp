---
title: "is_void クラス | Microsoft Docs"
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
  - "is_void"
  - "std.tr1.is_void"
  - "std::tr1::is_void"
  - "std.is_void"
  - "std::is_void"
  - "type_traits/std::is_void"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_void クラス [TR1]"
  - "is_void"
ms.assetid: 99b0de3b-1b38-4949-b053-080e5363174e
caps.latest.revision: 21
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_void クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が void であるかどうかをテストします。  
  
## 構文  
  
```  
template<class T>  
    struct is_void;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
## 解説  
 型 `T` が `void` か `void` の cv\-qualified 形式である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
## 使用例  
  
```cpp  
// std__type_traits__is_void.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_void<trivial> == " << std::boolalpha   
        << std::is_void<trivial>::value << std::endl;   
    std::cout << "is_void<void()> == " << std::boolalpha   
        << std::is_void<void()>::value << std::endl;   
    std::cout << "is_void<void> == " << std::boolalpha   
        << std::is_void<void>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_void<trivial> == false is_void<void()> == false is_void<void> == true  
```  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)