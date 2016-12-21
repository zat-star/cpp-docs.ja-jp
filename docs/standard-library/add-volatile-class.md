---
title: "add_volatile クラス | Microsoft Docs"
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
  - "std::tr1::add_volatile"
  - "add_volatile"
  - "std.tr1.add_volatile"
  - "std.add_volatile"
  - "std::add_volatile"
  - "type_traits/std::add_volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_volatile クラス [TR1]"
  - "add_volatile"
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
caps.latest.revision: 21
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# add_volatile クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した型から volatile 型を作成します。  
  
## 構文  
  
```  
template<class Ty>  
    struct add_volatile;  
  
template<class T>  
using add_volatile_t = typename add_volatile<T>::type;  
```  
  
#### パラメーター  
 `Ty`  
 変更する型。  
  
## 解説  
 この型修飾子のインスタンスは、`Ty` が参照、関数、または volatile で修飾された型である場合は、修飾型 `Ty` を保持します。それ以外の場合は、`volatile Ty` を保持します。  
  
## 使用例  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_volatile_t<int> *p = (volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_volatile<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_volatile\<int\> \=\= int**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_volatile クラス](../Topic/remove_volatile%20Class.md)