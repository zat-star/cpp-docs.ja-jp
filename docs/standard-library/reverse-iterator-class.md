---
title: "istreambuf_iterator クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- reverse_iterator
- std::reverse_iterator
- std.reverse_iterator
- xutility/std::reverse_iterator
dev_langs:
- C++
helpviewer_keywords:
- reverse_iterator class
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: ff83cfe68b15e1e94328e96dcd6f33f266bf531a
ms.lasthandoff: 02/24/2017

---
# <a name="reverseiterator-class"></a>reverse_iterator クラス
このテンプレート クラスは、逆方向でのみランダム アクセス反復子または双方向反復子のように動作する反転反復子オブジェクトを表す反復子アダプターです。 これは範囲の後方走査を有効にします。  
  
## <a name="syntax"></a>構文  
  
```  
template <class RandomIterator>  
class reverse_iterator  
```  
  
#### <a name="parameters"></a>パラメーター  
 RandomIterator  
 逆方向に動作するように適合させる反復子を表す型。  
  
## <a name="remarks"></a>コメント  
 既存の C++ 標準ライブラリのコンテナーは、`reverse_iterator` 型および `const_reverse_iterator` 型も定義し、反転反復子を返すメンバー関数 `rbegin` および `rend` を備えています。 これらの反復子には、上書きセマンティクスがあります。 `reverse_iterator` アダプターは、この機能を補完して挿入セマンティクスを提供し、ストリームで使用できるようにします。  
  
 双方向反復子を必要とする `reverse_iterator` で、ランダム アクセス反復子でのみ使用できるメンバー関数 `operator+=`、`operator+`、`operator-=`、`operator-`、または `operator[]` を呼び出すことはできません。  
  
 反復子の範囲が [ ` first`, last) である場合、左側の角かっこは \_*First* を包むことを指定し、右側のかっこは \_*Left* に至るまでの要素は含むが、\_*Left* 自体は除外することを指定します。 同じ要素が反転シーケンス [**rev** â€“ ` first`, **rev** â€“ \_ *Left*) に含まれます。\_ *Left* がシーケンス内で末尾の 1 つ次の要素である場合、反転シーケンス内の最初の要素 **rev** â€“ \_ *First* は \*(\_ *Left* â€“ 1 ) を指します。 すべての反転反復子を基になる反復子に関連付ける識別子は、次のとおりです。  
  
 &\*( **reverse_iterator** ( *i* ) ) == &\*( *i* â€“ 1 ).  
  
 実際には、反転シーケンスで reverse_iterator は、元のシーケンスで反復子が参照する要素の&1; つ次の (右側にある) 要素を参照することを意味します。 したがって、反復子がシーケンス (2、4、6、8) で要素 6 を指定する場合、`reverse_iterator` は反転シーケンス (8、6、4、2) の 4 要素を指定します。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[reverse_iterator](#reverse_iterator__reverse_iterator)|基になる反復子の既定の `reverse_iterator` または `reverse_iterator` を構築します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[difference_type](#reverse_iterator__difference_type)|同じコンテナー内の要素を参照する&2; つの `reverse_iterator` の違いを提供する型。|  
|[iterator_type](#reverse_iterator__iterator_type)|`reverse_iterator` に基になる反復子を提供する型。|  
|[pointer](#reverse_iterator__pointer)|`reverse_iterator` によってアドレス指定される要素へのポインターを提供する型。|  
|[reference](#reverse_iterator__reference)|`reverse_iterator` によってアドレス指定される要素への参照を提供する型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[base](#reverse_iterator__base)|その `reverse_iterator` から基になる反復子を復元します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator_star](#reverse_iterator__operator_star)|`reverse_iterator` がアドレス指定する要素を返します。|  
|[operator+](#reverse_iterator__operator_add)|反復子にオフセットを追加し、新しいオフセット位置に挿入された要素をアドレス指定する新しい `reverse_iterator` アドレスを返します。|  
|[operator++](#reverse_iterator__operator_add_add)|`reverse_iterator` を次の要素にインクリメントします。|  
|[operator+=](#reverse_iterator__operator_add_eq)|指定したオフセットを `reverse_iterator` から追加します。|  
|[operator-](#reverse_iterator__operator-)|`reverse_iterator` からオフセットを減算し、オフセット位置にある要素を指定する `reverse_iterator` を返します。|  
|[operator--](#reverse_iterator__operator--)|`reverse_iterator` を直前の要素にデクリメントします。|  
|[operator-=](#reverse_iterator__operator-_eq)|指定されたオフセットを `reverse_iterator` から減算します。|  
|[operator->](#reverse_iterator__operator-_gt_)|`reverse_iterator` によってアドレス指定される要素へのポインターを返します。|  
|[operator&#91;&#93;](#reverse_iterator__operator_at)|`reverse_iterator` によってアドレス指定される要素からの要素のオフセットへの参照を返します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<iterator>  
  
 **名前空間:** std  
  
##  <a name="a-namereverseiteratorbasea--reverseiteratorbase"></a><a name="reverse_iterator__base"></a>  reverse_iterator::base  
 その `reverse_iterator` から基になる反復子を復元します。  
  
```   
RandomIterator base() const;
```  
  
### <a name="return-value"></a>戻り値  
 `reverse_iterator` の基になる反復子。  
  
### <a name="remarks"></a>コメント  
 すべての反転反復子を基になる反復子に関連付ける識別子は、次のとおりです。  
  
 &\*( `reverse_iterator` ( *i* ) ) == &\*( *i* â€“ 1 ).  
  
 実際には、反転シーケンスで `reverse_iterator` は、元のシーケンスで反復子が参照する要素の&1; つ次の (右側にある) 要素を参照することを意味します。 したがって、反復子がシーケンス (2、4、6、8) で要素 6 を指定する場合、`reverse_iterator` は反転シーケンス (8、6、4、2) の 4 要素を指定します。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_base.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos, bpos;  
   pos = find ( vec.begin ( ), vec.end ( ), 6 );  
   cout << "The iterator pos points to: " << *pos << "." << endl;  
  
   typedef reverse_iterator<vector<int>::iterator>::iterator_type it_vec_int_type;  
  
   reverse_iterator<it_vec_int_type> rpos ( pos );  
   cout << "The reverse_iterator rpos points to: " << *rpos   
        << "." << endl;  
  
   bpos = rpos.base ( );  
   cout << "The iterator underlying rpos is bpos & it points to: "   
        << *bpos << "." << endl;  
}  
```  
  
##  <a name="a-namereverseiteratordifferencetypea--reverseiteratordifferencetype"></a><a name="reverse_iterator__difference_type"></a>  reverse_iterator::difference_type  
 同じコンテナー内の要素を参照する&2; つの `reverse_iterator` の違いを提供する型。  
  
```   
typedef typename iterator_traits<RandomIterator>::difference_type  difference_type; 
```  
  
### <a name="remarks"></a>コメント  
 `reverse_iterator` の差の型は、反復子の差の型と同じです。  
  
 この型は、反復子の特徴型名 `iterator_traits`\< **RandomIterator**> **::pointer** のシノニムです。  
  
### <a name="example"></a>例  
  `difference_type` を宣言して使用する方法の例については、[reverse_iterator::operator&#91;&#93](#reverse_iterator__operator_at) に関するページを参照してください。  
  
##  <a name="a-namereverseiteratoriteratortypea--reverseiteratoriteratortype"></a><a name="reverse_iterator__iterator_type"></a>  reverse_iterator::iterator_type  
 `reverse_iterator` に基になる反復子を提供する型。  
  
```  
typedef RandomIterator iterator_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター `Iterator`のシノニムです。  
  
### <a name="example"></a>例  
  `iterator_type` を宣言して使用する方法の例については、[reverse_iterator::base](#reverse_iterator__base) を参照してください。  
  
##  <a name="a-namereverseiteratoroperatorstara--reverseiteratoroperator"></a><a name="reverse_iterator__operator_star"></a>  reverse_iterator::operator*  
 reverse_iterator が指す要素を返します。  
  
```   
reference operator*() const;
```  
  
### <a name="return-value"></a>戻り値  
 reverse_iterator により指される要素の値。  
  
### <a name="remarks"></a>コメント  
 演算子は \*( **current** â€“ 1) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_op_ref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos, bpos;  
   pos = find ( vec.begin ( ), vec.end ( ), 6 );  
  
   // Declare a difference type for a parameter  
   // declare a reference return type  
   reverse_iterator<vector<int>::iterator>::reference refpos = *pos;  
   cout << "The iterator pos points to: " << refpos << "." << endl;  
}  
```  
  
##  <a name="a-namereverseiteratoroperatoradda--reverseiteratoroperator"></a><a name="reverse_iterator__operator_add"></a>  reverse_iterator::operator+  
 反復子にオフセットを追加し、新しいオフセット位置に挿入された要素をアドレス指定する新しい `reverse_iterator` アドレスを返します。  
  
```  
reverse_iterator<RandomIterator> operator+(difference_type Off) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `Off`  
 逆順反復子に追加するオフセット。  
  
### <a name="return-value"></a>戻り値  
 オフセット要素を指す `reverse_iterator`。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用できるのは、`reverse_iterator` がランダムアクセス反復子の要件を満たす場合のみです。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_op_add.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );  
  
   cout << "The iterator rVPOS1 initially points to the first "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   vector <int>::reverse_iterator rVPOS2 =rVPOS1 + 2; // offset added  
   cout << "After the +2 offset, the iterator rVPOS2 points\n"  
        << " to the 3rd element in the reversed sequence: "  
        << *rVPOS2 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 2 4 6 8 10 ).  
The vector vec reversed is: ( 10 8 6 4 2 ).  
The iterator rVPOS1 initially points to the first element  
 in the reversed sequence: 10.  
After the +2 offset, the iterator rVPOS2 points  
 to the 3rd element in the reversed sequence: 6.  
```  
  
##  <a name="a-namereverseiteratoroperatoraddadda--reverseiteratoroperator"></a><a name="reverse_iterator__operator_add_add"></a>  reverse_iterator::operator++  
 reverse_iterator を直前の要素にインクリメントします。  
  
```  
reverse_iterator<RandomIterator>& operator++();
reverse_iterator<RandomIterator> operator++(int);
```  
  
### <a name="return-value"></a>戻り値  
 最初の演算子は、プリインクリメントされた `reverse_iterator` を返し、2 番目のポストインクリメント演算子は、インクリメントされた `reverse_iterator` のコピーを返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用できるのは、`reverse_iterator` が双方向反復子の要件を満たす場合のみです。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i - 1 );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the last element  
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin( );  
  
   cout << "The iterator rVPOS1 initially points to the first "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   rVPOS1++;  // postincrement, preincrement: ++rVPSO1  
  
   cout << "After incrementing, the iterator rVPOS1 points\n"  
        << " to the second element in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 3 5 7 9 ).  
The vector vec reversed is: ( 9 7 5 3 1 ).  
The iterator rVPOS1 initially points to the first element  
 in the reversed sequence: 9.  
After incrementing, the iterator rVPOS1 points  
 to the second element in the reversed sequence: 7.  
```  
  
##  <a name="a-namereverseiteratoroperatoraddeqa--reverseiteratoroperator"></a><a name="reverse_iterator__operator_add_eq"></a>  reverse_iterator::operator+=  
 指定したオフセットを reverse_iterator から追加します。  
  
```  
reverse_iterator<RandomIterator>& operator+=(difference_type Off);
```  
  
### <a name="parameters"></a>パラメーター  
 `Off`  
 反復子をインクリメントするオフセット。  
  
### <a name="return-value"></a>戻り値  
 `reverse_iterator` によってアドレス指定される要素への参照を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_op_addoff.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )   
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the last element  
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );  
  
   cout << "The iterator rVPOS1 initially points to the first "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   rVPOS1+=2;   // addition of an offset  
   cout << "After the +2 offset, the iterator rVPOS1 now points\n"  
        << " to the third element in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 2 4 6 8 10 ).  
The vector vec reversed is: ( 10 8 6 4 2 ).  
The iterator rVPOS1 initially points to the first element  
 in the reversed sequence: 10.  
After the +2 offset, the iterator rVPOS1 now points  
 to the third element in the reversed sequence: 6.  
```  
  
##  <a name="a-namereverseiteratoroperator-a--reverseiteratoroperator-"></a><a name="reverse_iterator__operator-"></a>  reverse_iterator::operator-  
 `reverse_iterator` からオフセットを減算し、オフセット位置にある要素を指定する `reverse_iterator` を返します。  
  
```  
reverse_iterator<RandomIterator> operator-(difference_type Off) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `Off`  
 reverse_iterator から減算するオフセット。  
  
### <a name="return-value"></a>戻り値  
 オフセット要素を指す `reverse_iterator`。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用できるのは、`reverse_iterator` がランダムアクセス反復子の要件を満たす場合のみです。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_op_sub.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( 3 * i );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;  
  
   cout << "The iterator rVPOS1 initially points to the last "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   vector <int>::reverse_iterator rVPOS2 =rVPOS1 - 2; // offset subtracted  
   cout << "After the -2 offset, the iterator rVPOS2 points\n"  
        << " to the 2nd element from the last in the reversed sequence: "  
        << *rVPOS2 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 3 6 9 12 15 ).  
The vector vec reversed is: ( 15 12 9 6 3 ).  
The iterator rVPOS1 initially points to the last element  
 in the reversed sequence: 3.  
After the -2 offset, the iterator rVPOS2 points  
 to the 2nd element from the last in the reversed sequence: 9.  
```  
  
##  <a name="a-namereverseiteratoroperator--a--reverseiteratoroperator--"></a><a name="reverse_iterator__operator--"></a>  reverse_iterator::operator--  
 reverse_iterator を直前の要素にデクリメントします。  
  
```  
reverse_iterator<RandomIterator>& operator--();
reverse_iterator<RandomIterator> operator--(int);
```  
  
### <a name="return-value"></a>戻り値  
 最初の演算子はプリデクリメントされた `reverse_iterator` を返し、2 番目のポストデクリメント演算子は、デクリメントされた `reverse_iterator` のコピーを返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用できるのは、`reverse_iterator` が双方向反復子の要件を満たす場合のみです。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_op_decr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i - 1 );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;  
  
   cout << "The iterator rVPOS1 initially points to the last "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
   rVPOS1--;  // postdecrement, predecrement: --rVPSO1  
  
   cout << "After the decrement, the iterator rVPOS1 points\n"  
        << " to the next-to-last element in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 3 5 7 9 ).  
The vector vec reversed is: ( 9 7 5 3 1 ).  
The iterator rVPOS1 initially points to the last element  
 in the reversed sequence: 1.  
After the decrement, the iterator rVPOS1 points  
 to the next-to-last element in the reversed sequence: 3.  
```  
  
##  <a name="a-namereverseiteratoroperator-eqa--reverseiteratoroperator-"></a><a name="reverse_iterator__operator-_eq"></a>  reverse_iterator::operator-=  
 指定されたオフセットを `reverse_iterator` から減算します。  
  
```  
reverse_iterator<RandomIterator>& operator-=(difference_type Off);
```  
  
### <a name="parameters"></a>パラメーター  
 `Off`  
 `reverse_iterator` から減算されるオフセット。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用できるのは、`reverse_iterator` がランダムアクセス反復子の要件を満たす場合のみです。  
  
 演算子は **current** + _ *Off* を評価します。 その後、**\* this** を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_op_suboff.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( 3 * i );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;  
  
   cout << "The iterator rVPOS1 initially points to the last "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   rVPOS1-=2;      // Subtraction of an offset  
   cout << "After the -2 offset, the iterator rVPOS1 now points\n"  
        << " to the 2nd element from the last in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 3 6 9 12 15 ).  
The vector vec reversed is: ( 15 12 9 6 3 ).  
The iterator rVPOS1 initially points to the last element  
 in the reversed sequence: 3.  
After the -2 offset, the iterator rVPOS1 now points  
 to the 2nd element from the last in the reversed sequence: 9.  
```  
  
##  <a name="a-namereverseiteratoroperator-gta--reverseiteratoroperator-gt"></a><a name="reverse_iterator__operator-_gt_"></a>  reverse_iterator::operator-&gt;  
 `reverse_iterator` によってアドレス指定される要素へのポインターを返します。  
  
```   
pointer operator->() const;
```  
  
### <a name="return-value"></a>戻り値  
 `reverse_iterator` によってアドレス指定される要素へのポインター。  
  
### <a name="remarks"></a>コメント  
 この演算子は、**&\*\*this** を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_ptrto.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <utility>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef vector<pair<int,int> > pVector;  
   pVector vec;  
   vec.push_back(pVector::value_type(1,2));  
   vec.push_back(pVector::value_type(3,4));  
   vec.push_back(pVector::value_type(5,6));  
  
   pVector::iterator pvIter;  
   cout << "The vector vec of integer pairs is:\n( ";  
   for ( pvIter = vec.begin ( ) ; pvIter != vec.end ( ); pvIter++)  
      cout << "( " << pvIter -> first << ", " << pvIter -> second << ") ";  
   cout << ")" << endl << endl;  
  
   pVector::reverse_iterator rpvIter;  
   cout << "The vector vec reversed is:\n( ";  
   for ( rpvIter = vec.rbegin( ) ; rpvIter != vec.rend( ); rpvIter++ )  
      cout << "( " << rpvIter -> first << ", " << rpvIter -> second << ") ";  
   cout << ")" << endl << endl;  
  
   pVector::iterator pos = vec.begin ( );  
   pos++;  
   cout << "The iterator pos points to:\n( " << pos -> first << ", "   
   << pos -> second << " )" << endl << endl;  
  
   pVector::reverse_iterator rpos (pos);   
  
   // Use operator -> with return type: why type int and not int*  
   int fint = rpos -> first;  
   int sint = rpos -> second;  
  
   cout << "The reverse_iterator rpos points to:\n( " << fint << ", "   
   << sint << " )" << endl;  
}  
```  
  
```Output  
The vector vec of integer pairs is:  
( ( 1, 2) ( 3, 4) ( 5, 6) )  
  
The vector vec reversed is:  
( ( 5, 6) ( 3, 4) ( 1, 2) )  
  
The iterator pos points to:  
( 3, 4 )  
  
The reverse_iterator rpos points to:  
( 1, 2 )  
```  
  
##  <a name="a-namereverseiteratoroperatorata--reverseiteratoroperator"></a><a name="reverse_iterator__operator_at"></a>  reverse_iterator::operator[]  
 `reverse_iterator` によってアドレス指定される要素からの要素のオフセットへの参照を返します。  
  
```   
reference operator[](difference_type Off) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `Off`  
 `reverse_iterator` アドレスからのオフセット。  
  
### <a name="return-value"></a>戻り値  
 オフセット要素への参照。  
  
### <a name="remarks"></a>コメント  
 この演算子は、**\***( **\*this** + `Off` を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_ret_ref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos;  
   pos = find ( vec.begin ( ), vec.end ( ), 8 );  
   reverse_iterator<vector<int>::iterator> rpos ( pos );  
  
   // Declare a difference type for a parameter  
   reverse_iterator<vector<int>::iterator>::difference_type diff = 2;  
  
   cout << "The iterator pos points to: " << *pos << "." << endl;  
   cout << "The iterator rpos points to: " << *rpos << "." << endl;  
  
   // Declare a reference return type & use operator[]  
   reverse_iterator<vector<int>::iterator>::reference refrpos = rpos [diff];  
   cout << "The iterator rpos now points to: " << refrpos << "." << endl;     
}  
```  
  
```Output  
The vector vec is: ( 2 4 6 8 10 ).  
The vector vec reversed is: ( 10 8 6 4 2 ).  
The iterator pos points to: 8.  
The iterator rpos points to: 6.  
The iterator rpos now points to: 2.  
```  
  
##  <a name="a-namereverseiteratorpointera--reverseiteratorpointer"></a><a name="reverse_iterator__pointer"></a>  reverse_iterator::pointer  
 `reverse_iterator` によってアドレス指定される要素へのポインターを提供する型。  
  
```  
typedef typename iterator_traits<RandomIterator>::pointer pointer;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、反復子の特徴型名 `iterator_traits`\< *RandomIterator*> **::pointer** のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_pointer.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <utility>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef vector<pair<int,int> > pVector;  
   pVector vec;  
   vec.push_back( pVector::value_type( 1,2 ) );  
   vec.push_back( pVector::value_type( 3,4 ) );  
   vec.push_back( pVector::value_type( 5,6 ) );  
  
   pVector::iterator pvIter;  
   cout << "The vector vec of integer pairs is:\n" << "( ";  
   for ( pvIter = vec.begin ( ) ; pvIter != vec.end ( ); pvIter++)  
      cout << "( " << pvIter -> first << ", " << pvIter -> second << ") ";  
   cout << ")" << endl;  
  
   pVector::reverse_iterator rpvIter;  
   cout << "\nThe vector vec reversed is:\n" << "( ";  
   for ( rpvIter = vec.rbegin( ) ; rpvIter != vec.rend( ); rpvIter++)  
      cout << "( " << rpvIter -> first << ", " << rpvIter -> second << ") ";  
   cout << ")" << endl;  
  
   pVector::iterator pos = vec.begin ( );  
   pos++;  
   cout << "\nThe iterator pos points to:\n"  
        << "( " << pos -> first << ", "  
        << pos -> second << " )" << endl;  
  
   pVector::reverse_iterator rpos (pos);  
   cout << "\nThe iterator rpos points to:\n"  
        << "( " << rpos -> first << ", "  
        << rpos -> second << " )" << endl;  
}  
```  
  
```Output  
The vector vec of integer pairs is:  
( ( 1, 2) ( 3, 4) ( 5, 6) )  
  
The vector vec reversed is:  
( ( 5, 6) ( 3, 4) ( 1, 2) )  
  
The iterator pos points to:  
( 3, 4 )  
  
The iterator rpos points to:  
( 1, 2 )  
```  
  
##  <a name="a-namereverseiteratorreferencea--reverseiteratorreference"></a><a name="reverse_iterator__reference"></a>  reverse_iterator::reference  
 reverse_iterator によってアドレス指定される要素への参照を提供する型。  
  
```  
typedef typename iterator_traits<RandomIterator>::reference reference;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、反復子の特徴型名 `iterator_traits`\< *RandomIterator*> **::reference** のシノニムです。  
  
### <a name="example"></a>例  
  **reference** の宣言方法および使用方法の例については、[reverse_iterator::operator&#91;&#93;](#reverse_iterator__operator_at) または [reverse_iterator::operator*](#reverse_iterator__operator_star) に関するページを参照してください。  
  
##  <a name="a-namereverseiteratorreverseiteratora--reverseiteratorreverseiterator"></a><a name="reverse_iterator__reverse_iterator"></a>  reverse_iterator::reverse_iterator  
 基になる反復子の既定の `reverse_iterator` または `reverse_iterator` を構築します。  
  
```   
reverse_iterator();  
explicit reverse_iterator(RandomIterator right);

template <class Type>  
reverse_iterator(const reverse_iterator<Type>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 `reverse_iterator` に適合させる反復子。  
  
### <a name="return-value"></a>戻り値  
 既定の `reverse_iterator`、または基になる反復子を適合させる `reverse_iterator`。  
  
### <a name="remarks"></a>コメント  
 すべての反転反復子を基になる反復子に関連付ける識別子は、次のとおりです。  
  
 &\*( `reverse_iterator` ( *i* ) ) == &\*( *i* â€“ 1 ).  
  
 実際には、反転シーケンスで reverse_iterator は、元のシーケンスで反復子が参照する要素の&1; つ次の (右側にある) 要素を参照することを意味します。 したがって、反復子がシーケンス (2、4、6、8) で要素 6 を指定する場合、`reverse_iterator` は反転シーケンス (8、6、4、2) の 4 要素を指定します。  
  
### <a name="example"></a>例  
  
```cpp  
// reverse_iterator_reverse_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos;  
   pos = find ( vec.begin ( ), vec.end ( ), 4 );  
   cout << "The iterator pos = " << *pos << "." << endl;  
  
   vector <int>::reverse_iterator rpos ( pos );  
   cout << "The reverse_iterator rpos = " << *rpos   
        << "." << endl;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)


