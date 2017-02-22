---
title: "remove_cv クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "remove_cv"
  - "std::tr1::remove_cv"
  - "std.tr1.remove_cv"
  - "std.remove_cv"
  - "std::remove_cv"
  - "type_traits/std::remove_cv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_cv クラス [TR1]"
  - "remove_cv"
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# remove_cv クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型から非 const\/volatile 型を作成します。  
  
## 構文  
  
```  
template<class T>  
    struct remove_cv;  
  
template<class T>  
  using remove_cv_t = typename remove_cv<T>::type;  
```  
  
#### パラメーター  
 `T`  
 変更する型。  
  
## 解説  
 `remove_cv<T>` のインスタンスは、`T` の形式が `const T1`、`volatile T1`、または `const volatile T1` である場合は、修飾型 `T1` を保持します。それ以外の場合は、`T` を保持します。  
  
## 使用例  
  
```  
  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_cv_t<const volatile int> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_cv_t<const volatile int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **remove\_cv\_t\<const volatile int\> \=\= int**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_const クラス](../standard-library/remove-const-class.md)   
 [remove\_volatile クラス](../Topic/remove_volatile%20Class.md)