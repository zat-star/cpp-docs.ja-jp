---
title: "logical_or 構造体 | Microsoft Docs"
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
  - "std.logical_or"
  - "std::logical_or"
  - "logical_or"
  - "xfunctional/std::logical_or"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_or クラス"
  - "logical_or 構造体"
ms.assetid: ec8143f8-5755-4e7b-8025-507fb6bf6911
caps.latest.revision: 22
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# logical_or 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

引数に対して論理和演算 \(`operator||`\) を実行する定義済みの関数オブジェクト。  
  
## 構文  
  
```  
template<class Type = void>  
   struct logical_or : public binary_function<Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator||  
template<>  
   struct logical_or<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            || std::forward<Type2>(Right));  
   };  
  
```  
  
#### パラメーター  
 `Type`, `Type1`, `Type2`  
 指定または推論された型のオペランドを受け取る `operator||` をサポートする任意の型。  
  
 `Left`  
 論理和演算の左オペランド。  特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。  特殊化されたテンプレートは、推論された型 `Type1` の左辺値および右辺値参照引数の完全転送を行います。  
  
 `Right`  
 論理和演算の右オペランド。  特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。  特殊化されたテンプレートは、推論された型 `Type2` の左辺値および右辺値参照引数の完全転送を行います。  
  
## 戻り値  
 `Left` `||` `Right` の結果。  特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator||` によって返された型が含まれます。  
  
## 解説  
 ユーザー定義型の場合、オペランドの評価のショートサーキットはありません。  どちらの引数も `operator||` によって評価されます。  
  
## 使用例  
  
```  
// functional_logical_or.cpp  
// compile with: /EHsc  
#include <deque>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   deque <bool> d1, d2, d3( 7 );  
   deque <bool>::iterator iter1, iter2, iter3;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )  
   {  
      d1.push_back((bool)((rand() % 2) != 0));  
   }  
  
   int j;  
   for ( j = 0 ; j < 7 ; j++ )  
   {  
      d2.push_back((bool)((rand() % 2) != 0));  
   }  
  
   cout << boolalpha;    // boolalpha I/O flag on  
  
   cout << "Original deque:\n d1 = ( " ;  
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )  
      cout << *iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "Original deque:\n d2 = ( " ;  
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )  
      cout << *iter2 << " ";  
   cout << ")" << endl;  
  
   // To find element-wise disjunction of the truth values  
   // of d1 & d2, use the logical_or function object  
   transform( d1.begin( ), d1.end( ), d2.begin( ),  
      d3.begin( ), logical_or<bool>( ) );  
   cout << "The deque which is the disjuction of d1 & d2 is:\n d3 = ( " ;  
   for ( iter3 = d3.begin( ) ; iter3 != d3.end( ) ; iter3++ )  
      cout << *iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Original deque:**  
 **d1 \= \( true true false false true false false \)**  
**Original deque:**  
 **d2 \= \( false false false true true true true \)**  
**The deque which is the disjuction of d1 & d2 is:**  
 **d3 \= \( true true false true true true true \)**   
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)