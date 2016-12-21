---
title: "remove_reference クラス | Microsoft Docs"
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
  - "std.tr1.remove_reference"
  - "std::tr1::remove_reference"
  - "remove_reference"
  - "std.remove_reference"
  - "std::remove_reference"
  - "type_traits/std::remove_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_reference クラス [TR1]"
  - "remove_reference"
ms.assetid: 294e1965-3ae3-46ee-bc42-4fdf60c24717
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remove_reference クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型から非参照型を作成します。  
  
## 構文  
  
```  
template<class T>  
    struct remove_reference;  
  
template<class T>  using remove_reference_t = typename remove_reference<T>::type;  
```  
  
#### パラメーター  
 `T`  
 変更する型。  
  
## 解説  
 `remove_reference<T>` のインスタンスは、`T1` の形式が `T` である場合は、修飾型 `T1&` を保持します。それ以外の場合は、`T` を保持します。  
  
## 使用例  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_reference_t<int&> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_reference_t<int&> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
remove_reference_t<int&> == int  
```  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_lvalue\_reference クラス](../standard-library/add-lvalue-reference-class.md)