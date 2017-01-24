---
title: "integral_constant クラス、bool_constant クラス | Microsoft Docs"
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
  - "std.tr1.integral_constant"
  - "integral_constant"
  - "std::tr1::integral_constant"
  - "std.integral_constant"
  - "std::integral_constant"
  - "type_traits/std::integral_constant"
  - "std.bool_constant"
  - "std::bool_constant"
  - "type_traits/std::bool_constant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "integral_constant クラス [TR1]"
  - "integral_constant"
  - "bool_constant"
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
caps.latest.revision: 23
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# integral_constant クラス、bool_constant クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型および値から整数定数を作成します。  
  
## 構文  
  
```  
template <class T, T v>  
    struct integral_constant {  
        static constexpr T value = v;  
        typedef T value_type;  
        typedef integral_constant<T, v> type;  
        constexpr operator value_type() const noexcept { return (value); }  
        constexpr value_type operator()() const noexcept { return (value); }  
    };  
  
template <bool v>  
    using bool_constant = integral_constant<bool, v>;  
  
```  
  
#### パラメーター  
 `T`  
 定数の型。  
  
 `v`  
 定数の値。  
  
## 解説  
 `integral_constant` テンプレート クラスは、整数型に特化された `T` および値 `v` 、その型の指定した値を整数型の定数を保持するオブジェクトを表します。 という名前のメンバー `type` 生成済みテンプレートの特殊化型のエイリアスは、および `value` メンバーの値を保持する `v` 特殊化を作成するために使用します。  
  
 `bool_constant` テンプレート クラスの明示的な部分的特殊化は、 `integral_constant` を使用する `bool` として、 `T` 引数。  
  
## 使用例  
  
```cpp  
// std__type_traits__integral_constant.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "integral_constant<int, 5> == "   
        << std::integral_constant<int, 5>::value << std::endl;   
    std::cout << "integral_constant<bool, false> == " << std::boolalpha   
        << std::integral_constant<bool, false>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
integral_constant < int, 5 > 5 integral_constant < bool false > = = false = =  
```  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [false\_type Typedef](../Topic/false_type%20Typedef.md)   
 [true\_type Typedef](../Topic/true_type%20Typedef.md)