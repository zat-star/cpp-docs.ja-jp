---
title: "is_member_pointer クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::is_member_pointer"
  - "is_member_pointer"
  - "std.tr1.is_member_pointer"
  - "std.is_member_pointer"
  - "std::is_member_pointer"
  - "type_traits/std::is_member_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_member_pointer クラス [TR1]"
  - "is_member_pointer"
ms.assetid: da07ff4e-9ee0-4baa-ad93-1741f10913d1
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_member_pointer クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型がメンバーへのポインターであるかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_member_pointer;  
```  
  
#### パラメーター  
 `Ty`  
 問い合わせる型。  
  
## 解説  
 型 `Ty` がメンバー関数へのポインター、メンバー オブジェクトへのポインター、または、そのいずれかの `cv-qualified` 形式である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
## 使用例  
  
```  
// std_tr1__type_traits__is_member_pointer.cpp   
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
    std::cout << "is_member_pointer<trivial *> == "   
        << std::boolalpha   
        << std::is_member_pointer<trivial *>::value   
        << std::endl;   
    std::cout << "is_member_pointer<int trivial::*> == "   
        << std::boolalpha   
        << std::is_member_pointer<int trivial::*>::value   
        << std::endl;   
    std::cout << "is_member_pointer<int (functional::*)()> == "   
        << std::boolalpha   
        << std::is_member_pointer<int (functional::*)()>::value   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_member\_pointertrivial\<\*\> は \=\=**  
**true\<is\_member\_pointerint の trivial::\*\> \=\=**  
**true is\_member\_pointerint\< \(functional::\*\) \(\) \> \=\=**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_member\_function\_pointer クラス](../Topic/is_member_function_pointer%20Class.md)   
 [is\_member\_object\_pointer クラス](../standard-library/is-member-object-pointer-class.md)   
 [is\_pointer クラス](../standard-library/is-pointer-class.md)