---
title: "multiplies 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::multiplies"
  - "multiplies"
  - "xfunctional/std::multiplies"
  - "std.multiplies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multiplies クラス"
  - "multiplies 構造体"
ms.assetid: ec85e8af-70ad-44ad-90f0-d961a5847864
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# multiplies 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

引数に対して乗算演算 \(二項 `operator*`\) を実行する定義済みの関数オブジェクト。  
  
## 構文  
  
```  
template<class Type = void>  
   struct multiplies : public binary_function <Type, Type, Type>   
   {  
      Type operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator*  
template<>  
   struct multiplies<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            * std::forward<Type2>(Right));  
   };  
  
```  
  
#### パラメーター  
 `Type`, `Type1`, `Type2`  
 指定または推論された型のオペランドを受け取る二項 `operator*` をサポートする型。  
  
 `Left`  
 乗算演算の左オペランド。  特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。  特殊化されたテンプレートは、推論された型 `Type1` の左辺値および右辺値参照引数の完全転送を行います。  
  
 `Right`  
 乗算演算の右オペランド。  特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。  特殊化されたテンプレートは、推論された型 `Type2` の左辺値および右辺値参照引数の完全転送を行います。  
  
## 戻り値  
 `Left` `*` `Right` の結果。  特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator*` によって返された型が含まれます。  
  
## 使用例  
  
```  
// functional_multiplies.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <int> v1, v2, v3 ( 6 );  
   vector <int>::iterator Iter1, Iter2, Iter3;  
  
   int i;  
   for ( i = 1 ; i <= 6 ; i++ )  
   {  
      v1.push_back( 2 * i );  
   }  
  
   int j;  
   for ( j = 1 ; j <= 6 ; j++ )  
   {  
      v2.push_back( 3 * j );  
   }  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise products of the elements of v1 & v2  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),   
      multiplies<int>( ) );  
  
   cout << "The element-wise products of vectors V1 & v2\n are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **The vector v1 \= \( 2 4 6 8 10 12 \)**  
**The vector v2 \= \( 3 6 9 12 15 18 \)**  
**The element\-wise products of vectors V1 & v2**  
 **are: \( 6 24 54 96 150 216 \)**   
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)