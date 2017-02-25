---
title: "back_insert_iterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/std::back_insert_iterator"
  - "std::back_insert_iterator"
  - "back_insert_iterator"
  - "std.back_insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back_insert_iterator クラス"
ms.assetid: a1ee07f2-cf9f-46a1-8608-cfaf207f9713
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# back_insert_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

出力反復子の要件を満たす反復子アダプターについて説明します。 シーケンスのバック エンドに要素を上書きではなく、挿入し、C++ のシーケンス コンテナーの反復子が提供する上書きセマンティクスとは異なるセマンティクスを提供します。 `back_insert_iterator` クラスはコンテナーの型でテンプレート化されます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Container>  
class back_insert_iterator;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Container`  
 要素が `back_insert_iterator` によって後方に挿入されるコンテナーの型。  
  
## <a name="remarks"></a>コメント  
 コンテナーは償却定数時間でシーケンスの末尾に要素を挿入できる、有効な後方挿入シーケンスの要件を満たしている必要があります。 によって定義された、STL シーケンス コンテナー、 [deque クラス](../standard-library/deque-class.md), 、[list クラス](../standard-library/list-class.md) と [vector クラス](../standard-library/vector-class.md) 提供 `push_back` メンバー関数し、これらの要件を満たしています。 この 3 種類のコンテナー、および文字列はそれぞれ `back_insert_iterator` で使用するために改変される可能性があります。 `back_insert_iterator` は、常に、コンテナーで初期化されている必要があります。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[back_insert_iterator](#back_insert_iterator__back_insert_iterator)|コンテナー内の最後の要素の後に要素を挿入する `back_insert_iterator` を構築します。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[container_type](#back_insert_iterator__container_type)|`back_insert_iterator` にコンテナーを提供する型。|  
|[参照](#back_insert_iterator__reference)|`back_insert_iterator` に参照を提供する型。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 *](#back_insert_iterator__operator_star)|出力反復子式の実装に使用される逆参照演算子 * `i` = `x` 後方挿入のです。|  
|[+ + 演算子](#back_insert_iterator__operator_add_add)|値を格納できる次の位置に `back_insert_iterator` をインクリメントします。|  
|[演算子 =](#back_insert_iterator__operator_eq)|出力反復子式を実装するのに使用される代入演算子 * `i` = `x` 後方挿入のです。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー**: \< 反復子>  
  
 **名前空間:** std  
  
##  <a name="a-namebackinsertiteratorbackinsertiteratora-backinsertiteratorbackinsertiterator"></a><a name="back_insert_iterator__back_insert_iterator"></a>  back_insert_iterator::back_insert_iterator  
 コンテナー内の最後の要素の後に要素を挿入する `back_insert_iterator` を構築します。  
  
```  
 
explicit back_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Cont`  
 コンテナーを `back_insert_iterator` に要素を挿入することです。  
  
### <a name="return-value"></a>戻り値  
 A `back_insert_iterator` パラメーター コンテナー用です。  
  
### <a name="example"></a>例  
  
```  
// back_insert_iterator_back_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The initial vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   // Insertions with member function  
   back_inserter ( vec ) = 40;  
   back_inserter ( vec ) = 50;  
  
   // Alternatively, insertions can be done with template function  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 600;  
   backiter++;  
 *backiter = 700;  
  
   cout << "After the insertions, the vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The initial vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec is: ( 1 2 3 40 50 600 700 ).  
```  
  
##  <a name="a-namebackinsertiteratorcontainertypea-backinsertiteratorcontainertype"></a><a name="back_insert_iterator__container_type"></a>  back_insert_iterator::container_type  
 `back_insert_iterator` にコンテナーを提供する型。  
  
```  
 
typedef Container  
container_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **コンテナー**します。  
  
### <a name="example"></a>例  
  
```  
// back_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back (  i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The original vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::container_type vec1 = vec;  
   back_inserter ( vec1 ) = 40;  
  
   cout << "After the insertion, the vector is: ( ";  
   for ( vIter = vec1.begin ( ) ; vIter != vec1.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector vec is: ( 1 2 3 ).  
After the insertion, the vector is: ( 1 2 3 40 ).  
```  
  
##  <a name="a-namebackinsertiteratoroperatorstara-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_star"></a>  back_insert_iterator::operator *  
 出力反復子式の実装に使用される逆参照演算子 \* *は* = *x*です。  
  
```  
back_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーの後ろに挿入される要素への参照。  
  
### <a name="remarks"></a>コメント  
 出力反復子式を実装するために使用 **\*Iter** = **値**です。 場合 **Iter** をし、シーケンス内の要素を指す反復子は、 **\*Iter** = **値** その要素を値に置き換え、シーケンス内の要素の合計数を変更することはできません。  
  
### <a name="example"></a>例  
  
```  
// back_insert_iterator_back_insert.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec becomes: ( 1 2 3 10 20 ).  
```  
  
##  <a name="a-namebackinsertiteratoroperatoraddadda-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_add_add"></a>  back_insert_iterator::operator++  
 値を格納できる次の位置に `back_insert_iterator` をインクリメントします。  
  
```  
back_insert_iterator<Container>& operator++();

back_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>戻り値  
 A `back_insert_iterator` 値を格納するのには次の場所のアドレスを指定します。  
  
### <a name="remarks"></a>コメント  
 Preincrementation と postincrementation の両方の演算子は、同じ結果を返します。  
  
### <a name="example"></a>例  
  
```  
// back_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 3 ; ++i )    
   {  
      vec.push_back ( 10 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 30;  
   backiter++;      // Increment to the next element  
 *backiter = 40;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 10 20 ).  
After the insertions, the vector vec becomes: ( 10 20 30 40 ).  
```  
  
##  <a name="a-namebackinsertiteratoroperatoreqa-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_eq"></a>  back_insert_iterator::operator =  
 追加するかは、値は、コンテナーのバックエンドにプッシュします。  
  
```  
back_insert_iterator<Container>& operator=(typename Container::const_reference val);

    back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>パラメーター  
 ` val`  
 コンテナーに挿入する値。  
  
### <a name="return-value"></a>戻り値  
 コンテナーの後ろに挿入された最後の要素への参照。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー演算子が評価される `Container.push_back( val)`,、  
  
 戻ります `*this`します。 2 番目のメンバー演算子を評価します。  
  
 `container->push_back((typename Container::value_type&&)val)`、  
  
 戻ります `*this`します。  
  
### <a name="example"></a>例  
  
```  
// back_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
##  <a name="a-namebackinsertiteratorreferencea-backinsertiteratorreference"></a><a name="back_insert_iterator__reference"></a>  back_insert_iterator::reference  
 `back_insert_iterator` に参照を提供する型。  
  
```  
 
typedef typename Container::reference reference;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、関連するコンテナーによって制御されるシーケンスの要素への参照を表します。  
  
### <a name="example"></a>例  
  
```  
// back_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::reference   
        RefLast = *(vec.end ( ) - 1 );  
   cout << "The last element in the vector vec is: "   
        << RefLast << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
The last element in the vector vec is: 3.  
```  
  
## <a name="see-also"></a>「  
 [\< 反復子>](../standard-library/iterator.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)

