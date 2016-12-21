---
title: "tuple_size クラス &lt;array&gt; | Microsoft Docs"
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
  - "tuple_size"
  - "std::tr1::tuple_size"
  - "std.tr1.tuple_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple_size クラス <array> (TR1)"
ms.assetid: ef95ffee-59b4-4396-817f-487d4486772d
caps.latest.revision: 20
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tuple_size クラス &lt;array&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

配列のサイズをラップします。  
  
## 構文  
  
```  
template<class Tuple>  
struct tuple_size;  
  
// struct to determine number of elements in array  
template<class T, size_t Size>  
struct tuple_size<array<T, Size> >  
: integral_constant<size_t, Size>;  
  
// size of const tuple  
template<class Tuple>  
struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template<class Tuple>  
struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template<class Tuple>  
struct tuple_size<const volatile Tuple>;  
  
```  
  
## テンプレート パラメーター  
 `T`  
 要素の型。  
  
 `Size`  
 配列のサイズ。  
  
## 解説  
 このテンプレートは、テンプレート クラス [tuple\_size クラス](../standard-library/tuple-size-class-tuple.md) を特殊化したものです。 配列のサイズである `N` を値として持つ整数定数式であるメンバー `value` が含まれます。  
  
## 使用例  
  
```  
#include <array>   
#include <iostream>   
  
using namespace std;  
  
typedef array<int, 4> MyArray;  
  
int main()  
{  
    MyArray c0 { 0, 1, 2, 3 };  
  
    // display contents " 0 1 2 3"   
    for (const auto& e : c0)  
    {  
        cout << e;  
    }  
    cout << endl;  
  
    // display size " 4"   
    cout << " " << tuple_size<MyArray>::value << endl;  
}  
/*  
Output:  
0123  
4  
*/  
  
```  
  
## 必要条件  
 **ヘッダー:** \<array\>  
  
 **名前空間:** std  
  
## 参照  
 [\<array\>](../standard-library/array.md)   
 [\<tuple\>](../standard-library/tuple.md)   
 [tuple\_size クラス](../standard-library/tuple-size-class-tuple.md)