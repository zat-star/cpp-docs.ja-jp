---
title: "tuple_element クラス&lt;utility&gt; | Microsoft Docs"
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
  - "std.tr1.tuple_element"
  - "tuple_element"
  - "std::tr1::tuple_element"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple_element クラス<utility> (TR1)"
ms.assetid: f9db79e8-685c-49e3-97ee-81763e516ce3
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tuple_element クラス&lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`pair` 要素の型をラップします。  
  
## 構文  
  
```  
// CLASS tuple_element (find element by index)  
template<size_t Index, class Tuple>  
struct tuple_element;  
  
// struct to determine type of element 0 in pair  
template<class Ty1, class Ty2>  
struct tuple_element<0, pair<Ty1, Ty2> >;  
  
// struct to determine type of element 1 in pair  
template<class Ty1, class Ty2>  
struct tuple_element<1, pair<Ty1, Ty2> >;  
  
// tuple_element for const  
template<size_t Index, class Tuple>  
struct tuple_element<Index, const Tuple>;  
  
// tuple_element for volatile  
template<size_t Index, class Tuple>  
struct tuple_element<Index, volatile Tuple>;  
  
// tuple_element for const volatile  
template<size_t Index, class Tuple>  
struct tuple_element<Index, const volatile Tuple>;  
  
template<size_t Index, class Tuple>  
using tuple_element_t = typename tuple_element<Index, Tuple>::type;  
```  
  
#### パラメーター  
 インデックス  
 要素の位置。ペアの場合、この値は、0 または 1 のいずれかです。  
  
 `T1`  
 1 番目の pair 要素の型。  
  
 `T2`  
 2 番目の pair 要素の型。  
  
 型  
  
## 解説  
 これらのテンプレートは、テンプレート クラス [tuple\_element クラス](../standard-library/tuple-element-class-tuple.md) を特殊化したものです。 それぞれが、1 つのメンバーの typedef である `type` を持っています。これは、`pair` の指定された位置にある要素の型のシノニムであり、const または volatile の制限が保持されます。`tuple_element_t` は `tuple_element<N, pair<T1, T2>>::type` の便利なエイリアスです。[get 関数](../Topic/get%20Function%20%3Cutility%3E.md) を使用して、指定した位置または \(C\+\+14 \/ Visual Studio 2015 内の\) 指定した型の要素を返します。  
  
## 使用例  
  
```  
#include <utility>   
#include <iostream>   
  
using namespace std;  
  
typedef pair<int, double> MyPair;  
int main()  
{  
    MyPair c0(0, 1.333);  
  
    // display contents " 0 1"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0) << endl;  
  
    // display first element " 0" by index  
    tuple_element<0, MyPair>::type val = get<0>(c0);  
    cout << " " << val;  
  
    // display second element by type   
    tuple_element<1, MyPair>::type val2 = get<double>(c0);  
    cout << " " << val2 << endl;  
}  
  
/*  
Output:  
0 1.333  
0 1.333  
*/  
```  
  
## 必要条件  
 **ヘッダー:** \<utility\>  
  
 **名前空間:** std  
  
## 参照  
 [\<utility\>](../standard-library/utility.md)   
 [get 関数](../Topic/get%20Function%20%3Cutility%3E.md)   
 [tuple\_size クラス](../standard-library/tuple-size-class-utility.md)