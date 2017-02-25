---
title: "is_enum クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_enum"
  - "std.tr1.is_enum"
  - "std::tr1::is_enum"
  - "std.is_enum"
  - "std::is_enum"
  - "type_traits/std::is_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_enum クラス [TR1]"
  - "is_enum"
ms.assetid: df3b00b7-4f98-4b3a-96ce-10ad958ee69c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_enum クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が列挙型であるかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_enum;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` が列挙型または列挙型の `cv-qualified` 形式である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
## 使用例  
  
```  
// std_tr1__type_traits__is_enum.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
enum color {   
    red, greed, blue};   
  
int main()   
    {   
    std::cout << "is_enum<trivial> == " << std::boolalpha   
        << std::is_enum<trivial>::value << std::endl;   
    std::cout << "is_enum<color> == " << std::boolalpha   
        << std::is_enum<color>::value << std::endl;   
    std::cout << "is_enum<int> == " << std::boolalpha   
        << std::is_enum<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_enum\<trivial\> \=\= false**  
**is\_enum\<color\> \=\= true**  
**is\_enum\<int\> \=\= false**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_integral クラス](../standard-library/is-integral-class.md)