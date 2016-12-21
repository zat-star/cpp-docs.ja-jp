---
title: "iterator_traits 構造体 | Microsoft Docs"
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
  - "std::iterator_traits"
  - "xutility/std::iterator_traits"
  - "iterator_traits"
  - "std.iterator_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator_traits クラス"
  - "iterator_traits 構造体"
ms.assetid: 8b92c2c5-f658-402f-8ca1-e7ae301b8514
caps.latest.revision: 19
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# iterator_traits 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ある反復子が必要とするすべての重要な型定義を指定するために使用するテンプレートのヘルパー構造体。  
  
## 構文  
  
```  
template<class Iterator>  
    struct iterator_traits {  
        typedef typename Iterator::iterator_category iterator_category;  
        typedef typename Iterator::value_type value_type;  
        typedef typename Iterator::difference_type difference_type;  
        typedef difference_type distance_type;  
        typedef typename Iterator::pointer pointer;  
        typedef typename Iterator::reference reference;  
    };  
template<class Type>  
    struct iterator_traits<Type*> {  
        typedef random_access_iterator_tag iterator_category;  
        typedef Type value_type;  
        typedef ptrdiff_t difference_type;  
        typedef difference_type distance_type;  
        typedef Type *pointer;  
        typedef Type& reference;  
    };  
template<class Type>  
    struct iterator_traits<const Type*> {  
        typedef random_access_iterator_tag iterator_category;  
        typedef Type value_type;  
        typedef ptrdiff_t difference_type;  
        typedef difference_type distance_type;  
        typedef const Type *pointer;  
        typedef const Type& reference;  
    };  
```  
  
## 解説  
 テンプレートの構造体にメンバー型を定義します。  
  
-   **iterator\_category**: **Iterator::iterator\_category**のシノニムです。  
  
-   `value_type`: **Iterator::value\_type**のシノニムです。  
  
-   `difference_type`: **Iterator::difference\_type**のシノニムです。  
  
-   `distance_type`: **Iterator::difference\_type.**のシノニム  
  
-   **ポインタ**: **Iterator::pointer**のシノニムです。  
  
-   **リファレンス**: **Iterator::reference**のシノニムです。  
  
 部分的な特化が型 **Type \*** または定数 **Type \***オブジェクト ポインターに関連付けられているすべての重要な型が決まります。  
  
 この実装では、部分的な特化を使用しない複数のテンプレート関数を使用する場合:  
  
```  
template<class Category, class Type, class Diff>  
C _Iter_cat(const iterator<Category, Ty, Diff>&);  
template<class Ty>  
    random_access_iterator_tag _Iter_cat(const Ty *);  
  
template<class Category, class Ty, class Diff>  
Ty *_Val_type(const iterator<Category, Ty, Diff>&);  
template<class Ty>  
    Ty *_Val_type(const Ty *);  
  
template<class Category, class Ty, class Diff>  
Diff *_Dist_type(const iterator<Category, Ty, Diff>&);  
template<class Ty>  
    ptrdiff_t *_Dist_type(const Ty *);  
```  
  
 同じ型のいくつかが間接的に決定されるかを指定できます。  関数呼び出しの引数としてこれらの関数を使用します。  唯一の目的は、呼び出された関数に役立つクラス テンプレート パラメーターを指定します。  
  
## 使用例  
  
```  
// iterator_traits.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iterator>  
#include <vector>  
#include <list>  
  
using namespace std;  
  
template< class it >  
void  
function( it i1, it i2 )  
{  
   iterator_traits<it>::iterator_category cat;  
   cout << typeid( cat ).name( ) << endl;  
   while ( i1 != i2 )  
   {  
      iterator_traits<it>::value_type x;  
      x = *i1;  
      cout << x << " ";  
      i1++;  
   };     
   cout << endl;  
};  
  
int main( )   
{  
   vector<char> vc( 10,'a' );  
   list<int> li( 10 );  
   function( vc.begin( ), vc.end( ) );  
   function( li.begin( ), li.end( ) );  
}  
```  
  
  **構造体の std::random\_access\_iterator\_tag**  
**a**  
**構造体の std::bidirectional\_iterator\_tag**  
**0 0 0 0 0 0 0 0 0 0**   
## 必要条件  
 **ヘッダー:** の \<反復子\>  
  
 **名前空間:** std  
  
## 参照  
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)