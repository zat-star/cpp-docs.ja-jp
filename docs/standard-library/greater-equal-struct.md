---
title: "greater_equal 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.greater_equal"
  - "greater_equal"
  - "std::greater_equal"
  - "xfunctional/std::greater_equal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "greater_equal 構造体"
  - "greater_equal 関数"
ms.assetid: a8ba911b-7af8-4653-b972-d8618f4df7d5
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# greater_equal 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

引数に対して "以上" 演算 \(`operator>=`\) を実行する二項述語。  
  
## 構文  
  
```  
template<class Type = void>  
   struct greater_equal : public binary_function <Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator>=  
template<>  
   struct greater_equal<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            >= std::forward<Type2>(Right));  
   };  
  
```  
  
#### パラメーター  
 `Type`, `Type1`, `Type2`  
 指定または推論された型のオペランドを受け取る `operator>=` をサポートする任意の型。  
  
 `Left`  
 以上演算の左オペランド。  特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。  特殊化されたテンプレートは、推論された型 `Type1` の左辺値および右辺値参照引数の完全転送を行います。  
  
 `Right`  
 以上演算の右オペランド。  特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。  特殊化されたテンプレートは、推論された型 `Type2` の左辺値および右辺値参照引数の完全転送を行います。  
  
## 戻り値  
 `Left` `>=` `Right` の結果。  特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator>=` によって返された型が含まれます。  
  
## 解説  
 二項述語 `greater_equal`\<`Type`\> は、型 `Type` の要素値のセットの、等価クラスへの厳密弱順序を提供します。ただし、その型がそのように順序付けられる標準的な数学的要件を満たす場合のみです。  任意のポインター型に対する特殊化によって、要素の完全な順序付けが生成されます。この場合、一意の値を持つすべての要素が、相互の値に基づいて並べ替えられます。  
  
## 使用例  
  
```  
// functional_greater_equal.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <cstdlib>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator Iter1;  
  
   int i;  
   v1.push_back( 6262 );  
   v1.push_back( 6262 );  
   for ( i = 0 ; i < 5 ; i++ )  
   {  
      v1.push_back( rand( ) );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use default binary predicate less<int>( )  
   sort( v1.begin( ), v1.end( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in descending order,   
   // specify binary predicate greater_equal<int>( )  
   sort( v1.begin( ), v1.end( ), greater_equal<int>( ) );  
   cout << "Resorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
## 出力  
  
```  
Original vector v1 = ( 6262 6262 41 18467 6334 26500 19169 )  
Sorted vector v1 = ( 41 6262 6262 6334 18467 19169 26500 )  
Resorted vector v1 = ( 26500 19169 18467 6334 6262 6262 41 )  
```  
  
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)