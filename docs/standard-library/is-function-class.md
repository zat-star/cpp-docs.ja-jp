---
title: "is_function クラス | Microsoft Docs"
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
  - "std::tr1::is_function"
  - "std.tr1.is_function"
  - "is_function"
  - "std.is_function"
  - "std::is_function"
  - "type_traits/std::is_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_function クラス [TR1]"
  - "is_function"
ms.assetid: e5c0dbcd-829b-415f-853f-8c5be47c5040
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_function クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が関数型であるかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_function;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` が関数型である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
## 使用例  
  
```  
// std_tr1__type_traits__is_function.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_function<trivial> == " << std::boolalpha   
        << std::is_function<trivial>::value << std::endl;   
    std::cout << "is_function<functional> == " << std::boolalpha   
        << std::is_function<functional>::value << std::endl;   
    std::cout << "is_function<float()> == " << std::boolalpha   
        << std::is_function<float()>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_function\<trivial\> \=\= false**  
**is\_function\<functional\> \=\= false**  
**is\_function\<float\(\)\> \=\= true**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_object クラス](../standard-library/is-object-class.md)