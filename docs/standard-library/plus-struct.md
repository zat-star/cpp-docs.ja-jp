---
title: "plus 構造体 | Microsoft Docs"
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
  - "xfunctional/std::plus"
  - "std.plus"
  - "plus"
  - "std::plus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "plus クラス"
  - "plus 構造体"
ms.assetid: 4594abd5-b2f2-4fac-9b6b-fc9a2723f8cf
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# plus 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

引数に対して加算演算 \(二項 `operator+`\) を実行する定義済みの関数オブジェクト。  
  
## 構文  
  
```  
template<class Type = void>  
   struct plus : public binary_function <Type, Type, Type>   
   {  
      Type operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator+  
template<> struct plus<void>  
   {  
   template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
      -> decltype(std::forward<Type1>(Left)  
         + std::forward<Type2>(Right));  
   };  
  
```  
  
#### パラメーター  
 `Type`, `Type1`, `Type2`  
 指定または推論された型のオペランドを受け取る二項 `operator+` をサポートする型。  
  
 `Left`  
 加算演算の左オペランド。  特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。  特殊化されたテンプレートは、推論された型 `Type1` の左辺値および右辺値参照引数の完全転送を行います。  
  
 `Right`  
 加算演算の右オペランド。  特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。  特殊化されたテンプレートは、推論された型 `Type2` の左辺値および右辺値参照引数の完全転送を行います。  
  
## 戻り値  
 `Left` `+` `Right` の結果。  特殊化されたテンプレートは、結果の完全転送を行います。結果には二項 `operator+` によって返された型が含まれます。  
  
## 使用例  
  
```  
// functional_plus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <double> v1, v2, v3 ( 6 );  
   vector <double>::iterator Iter1, Iter2, Iter3;  
  
   int i;  
   for ( i = 0 ; i <= 5 ; i++ )  
      v1.push_back( 4 * i );  
  
   int j;  
   for ( j = 0 ; j <= 5 ; j++ )  
      v2.push_back( -2.0 * j - 4 );  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise sums of the elements of v1 & v2  
   transform (v1.begin( ), v1.end( ), v2.begin( ), v3.begin ( ), plus<double>( ) );  
  
   cout << "The element-wise sums are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **The vector v1 \= \( 0 4 8 12 16 20 \)**  
**The vector v2 \= \( \-4 \-6 \-8 \-10 \-12 \-14 \)**  
**The element\-wise sums are: \( \-4 \-2 0 2 4 6 \)**   
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)