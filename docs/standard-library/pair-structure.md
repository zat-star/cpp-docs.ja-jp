---
title: "pair 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "utility/std::pair"
  - "pair"
  - "std::pair"
  - "std.pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair クラス"
ms.assetid: 539d3d67-80a2-4170-b347-783495d42109
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# pair 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 つのオブジェクトを 1 つのオブジェクトとして処理する機能を提供する構造体。  
  
## 構文  
  
```  
template<class T1, class T2>  
   struct pair   
   {  
   typedef T1 first_type;  
   typedef T2 second_type;  
   T1 first;  
   T2 second;  
  
   constexpr pair( );  
   constexpr pair(  
      const T1& Val1,   
      const T2& Val2  
   );  
  
   template<class Other1, class Other2>  
      constexpr pair(  
         const pair<Other1, Other2>& Right  
      );  
  
template<class Other1, class Other2>  
      constexpr pair(  
        const pair <Other1 Val1, Other2 Val2>&& Right  
      );  
  
   template<class Other1, class Other2>  
      constexpr pair(  
         Other1&& Val1, Other2&& Val2  
      );  
   };  
```  
  
#### パラメーター  
 `Val1`  
 `pair` の最初の要素を初期化する値。  
  
 `Val2`  
 `pair` の 2 番目の要素を初期化する値。  
  
 `Right`  
 別のペアの要素を初期化するために値が使用されるペア。  
  
## 戻り値  
 最初の \(既定の\) コンストラクターがペアの最初の要素を既定の **T1** 型に初期化し、2 番目の要素を既定の **T2** 型に初期化します。  
  
 2 番目のコンストラクターは、ペアの最初の要素を `Val1` に初期化し、2 番目の要素を *Val2* に初期化します。  
  
 3 番目の \(テンプレート\) コンストラクターは、ペアの最初の要素を `Right`.**first** に初期化し、2 番目の要素を `Right`.**second** に初期化します。  
  
 4 番目のコンストラクターは、[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)を使用して、ペアの最初の要素を `Val1` に初期化し、2 番目の要素を *Val2* に初期化します。  
  
## 解説  
 テンプレート構造体は、**T1** 型と **T2** 型のオブジェクトのペアをそれぞれ格納します。  **first\_type** 型はテンプレート パラメーター **T1** と同一で、**second\_type** 型はテンプレート パラメーター **T2** と同一です。  **T1** および **T2** には、それぞれ既定のコンストラクター、引数が 1 つのコンストラクター、およびデストラクターのみ指定する必要があります。  `pair` 型は**クラス**としてではなく `struct` として宣言されているため、この型のメンバーはすべてパブリックです。  ペアの最も一般的な用途としては、2 つの値を返す関数の戻り値の型としての用途と、連想コンテナー クラスの [map クラス](../Topic/map%20Class.md)と [multimap クラス](../standard-library/multimap-class.md)の要素としての用途の 2 つが挙げられます。これらのクラスはどちらも、キーと、各要素に関連付けられている値の型を持っています。  後者は、ペアの連想コンテナーの要件を満たしており、`pair`\<**const** `key_type`, `mapped_type`\> 形式の値の型を持っています。  
  
## 使用例  
  
```  
// utility_pair.cpp  
// compile with: /EHsc  
#include <utility>  
#include <map>  
#include <iomanip>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Using the constructor to declare and initialize a pair  
   pair <int, double> p1 ( 10, 1.1e-2 );  
  
   // Compare using the helper function to declare and initialize a pair  
   pair <int, double> p2;  
   p2 = make_pair ( 10, 2.22e-1 );  
  
   // Making a copy of a pair  
   pair <int, double> p3 ( p1 );  
  
   cout.precision ( 3 );  
   cout << "The pair p1 is: ( " << p1.first << ", "   
        << p1.second << " )." << endl;  
   cout << "The pair p2 is: ( " << p2.first << ", "   
        << p2.second << " )." << endl;  
   cout << "The pair p3 is: ( " << p3.first << ", "   
        << p3.second << " )." << endl;  
  
   // Using a pair for a map element  
   map <int, int> m1;  
   map <int, int>::iterator m1_Iter;  
  
   typedef pair <int, int> Map_Int_Pair;  
  
   m1.insert ( Map_Int_Pair ( 1, 10 ) );  
   m1.insert ( Map_Int_Pair ( 2, 20 ) );  
   m1.insert ( Map_Int_Pair ( 3, 30 ) );  
  
   cout << "The element pairs of the map m1 are:";  
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )  
      cout << " ( " << m1_Iter -> first << ", "  
           << m1_Iter -> second << " )";  
   cout   << "." << endl;  
  
   // Using pair as a return type for a function  
   pair< map<int,int>::iterator, bool > pr1, pr2;  
   pr1 = m1.insert ( Map_Int_Pair ( 4, 40 ) );  
   pr2 = m1.insert ( Map_Int_Pair (1, 10 ) );  
  
   if( pr1.second == true )  
   {  
      cout << "The element (4,40) was inserted successfully in m1."  
           << endl;  
   }  
   else     
   {  
      cout << "The element with a key value of\n"  
           << " ( (pr1.first) -> first ) = " << ( pr1.first ) -> first   
           << " is already in m1,\n so the insertion failed." << endl;  
   }  
  
   if( pr2.second == true )  
   {  
      cout << "The element (1,10) was inserted successfully in m1."  
           << endl;  
   }  
   else     
   {  
      cout << "The element with a key value of\n"  
           << " ( (pr2.first) -> first ) = " << ( pr2.first ) -> first   
           << " is already in m1,\n so the insertion failed." << endl;  
   }  
}  
```  
  
  **ペア p1 は \( 10, 0.011 \)  ペア p2 は \( 10, 0.222 \)  ペア p3 は \( 10, 0.011 \)  マップ m1 の要素ペアは \( 1, 10 \) \( 2, 20 \) \( 3, 30 \)  要素 \(4,40\) は m1 に正常に挿入されました。  キー値**  
 **\( \(pr2.first\) \-\> first \) \= 1 を持つ要素は既に m1 にあるため、**  
 **挿入は失敗しました。**    
## 必要条件  
 **ヘッダー:** \<utility\>  
  
 **名前空間:** std  
  
## 参照  
 [2項論理演算子](../misc/pair-logical-operator.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)