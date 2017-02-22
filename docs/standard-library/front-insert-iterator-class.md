---
title: "front_insert_iterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/std::front_insert_iterator"
  - "std::front_insert_iterator"
  - "std.front_insert_iterator"
  - "front_insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "front_insert_iterator クラス"
ms.assetid: a9a9c075-136a-4419-928b-c4871afa033c
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# front_insert_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

出力反復子の要件を満たす反復子アダプターについて説明します。 シーケンスの前に要素を上書きではなく、挿入し、C++ のシーケンス コンテナーの反復子が提供する上書きセマンティクスとは異なるセマンティクスを提供します。 `front_insert_iterator` クラスはコンテナーの型でテンプレート化されます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Container>  
class front_insert_iterator;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Container`  
 要素が `front_insert_iterator` によって前方に挿入されるコンテナーの型。  
  
## <a name="remarks"></a>コメント  
 コンテナーは償却定数時間でシーケンスの先頭に要素を挿入できる、有効な前方挿入シーケンスの要件を満たしている必要があります。 によって定義された標準テンプレート ライブラリ シーケンス コンテナー、 [deque クラス](../standard-library/deque-class.md) と [list クラス](../standard-library/list-class.md) 提供 `push_front` メンバー関数し、これらの要件を満たしています。 これに対し、シーケンスで定義されたコンテナー、 [vector クラス](../standard-library/vector-class.md) これらの要件を満たしていないと、使用するように調整することはできません `front_insert_iterator`秒です。 `front_insert_iterator` は、常に、コンテナーで初期化されている必要があります。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[front_insert_iterator](#front_insert_iterator__front_insert_iterator)|指定されたコンテナー オブジェクトの前に要素を挿入できる反復子を作成します。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[container_type](#front_insert_iterator__container_type)|前方挿入の対象となるコンテナーを表す型。|  
|[参照](#front_insert_iterator__reference)|関連するコンテナーによって制御されるシーケンスの要素への参照を提供する型。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 *](#front_insert_iterator__operator_star)|出力反復子式の実装に使用される逆参照演算子 * `i` = `x` 前方挿入のです。|  
|[+ + 演算子](#front_insert_iterator__operator_add_add)|値を格納できる次の位置に `front_insert_iterator` をインクリメントします。|  
|[演算子 =](#front_insert_iterator__operator_eq)|出力反復子式を実装するのに使用される代入演算子 * `i` = `x` 前方挿入のです。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー**: \< 反復子>  
  
 **名前空間:** std  
  
##  <a name="a-namefrontinsertiteratorcontainertypea-frontinsertiteratorcontainertype"></a><a name="front_insert_iterator__container_type"></a>  front_insert_iterator::container_type  
 前方挿入の対象となるコンテナーを表す型。  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **コンテナー**します。  
  
### <a name="example"></a>例  
  
```  
// front_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> >::container_type L2 = L1;  
   front_inserter ( L2 ) = 20;  
   front_inserter ( L2 ) = 10;  
   front_inserter ( L2 ) = 40;  
  
   list <int>::iterator vIter;  
   cout << "The list L2 is: ( ";  
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L2 is: ( 40 10 20 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratorfrontinsertiteratora-frontinsertiteratorfrontinsertiterator"></a><a name="front_insert_iterator__front_insert_iterator"></a>  front_insert_iterator::front_insert_iterator  
 指定されたコンテナー オブジェクトの前に要素を挿入できる反復子を作成します。  
  
```  
explicit front_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Cont`  
 コンテナー オブジェクトを `front_insert_iterator` 要素を挿入することです。  
  
### <a name="return-value"></a>戻り値  
 A `front_insert_iterator` パラメーター コンテナー オブジェクトです。  
  
### <a name="example"></a>例  
  
```  
// front_insert_iterator_front_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for (i = -1 ; i < 9 ; ++i )    
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   // Using the member function to insert an element  
   front_inserter ( L ) = 20;  
  
   // Alternatively, one may use the template function  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatorstara-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_star"></a>  front_insert_iterator::operator *  
 これに対応する要素を返す挿入反復子を逆参照します。  
  
```  
front_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>戻り値  
 メンバー関数は、アドレス指定された要素の値を返します。  
  
### <a name="remarks"></a>コメント  
 出力反復子式を実装するために使用 **\*Iter** = **値**です。 場合 **Iter** をし、シーケンス内の要素を指す反復子は、 **\*Iter** = **値** その要素を値に置き換え、シーケンス内の要素の合計数を変更することはできません。  
  
### <a name="example"></a>例  
  
```  
// front_insert_iterator_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for ( i = -1 ; i < 9 ; ++i )   
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 20;  
  
   // Alternatively, you may use  
   front_inserter ( L ) = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatoraddadda-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_add_add"></a>  front_insert_iterator::operator++  
 値を格納できる次の位置に `back_insert_iterator` をインクリメントします。  
  
```  
front_insert_iterator<Container>& operator++();

front_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>戻り値  
 A `front_insert_iterator` 値を格納するのには次の場所のアドレスを指定します。  
  
### <a name="remarks"></a>コメント  
 Preincrementation と postincrementation の両方の演算子は、同じ結果を返します。  
  
### <a name="example"></a>例  
  
```  
// front_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatoreqa-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_eq"></a>  front_insert_iterator::operator =  
 追加 (プッシュ) 値をコンテナーの前にします。  
  
```  
front_insert_iterator<Container>& operator=(typename Container::const_reference val);

front_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>パラメーター  
 ` val`  
 コンテナーに割り当てられる値です。  
  
### <a name="return-value"></a>戻り値  
 コンテナーの先頭に挿入された最後の要素への参照。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー演算子が評価される `container.push_front( val)`, 、戻ります `*this`します。  
  
 2 番目のメンバー演算子を評価します。  
  
 `container->push_front((typename Container::value_type&&) val)`、  
  
 戻ります `*this`します。  
  
### <a name="example"></a>例  
  
```  
// front_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratorreferencea-frontinsertiteratorreference"></a><a name="front_insert_iterator__reference"></a>  front_insert_iterator::reference  
 関連するコンテナーによって制御されるシーケンスの要素への参照を提供する型。  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="example"></a>例  
  
```  
// front_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L;  
   front_insert_iterator<list<int> > fiivIter( L );  
 *fiivIter = 10;  
 *fiivIter = 20;  
 *fiivIter = 30;  
  
   list<int>::iterator LIter;  
   cout << "The list L is: ( ";  
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++)  
      cout << *LIter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator<list<int> >::reference   
        RefFirst = *(L.begin ( ));  
   cout << "The first element in the list L is: "   
        << RefFirst << "." << endl;  
}  
\* Output:   
The list L is: ( 30 20 10 ).  
The first element in the list L is: 30.  
*\  
```  
  
## <a name="see-also"></a>関連項目  
 [\< 反復子>](../standard-library/iterator.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)

