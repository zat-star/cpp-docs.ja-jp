---
title: "common_type クラス | Microsoft Docs"
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
  - "std.tr1.common_type"
  - "common_type"
  - "std::tr1::common_type"
  - "std.common_type"
  - "std::common_type"
  - "type_traits/std::common_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "common_type クラス [TR1]"
  - "common_type"
ms.assetid: 02bc4e7b-c63d-49de-9f8a-511d3a5c1e7f
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# common_type クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

1 つ以上の型の共通型を決定します。  
  
## 構文  
  
```  
  
template <class... T>  
   struct common_type;  
  
template <class T>  
   struct common_type<T> {  
      typedef typename decay<T>::type type;  
};  
  
template <class T, class U>  
   struct common_type<T, U> {  
      typedef typename decay<decltype(true ?  declval<T>() :  
         declval<U>())>::type type;  
};  
  
template <class T, class U, class... V>  
   struct common_type<T, U, V...> {  
      typedef typename common_type<typename common_type<T, U>::type, V...>::type type;  
};  
```  
  
#### パラメーター  
 [完全型](../Topic/Incomplete%20Types.md)または void である型のリスト。  
  
## 解説  
 `type` のメンバーは、パラメーター リストのすべての型をその型に変換できる共通型です。  
  
## 例  
 次のプログラムは、適切な用法のシナリオと結果のテストを示します。  
  
```cpp  
// Compile using cl.exe /EHsc  
// common_type sample  
#include <iostream>  
#include <type_traits>  
  
struct Base {};  
struct Derived : Base {};  
  
int main()   
{  
    typedef std::common_type<unsigned char, short, int>::type NumericType;  
    typedef std::common_type<float, double>::type FloatType;  
    typedef std::common_type<const int, volatile int>::type ModifiedIntType;  
    typedef std::common_type<Base, Derived>::type ClassType;  
  
    std::cout << std::boolalpha;  
    std::cout << "Test for typedefs of common_type int" << std::endl;  
    std::cout << "NumericType: "     << std::is_same<int, NumericType>::value << std::endl;  
    std::cout << "FloatType: "       << std::is_same<int, FloatType>::value << std::endl;  
    std::cout << "ModifiedIntType: " << std::is_same<int, ModifiedIntType>::value << std::endl;  
    std::cout << "ClassType: "       << std::is_same<int, ClassType>::value << std::endl;  
    std::cout << "---------------------------" << std::endl;  
    std::cout << "Test for typedefs of common_type double" << std::endl;  
    std::cout << "NumericType: "     << std::is_same<double, NumericType>::value << std::endl;  
    std::cout << "FloatType: "       << std::is_same<double, FloatType>::value << std::endl;  
    std::cout << "ModifiedIntType: " << std::is_same<double, ModifiedIntType>::value << std::endl;  
    std::cout << "ClassType: "       << std::is_same<double, ClassType>::value << std::endl;  
    std::cout << "---------------------------" << std::endl;  
    std::cout << "Test for typedefs of common_type Base" << std::endl;  
    std::cout << "NumericType: "     << std::is_same<Base, NumericType>::value << std::endl;  
    std::cout << "FloatType: "       << std::is_same<Base, FloatType>::value << std::endl;  
    std::cout << "ModifiedIntType: " << std::is_same<Base, ModifiedIntType>::value << std::endl;  
    std::cout << "ClassType: "       << std::is_same<Base, ClassType>::value << std::endl;  
  
    return 0;  
}  
```  
  
## 出力  
  
```  
Test for typedefs of common_type int  
NumericType: true  
FloatType: false  
ModifiedIntType: true  
ClassType: false  
---------------------------  
Test for typedefs of common_type double  
NumericType: false  
FloatType: true  
ModifiedIntType: false  
ClassType: false  
---------------------------  
Test for typedefs of common_type Base  
NumericType: false  
FloatType: false  
ModifiedIntType: false  
ClassType: true  
  
```  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)