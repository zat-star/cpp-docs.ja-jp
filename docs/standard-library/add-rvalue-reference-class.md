---
title: "add_rvalue_reference クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "type_traits/std::add_rvalue_reference"
  - "std::add_rvalue_reference"
  - "add_rvalue_reference"
  - "std.add_rvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_rvalue_reference クラス"
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# add_rvalue_reference クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクトまたは関数の型の場合は、テンプレート パラメーターの右辺値参照型を作成します。 それ以外の場合、参照縮小のセマンティクスのため、型は、テンプレート パラメーターと同じです。  
  
## 構文  
  
```cpp  
template<class T>  
    struct add_rvalue_reference;  
  
template<class T>  
    using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;  
```  
  
#### パラメーター  
 T  
 変更する型。  
  
## 解説  
 `add_rvalue_reference` クラスという名前のメンバーには `type`, 、右辺値参照をテンプレート パラメーターの型のエイリアスである `T`です。 非オブジェクトおよび非関数型の参照縮小のセマンティクスを意味 `T`, 、`T&&` は、 `T`です。 たとえば、 `T` 、左辺値参照型である  `add_rvalue_reference<T>::type` は左辺値参照型で、右辺値参照ではなく。  
  
 便宜上、\< type\_traits \> ヘルパー テンプレートを定義する `add_rvalue_reference_t`, 、そのエイリアス、 `type` のメンバー `add_rvalue_reference`します。  
  
## 使用例  
 このコード例では、static\_assert を使用して、使用して、右辺値参照型を作成する方法を表示する `add_rvalue_reference` と `add_rvalue_reference_t`, 、どのようにの結果 `add_rvalue_reference` 、左辺値参照の型はありませんが、右辺値参照が左辺値参照型に縮小します。  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## 必要条件  
 ヘッダー: \<type\_traits\> 名前空間: std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_lvalue\_reference クラス](../standard-library/add-lvalue-reference-class.md)   
 [is\_rvalue\_reference クラス](../Topic/is_rvalue_reference%20Class.md)