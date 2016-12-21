---
title: "random_access_iterator_tag 構造体 | Microsoft Docs"
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
  - "xutility/std::random_access_iterator_tag"
  - "random_access_iterator_tag"
  - "std.random_access_iterator_tag"
  - "std::random_access_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "random_access_iterator_tag クラス"
  - "random_access_iterator_tag 構造体"
ms.assetid: 59f5b741-c5b4-459c-ad0a-3b67cddeea23
caps.latest.revision: 23
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# random_access_iterator_tag 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ランダム アクセス反復子を表す **iterator\_category** 関数の戻り値の型を提供するクラス。  
  
## 構文  
  
```  
  
   struct random_access_iterator_tag  
: public bidirectional_iterator_tag {};  
```  
  
## 解説  
 カテゴリのタグ クラスは、アルゴリズムの選択に対するコンパイル タグとして使用されます。  このテンプレート関数は、コンパイル時に最も効率的なアルゴリズムを使用できるように反復子の引数の特定のカテゴリを探す必要があります。  型 `Iterator`の反復子は、`iterator_traits`\<`Iterator`\>**::iterator\_category** は、反復子の動作を説明する特定のカテゴリのタグになるように定義する必要があります。  
  
 型は **反復子**\<**Iter**\>**::iterator\_category** と **Iter** がランダム アクセス反復子として使用できるオブジェクトを表すと同じです。  
  
## 使用例  
  
```  
// iterator_rait.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
#include <list>  
  
using namespace std;  
  
int main( )  
{  
   vector<int> vi;  
   vector<char> vc;  
   list<char> lc;  
   iterator_traits<vector<int>:: iterator>::iterator_category cati;  
   iterator_traits<vector<char>:: iterator>::iterator_category catc;  
   iterator_traits<list<char>:: iterator>::iterator_category catlc;  
  
   // These are both random-access iterators  
   cout << "The type of iterator for vector<int> is "  
       << "identified by the tag:\n "   
       << typeid ( cati ).name( ) << endl;  
   cout << "The type of iterator for vector<char> is "  
       << "identified by the tag:\n "   
       << typeid ( catc ).name( ) << endl;  
   if ( typeid ( cati ) == typeid( catc ) )  
      cout << "The iterators are the same." << endl << endl;  
   else  
      cout << "The iterators are not the same." << endl << endl;  
  
   // But the list iterator is bidirectinal, not random access  
   cout << "The type of iterator for list<char> is "  
       << "identified by the tag:\n "   
       << typeid (catlc).name( ) << endl;  
  
   // cout << ( typeid ( vi.begin( ) ) == typeid( vc.begin( ) ) ) << endl;  
   if ( typeid ( vi.begin( ) ) == typeid( vc.begin( ) ) )  
      cout << "The iterators are the same." << endl;  
   else  
      cout << "The iterators are not the same." << endl;  
   // A random-access iterator is a bidirectional iterator.  
   cout << ( void* ) dynamic_cast< iterator_traits<list<char>:: iterator>  
          ::iterator_category* > ( &catc ) << endl;  
}  
```  
  
## 出力例  
 次の出力は x86 のものです。  
  
```  
The type of iterator for vector<int> is identified by the tag:  
 struct std::random_access_iterator_tag  
The type of iterator for vector<char> is identified by the tag:  
 struct std::random_access_iterator_tag  
The iterators are the same.  
  
The type of iterator for list<char> is identified by the tag:  
 struct std::bidirectional_iterator_tag  
The iterators are not the same.  
0012FF3B  
```  
  
## 必要条件  
 **ヘッダー:** の \<反復子\>  
  
 **名前空間:** std  
  
## 参照  
 [bidirectional\_iterator\_tag 構造体](../Topic/bidirectional_iterator_tag%20Struct.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)