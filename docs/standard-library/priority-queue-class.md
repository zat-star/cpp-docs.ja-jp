---
title: "priority_queue クラス | Microsoft Docs"
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
  - "std.priority_queue"
  - "priority_queue"
  - "std::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "priority_queue クラス"
ms.assetid: 69fca9cc-a449-4be4-97b7-02ca5db9cbb2
caps.latest.revision: 25
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# priority_queue クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

制限が最大で常にいくつかの基になるコンテナー型のまたは優先度が高いは、最上位の要素へのアクセスを制限する機能を提供するテンプレート コンテナー アダプター クラス。 Priority_queue に新しい要素を追加でき、priority_queue の最上位の要素を検査または削除します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Type, class Container= vector <Type>, class Compare= less <typename Container ::value_type>>  
class priority_queue  
```  
  
#### <a name="parameters"></a>パラメーター  
 *Type*  
 Priority_queue に格納される要素のデータを入力します。  
  
 `Container`  
 Priority_queue を実装するために使用する基になるコンテナーの型。  
  
 *比較*  
 Priority_queue 内の相対順序を決定する並べ替えキーとして 2 つの要素の値を比較できる関数オブジェクトを提供する型。 この引数は省略可能と二項述語 **少ない***\<***typename** *コンテナー***:: value_type***>* 既定値です。  
  
## <a name="remarks"></a>コメント  
 クラスの要素 **型** 最初のテンプレートで規定されている、キュー オブジェクトのパラメーターが指定と同じ意味 [value_type](#priority_queue__value_type) 基になるコンテナー クラス内の要素の型を一致させる必要があります **コンテナー** 、2 番目のテンプレート パラメーターで規定します。  **型** その型のオブジェクトをコピーして、その型の変数に値を割り当てることができるように、割り当てることがあります。  
  
 Priority_queue が格納されている関数オブジェクトのクラスを呼び出すことによって、制御するシーケンスを並べ替えます **特徴 (traits)**します。 通常、要素は、この順序を確立するために小なり比較だけを実行できる必要があります。これにより、2 つの要素が指定されたときに、それらの要素が等しいか (どちらか一方が小さくはない)、または一方が他方より小さいかを判断できます。 この結果、等価でない複数の要素間で順序が付けられます。 テクニカル ノートでは、比較関数は、数学上の標準的な意味で厳密弱順序を発生させる二項述語であると示されています。  
  
 Priority_queue 用の適切な基になるコンテナー クラスを含める [deque クラス](../standard-library/deque-class.md) と既定 [vector クラス](../standard-library/vector-class.md) またはその他のシーケンス コンテナーの操作をサポートする `front`, 、`push_back`, 、および `pop_back` とランダム アクセス反復子。 基になるコンテナー クラスは、コンテナー アダプター内にカプセル化されます。コンテナー アダプターは、限られた一連のシーケンス コンテナーのメンバーの関数のみをパブリック インターフェイスとして公開します。  
  
 要素を追加してから要素を削除する、 `priority_queue` 対数複雑さがある両方です。 内の要素へのアクセス、 `priority_queue` 一定の複雑さを持ちます。  
  
 STL によって定義されたコンテナー アダプターの 3 つの種類があります。 スタック、キュー、および priority_queue です。 それぞれに、標準的なデータ構造を正確に制御されたインターフェイスを提供するいくつかの基になるコンテナー クラスの機能が制限されます。  
  
-    [Stack クラス](../standard-library/stack-class.md) 後入れ先出し (LIFO) のデータ構造をサポートしています。 思い描くのに助けとなるのは、積み重ねられた皿です。 要素 (皿) は、積み重ねの一番上からのみ挿入、検査、または削除できます。積み重ねの一番上に相当するのは、基本のコンテナーの末尾にある最後の要素です。 一番上の要素にのみアクセスできる制限があることが、stack クラスを使用する理由です。  
  
-    [Queue クラス](../standard-library/queue-class.md) では、先入れ先出し (FIFO) のデータ構造をサポートしています。 思い描くのに助けとなるのは、銀行の窓口で並んでいる人です。 要素 (人々) は、列の一番後ろに追加され、列の一番前から取り除くことができます。 列の一番前と一番後ろの両方を検査できます。 この方法でフロント エンドとバックエンドの要素のみへのアクセスに制限は、キューのクラスを使用する理由です。  
  
-   Priority_queue クラスは、上端の位置を最大の要素が常に、その要素を並べ替えます。 要素の挿入、および先頭の要素の検査と削除をサポートしています。 思い描くのに助けとなるのは、年齢、身長、またはその他の条件によって整列している人です。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[priority_queue](#priority_queue__priority_queue)|構築、 `priority_queue` が空または基本コンテナー オブジェクトまたはその他の範囲のコピーである `priority_queue`です。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[container_type](#priority_queue__container_type)|`priority_queue` によって適合されるように、基本のコンテナーを提供する型。|  
|[size_type](#priority_queue__size_type)|`priority_queue` 内の要素の数を表すことができる符号なし整数型。|  
|[value_type](#priority_queue__value_type)|`priority_queue` 内に要素として格納されるオブジェクトの種類を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[空](#priority_queue__empty)|`priority_queue` が空かどうかをテストします。|  
|[pop](#priority_queue__pop)|最大の要素を削除、 `priority_queue` 最上位からです。|  
|[プッシュ](#priority_queue__push)|演算子のシーケンスから要素の優先順位に基づいて、優先順位キューに要素を追加 < します。|  
|[サイズ](#priority_queue__size)|`priority_queue` 内の要素数を返します。|  
|[ページのトップへ](#priority_queue__top)|返します。 の上部にある最大の要素への const の参照、 `priority_queue`です。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \< キュー>  
  
 **名前空間:** std  
  
##  <a name="a-namepriorityqueuecontainertypea-priorityqueuecontainertype"></a><a name="priority_queue__container_type"></a>  priority_queue::container_type  
 合わせて実行する基本のコンテナーを提供する型。  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター `Container` のシノニムです。 STL シーケンス コンテナー クラスの deque と既定クラス vector、priority_queue オブジェクトの基本のコンテナーとして使用するための要件を満たします。 ユーザー定義型の要件を満たすこともできます。  
  
 詳細については `Container`, の「解説」セクションを参照してください、 [priority_queue クラス](../standard-library/priority-queue-class.md) トピックです。  
  
### <a name="example"></a>例  
  例を参照してください [priority_queue](#priority_queue__priority_queue) を宣言および使用する方法の例については `container_type`です。  
  
##  <a name="a-namepriorityqueueemptya-priorityqueueempty"></a><a name="priority_queue__empty"></a>  priority_queue::empty  
 Priority_queue が空かどうか。  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 **true** 、priority_queue が空である場合 **false** 、priority_queue が空でない場合。  
  
### <a name="example"></a>例  
  
```  
// pqueue_empty.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares priority_queues with default deque base container  
   priority_queue <int> q1, s2;  
  
   q1.push( 1 );  
  
   if ( q1.empty( ) )  
      cout << "The priority_queue q1 is empty." << endl;  
   else  
      cout << "The priority_queue q1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The priority_queue s2 is empty." << endl;  
   else  
      cout << "The priority_queue s2 is not empty." << endl;  
}  
```  
  
```Output  
The priority_queue q1 is not empty.  
The priority_queue s2 is empty.  
```  
  
##  <a name="a-namepriorityqueuepopa-priorityqueuepop"></a><a name="priority_queue__pop"></a>  priority_queue::pop  
 上端の位置から、priority_queue で最も大きな要素を削除します。  
  
```  
void pop();
```  
  
### <a name="remarks"></a>コメント  
 メンバー関数を適用するには、priority_queue を空にすることはできません。 Priority_queue の一番上は常に、コンテナーの最大の要素によって占有されています。  
  
### <a name="example"></a>例  
  
```  
// pqueue_pop.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue <int> q1, s2;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   priority_queue <int>::size_type i, iii;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
  
   q1.pop( );  
  
   iii = q1.size( );  
   cout << "After a pop, the priority_queue length is "   
        << iii << "." << endl;  
  
   const int& iv = q1.top( );  
   cout << "After a pop, the element at the top of the "  
        << "priority_queue is " << iv << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
After a pop, the priority_queue length is 2.  
After a pop, the element at the top of the priority_queue is 20.  
```  
  
##  <a name="a-namepriorityqueuepriorityqueuea-priorityqueuepriorityqueue"></a><a name="priority_queue__priority_queue"></a>  priority_queue::priority_queue  
 空か、または別 priority_queue 基本コンテナー オブジェクトの範囲のコピーである、priority_queue を構築します。  
  
```  
priority_queue();

explicit priority_queue(const Traits&_comp);

priority_queue(const Traits&_comp, const container_type& _Cont);

priority_queue(const priority_queue& right);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last, const Traits&_comp);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last, const Traits&_comp, const container_type& _Cont);
```  
  
### <a name="parameters"></a>パラメーター  
 *_ コンポジションします。*  
 型の比較関数 **constTraits** 基本コンテナーの機能を比較する既定値は priority_queue で要素の並べ替えに使用します。  
  
 `_Cont`  
 構築された priority_queue のコピーであることに元の基本コンテナーです。  
  
 ` right`  
 構築されたセットのコピーであることに元の priority_queue です。  
  
 ` first`  
 コピーする要素範囲内の最初の要素の位置。  
  
 ` last`  
 コピーする要素範囲を超える最初の要素の位置。  
  
### <a name="remarks"></a>コメント  
 最初の 3 つのコンス トラクターのそれぞれの指定、2 つ目も型を指定する比較関数の空初期 priority_queue ( ` comp`) 要素を第 3 に明示的に指定の順序を確立するために使用する、 `container_type` ( `_Cont`) 使用します。 キーワード **明示的な** 特定の種類の自動型変換を抑制します。  
  
 4 番目のコンス トラクター、priority_queue のコピーを指定する ` right`です。  
  
 最後の 3 つのコンス トラクターは、範囲をコピーします。 [ * 第 1、最終*) のいずれかのコンテナー クラスの比較関数の種類を指定することになるほど priority_queue を初期化するために値を使用して **特徴 (traits)** と `container_type`です。  
  
### <a name="example"></a>例  
  
```  
// pqueue_ctor.cpp  
// compile with: /EHsc  
#include <queue>  
#include <vector>  
#include <deque>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The first member function declares priority_queue  
   // with a default vector base container  
   priority_queue <int> q1;  
   cout << "q1 = ( ";  
   while ( !q1.empty( ) )  
   {  
      cout << q1.top( ) << " ";  
      q1.pop( );  
   }  
   cout << ")" << endl;  
  
   // Explicitly declares a priority_queue with nondefault  
   // deque base container  
   priority_queue <int, deque <int> > q2;  
   q2.push( 5 );  
   q2.push( 15 );  
   q2.push( 10 );  
   cout << "q2 = ( ";  
   while ( !q2.empty( ) )  
   {  
      cout << q2.top( ) << " ";  
      q2.pop( );  
   }  
   cout << ")" << endl;  
  
   // This method of printing out the elements of a priority_queue  
   // removes the elements from the priority queue, leaving it empty  
   cout << "After printing, q2 has " << q2.size( ) << " elements." << endl;  
  
   // The third member function declares a priority_queue   
   // with a vector base container and specifies that the comparison   
   // function greater is to be used for ordering elements  
   priority_queue <int, vector<int>, greater<int> > q3;  
   q3.push( 2 );  
   q3.push( 1 );  
   q3.push( 3 );  
   cout << "q3 = ( ";  
   while ( !q3.empty( ) )  
   {  
      cout << q3.top( ) << " ";  
      q3.pop( );  
   }  
   cout << ")" << endl;  
  
   // The fourth member function declares a priority_queue and  
   // initializes it with elements copied from another container:  
   // first, inserting elements into q1, then copying q1 elements into q4  
   q1.push( 100 );  
   q1.push( 200 );  
   priority_queue <int> q4( q1 );  
   cout << "q4 = ( ";     
   while ( !q4.empty( ) )  
   {  
      cout << q4.top( ) << " ";  
      q4.pop( );  
   }  
   cout << ")" << endl;  
  
   // Creates an auxiliary vector object v5 to be used to initialize q5  
   vector <int> v5;  
   vector <int>::iterator v5_Iter;  
   v5.push_back( 10 );  
   v5.push_back( 30 );  
   v5.push_back( 20 );  
   cout << "v5 = ( " ;  
   for ( v5_Iter = v5.begin( ) ; v5_Iter != v5.end( ) ; v5_Iter++ )  
      cout << *v5_Iter << " ";  
   cout << ")" << endl;  
  
   // The fifth member function declares and  
   // initializes a priority_queue q5 by copying the  
   // range v5[ first,  last) from vector v5  
   priority_queue <int> q5( v5.begin( ), v5.begin( ) + 2 );  
   cout << "q5 = ( ";  
   while ( !q5.empty( ) )  
   {  
      cout << q5.top( ) << " ";  
      q5.pop( );  
   }  
   cout << ")" << endl;  
  
   // The sixth member function declares a priority_queue q6  
   // with a comparison function greater and initializes q6  
   // by copying the range v5[ first,  last) from vector v5  
   priority_queue <int, vector<int>, greater<int> >   
      q6( v5.begin( ), v5.begin( ) + 2 );  
   cout << "q6 = ( ";  
   while ( !q6.empty( ) )  
   {  
      cout << q6.top( ) << " ";  
      q6.pop( );  
   }  
   cout << ")" << endl;  
}  
```  
  
##  <a name="a-namepriorityqueuepusha-priorityqueuepush"></a><a name="priority_queue__push"></a>  priority_queue::push  
 演算子のシーケンスから要素の優先順位に基づいて、優先順位キューに要素を追加 < します。  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>パラメーター  
 ` val`  
 Priority_queue の先頭に追加する要素。  
  
### <a name="remarks"></a>コメント  
 Priority_queue の一番上は、コンテナーの最大の要素によって占有されていた位置です。  
  
### <a name="example"></a>例  
  
```  
// pqueue_push.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue<int> q1;  
  
   q1.push( 10 );  
   q1.push( 30 );  
   q1.push( 20 );  
  
   priority_queue<int>::size_type i;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
```  
  
##  <a name="a-namepriorityqueuesizea-priorityqueuesize"></a><a name="priority_queue__size"></a>  priority_queue::size  
 Priority_queue 要素の数を返します。  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>戻り値  
 現在、priority_queue の長さ。  
  
### <a name="example"></a>例  
  
```  
// pqueue_size.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue <int> q1, q2;  
   priority_queue <int>::size_type i;  
  
   q1.push( 1 );  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   q1.push( 2 );  
   i = q1.size( );  
   cout << "The priority_queue length is now " << i << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 1.  
The priority_queue length is now 2.  
```  
  
##  <a name="a-namepriorityqueuesizetypea-priorityqueuesizetype"></a><a name="priority_queue__size_type"></a>  priority_queue::size_type  
 符号なし整数型、priority_queue 内の要素の数を表すことができます。  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>コメント  
 型のシノニムは、 `size_type` 、priority_queue によって採用基本コンテナーです。  
  
### <a name="example"></a>例  
  例を参照してください [サイズ](#priority_queue__size) を宣言および使用する方法の例については `size_type`です。  
  
##  <a name="a-namepriorityqueuetopa-priorityqueuetop"></a><a name="priority_queue__top"></a>  priority_queue::top  
 priority_queue の最上位にある最大要素への const 参照を返します。  
  
```  
const_reference top() const;
```  
  
### <a name="return-value"></a>戻り値  
 によって決定される最大の要素への参照、 **特徴 (traits)** 、priority_queue のオブジェクトを使用して機能します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を適用するには、priority_queue を空にすることはできません。  
  
### <a name="example"></a>例  
  
```  
// pqueue_top.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue<int> q1;  
  
   q1.push( 10 );  
   q1.push( 30 );  
   q1.push( 20 );  
  
   priority_queue<int>::size_type i;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
```  
  
##  <a name="a-namepriorityqueuevaluetypea-priorityqueuevaluetype"></a><a name="priority_queue__value_type"></a>  priority_queue::value_type  
 Priority_queue 内の要素として格納されるオブジェクトの種類を表す型。  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>コメント  
 型のシノニムは、 `value_type` 、priority_queue によって採用基本コンテナーです。  
  
### <a name="example"></a>例  
  
```  
// pqueue_value_type.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares priority_queues with default deque base container  
   priority_queue<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   priority_queue<int> q1;  
   q1.push( AnInt );  
   cout << "The element at the top of the priority_queue is "  
        << q1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the priority_queue is 69.  
```  
  
## <a name="see-also"></a>「  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)

