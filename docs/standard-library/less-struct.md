---
title: "less 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::less"
  - "std.less"
  - "less"
  - "xfunctional/std::less"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "less 構造体"
  - "less 関数"
ms.assetid: 39349da3-11cd-4774-b2cc-b46af5aae5d7
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# less 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

引数に対して "より小さい" 演算 \(`operator<`\) を実行する二項述語。  
  
## 構文  
  
```  
template<class Type = void>  
   struct less : public binary_function <Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator<  
template<>  
   struct less<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            < std::forward<Type2>(Right));  
   };  
  
```  
  
#### パラメーター  
 `Type`, `Type1`, `Type2`  
 指定または推論された型のオペランドを受け取る `operator<` をサポートする任意の型。  
  
 `Left`  
 より小さい演算の左オペランド。  特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。  特殊化されたテンプレートは、推論された型 `Type1` の左辺値および右辺値参照引数の完全転送を行います。  
  
 `Right`  
 より小さい演算の右オペランド。  特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。  特殊化されたテンプレートは、推論された型 `Type2` の左辺値および右辺値参照引数の完全転送を行います。  
  
## 戻り値  
 `Left` `<` `Right` の結果。  特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator<` によって返された型が含まれます。  
  
## 解説  
 二項述語 `less`\<`Type`\> は、型 `Type` の要素値のセットの、等価クラスへの厳密弱順序を提供します。ただし、その型がそのように順序付けられる標準的な数学的要件を満たす場合のみです。  任意のポインター型に対する特殊化によって、要素の完全な順序付けが生成されます。この場合、一意の値を持つすべての要素が、相互の値に基づいて並べ替えられます。  
  
## 使用例  
  
```  
// functional_less.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
struct MyStruct {  
   MyStruct(int i) : m_i(i){}  
  
   bool operator < (const MyStruct & rhs) const {  
      return m_i < rhs.m_i;  
   }     
  
   int m_i;  
};  
  
int main() {  
   using namespace std;  
   vector <MyStruct> v1;  
   vector <MyStruct>::iterator Iter1;  
   vector <MyStruct>::reverse_iterator rIter1;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )       
       v1.push_back( MyStruct(rand()));  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )   
cout << Iter1->m_i << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   sort( v1.begin( ), v1.end( ), less<MyStruct>());  
  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )   
cout << Iter1->m_i << " ";  
   cout << ")" << endl;  
 }  
```  
  
## 出力  
  
```  
Original vector v1 = ( 41 18467 6334 26500 19169 15724 11478 )  
Sorted vector v1 = ( 41 6334 11478 15724 18467 19169 26500 )  
```  
  
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)