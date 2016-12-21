---
title: "queue クラス | Microsoft Docs"
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
  - "std.queue"
  - "std::queue"
  - "queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queue クラス"
ms.assetid: 28c20ab0-3a72-4185-9e0f-5a44eea0e204
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# queue クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

フロント エンドとバックエンドの要素へのアクセスを制限することによって基になるコンテナー型の機能の制限を提供するテンプレートのコンテナー アダプター クラス。 要素したりすることで追加前面から、削除、キューの先頭または末尾に要素を検査できます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Type, class Container = deque <Type>>  
class queue  
```  
  
#### <a name="parameters"></a>パラメーター  
 *Type*  
 キューに格納される要素のデータ型  
  
 `Container`  
 キューを実装するために使用する基になるコンテナーの型。  
  
## <a name="remarks"></a>コメント  
 クラスの要素 **型** 最初のテンプレートで規定されている、キュー オブジェクトのパラメーターが指定と同じ意味 [value_type](#queue__value_type) 基になるコンテナー クラス内の要素の型を一致させる必要があります **コンテナー** 、2 番目のテンプレート パラメーターで規定します。  **型** その型のオブジェクトをコピーして、その型の変数に値を割り当てることができるように、割り当てることがあります。  
  
 キュー用の適切な基になるコンテナー クラスを含める [deque](../standard-library/deque-class.md) と [リスト](../standard-library/list-class.md), 、またはその他のシーケンス コンテナーの操作をサポートする `front`, 、**戻る**, 、`push_back`, と `pop_front`です。 基になるコンテナー クラスは、コンテナー アダプター内にカプセル化されます。コンテナー アダプターは、限られた一連のシーケンス コンテナーのメンバーの関数のみをパブリック インターフェイスとして公開します。  
  
 キュー オブジェクトは比較可能な場合に等しいかどうかと場合にのみ、クラスの要素 **型** は等しいかどうかを比較、および要素が小さい-場合にのみと同等の場合よりもクラスの要素 **型** が小さい-より相当します。  
  
 STL によって定義されたコンテナー アダプターの 3 つの種類があります。 スタック、キュー、および priority_queue です。 それぞれに、標準的なデータ構造を正確に制御されたインターフェイスを提供するいくつかの基になるコンテナー クラスの機能が制限されます。  
  
-    [Stack クラス](../standard-library/stack-class.md) 後入れ先出し (LIFO) のデータ構造をサポートしています。 思い描くのに助けとなるのは、積み重ねられた皿です。 要素 (皿) は、積み重ねの一番上からのみ挿入、検査、または削除できます。積み重ねの一番上に相当するのは、基本のコンテナーの末尾にある最後の要素です。 一番上の要素にのみアクセスできる制限があることが、stack クラスを使用する理由です。  
  
-   Queue クラスには、先入れ先出し (FIFO) のデータ構造がサポートしています。 思い描くのに助けとなるのは、銀行の窓口で並んでいる人です。 要素 (人々) は、列の一番後ろに追加され、列の一番前から取り除くことができます。 列の一番前と一番後ろの両方を検査できます。 この方法でフロント エンドとバックエンドの要素のみへのアクセスに制限は、キューのクラスを使用する理由です。  
  
-    [Priority_queue クラス](../standard-library/priority-queue-class.md) が常に最大の要素上の位置にその要素を並べ替えます。 要素の挿入、および先頭の要素の検査と削除をサポートしています。 思い描くのに助けとなるのは、年齢、身長、またはその他の条件によって整列している人です。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[キュー](#queue__queue)|空であるか、基本のコンテナー オブジェクトのコピーである `queue` を構築します。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[container_type](#queue__container_type)|調整する基本のコンテナーを提供する型、 `queue`です。|  
|[size_type](#queue__size_type)|`queue` 内の要素の数を表すことができる符号なし整数型。|  
|[value_type](#queue__value_type)|`queue` 内に要素として格納されるオブジェクトの種類を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[戻る](#queue__back)|参照が最後に、最も最近追加の背面にある要素を返します。、 `queue`です。|  
|[空](#queue__empty)|`queue` が空かどうかをテストします。|  
|[前面](#queue__front)|先頭にある最初の要素への参照を返す、 `queue`です。|  
|[pop](#queue__pop)|先頭から要素を削除、 `queue`です。|  
|[プッシュ](#queue__push)|背面に要素を追加、 `queue`です。|  
|[サイズ](#queue__size)|`queue` 内の要素数を返します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \< キュー>  
  
 **名前空間:** std  
  
##  <a name="a-namequeuebacka-queueback"></a><a name="queue__back"></a>  queue::back  
 参照が最後に、最も最近追加キューの末尾の要素を返します。  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>戻り値  
 キューの最後の要素。 キューが空の場合、戻り値は未定義です。  
  
### <a name="remarks"></a>コメント  
 場合の戻り値 **戻る** に割り当てられている、 `const_reference`, 、キュー オブジェクトは変更できません。 場合の戻り値 **戻る** に割り当てられている、 **参照**, 、キュー オブジェクトを変更できます。  
  
 _SECURE_SCL 1 でコンパイル、空のキュー内の要素にアクセスしようとすると、ランタイム エラーが発生します。  詳細については、「 [Checked Iterators](../standard-library/checked-iterators.md) 」を参照してください。  
  
### <a name="example"></a>例  
  
```  
// queue_back.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 11 );  
  
   int& i = q1.back( );  
   const int& ii = q1.front( );  
  
   cout << "The integer at the back of queue q1 is " << i   
        << "." << endl;  
   cout << "The integer at the front of queue q1 is " << ii   
        << "." << endl;  
}  
```  
  
##  <a name="a-namequeuecontainertypea-queuecontainertype"></a><a name="queue__container_type"></a>  queue::container_type  
 合わせて実行する基本のコンテナーを提供する型。  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター `Container` のシノニムです。 2 つの STL シーケンス コンテナー クラス: リストのクラスと既定の deque クラス-キュー オブジェクトの基本のコンテナーとして使用するための要件を満たしています。 ユーザー定義型の要件を満たすこともできます。  
  
 詳細については `Container`, の「解説」セクションを参照してください、 [queue クラス](../standard-library/queue-class.md) トピックです。  
  
### <a name="example"></a>例  
  例を参照してください [キュー](#queue__queue) を宣言および使用する方法の例については `container_type`です。  
  
##  <a name="a-namequeueemptya-queueempty"></a><a name="queue__empty"></a>  queue::empty  
 キューが空かどうか。  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 **true** キューが空である場合 **false** キューが空でない場合。  
  
### <a name="example"></a>例  
  
```  
// queue_empty.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
   // Declares queues with default deque base container  
   queue <int> q1, q2;  
  
   q1.push( 1 );  
  
   if ( q1.empty( ) )  
      cout << "The queue q1 is empty." << endl;  
   else  
      cout << "The queue q1 is not empty." << endl;  
  
   if ( q2.empty( ) )  
      cout << "The queue q2 is empty." << endl;  
   else  
      cout << "The queue q2 is not empty." << endl;  
}  
```  
  
```Output  
The queue q1 is not empty.  
The queue q2 is empty.  
```  
  
##  <a name="a-namequeuefronta-queuefront"></a><a name="queue__front"></a>  queue::front  
 キューの先頭にある最初の要素への参照を返します。  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>戻り値  
 キューの最初の要素。 キューが空の場合、戻り値は未定義です。  
  
### <a name="remarks"></a>コメント  
 場合の戻り値 `front` に割り当てられている、 `const_reference`, 、キュー オブジェクトは変更できません。 場合の戻り値 `front` に割り当てられている、 **参照**, 、キュー オブジェクトを変更できます。  
  
 メンバー関数を返します、 **参照** 被制御シーケンスの最初の要素を空にすることです。  
  
 _SECURE_SCL 1 でコンパイル、空のキュー内の要素にアクセスしようとすると、ランタイム エラーが発生します。  詳細については、「 [Checked Iterators](../standard-library/checked-iterators.md) 」を参照してください。  
  
### <a name="example"></a>例  
  
```  
// queue_front.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   int& ii = q1.back( );  
   int& iii = q1.front( );  
  
   cout << "The integer at the back of queue q1 is " << ii   
        << "." << endl;  
   cout << "The integer at the front of queue q1 is " << iii   
        << "." << endl;  
}  
```  
  
##  <a name="a-namequeuepopa-queuepop"></a><a name="queue__pop"></a>  queue::pop  
 キューの先頭から要素を削除します。  
  
```  
void pop();
```  
  
### <a name="remarks"></a>コメント  
 キューは、メンバー関数の適用先空でないである必要があります。 キューの先頭は最近追加された要素によって占有されている位置で、コンテナーの末尾にある最後の要素です。  
  
### <a name="example"></a>例  
  
```  
// queue_pop.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, s2;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   i = q1.front( );  
   cout << "The element at the front of the queue is "  
        << i << "." << endl;  
  
   q1.pop( );  
  
   i = q1.size( );  
   cout << "After a pop the queue length is "   
        << i << "." << endl;  
  
   i = q1. front ( );  
   cout << "After a pop, the element at the front of the queue is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 3.  
The element at the front of the queue is 10.  
After a pop the queue length is 2.  
After a pop, the element at the front of the queue is 20.  
```  
  
##  <a name="a-namequeuepusha-queuepush"></a><a name="queue__push"></a>  queue::push  
 キューの末尾に要素を追加します。  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>パラメーター  
 `val`  
 キューの末尾に追加する要素。  
  
### <a name="remarks"></a>コメント  
 キューの末尾は最近追加された要素によって占有されている位置で、コンテナーの末尾にある最後の要素です。  
  
### <a name="example"></a>例  
  
```  
// queue_push.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   i = q1.front( );  
   cout << "The element at the front of the queue is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 3.  
The element at the front of the queue is 10.  
```  
  
##  <a name="a-namequeuequeuea-queuequeue"></a><a name="queue__queue"></a>  queue::queue  
 空か、基本コンテナー オブジェクトのコピーであるキューを作成します。  
  
```  
queue();

explicit queue(const container_type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
  **Const** が、構築されたキューのコピーであることに元のコンテナーです。  
  
### <a name="remarks"></a>コメント  
 キューの既定の基本コンテナーは、deque です。 基本のコンテナーとしてリストを指定することもできますが、必要があるために、ベクトルを指定することはできません `pop_front` メンバー関数。  
  
### <a name="example"></a>例  
  
```  
// queue_queue.cpp  
// compile with: /EHsc  
#include <queue>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queue with default deque base container  
   queue <char> q1;  
  
   // Explicitly declares a queue with deque base container  
   queue <char, deque<char> > q2;  
  
   // These lines don't cause an error, even though they  
   // declares a queue with a vector base container  
   queue <int, vector<int> > q3;  
   q3.push( 10 );  
   // but the following would cause an error because vector has   
   // no pop_front member function  
   // q3.pop( );  
  
   // Declares a queue with list base container  
   queue <int, list<int> > q4;  
  
   // The second member function copies elements from a container  
   list<int> li1;  
   li1.push_back( 1 );  
   li1.push_back( 2 );  
   queue <int, list<int> > q5( li1 );  
   cout << "The element at the front of queue q5 is "  
        << q5.front( ) << "." << endl;  
   cout << "The element at the back of queue q5 is "  
        << q5.back( ) << "." << endl;  
}  
```  
  
```Output  
The element at the front of queue q5 is 1.  
The element at the back of queue q5 is 2.  
```  
  
##  <a name="a-namequeuesizea-queuesize"></a><a name="queue__size"></a>  queue::size  
 キュー内の要素の数を返します。  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>戻り値  
 現在、キューの長さ。  
  
### <a name="example"></a>例  
  
```  
// queue_size.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2;  
   queue <int>::size_type i;  
  
   q1.push( 1 );  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   q1.push( 2 );  
   i = q1.size( );  
   cout << "The queue length is now " << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 1.  
The queue length is now 2.  
```  
  
##  <a name="a-namequeuesizetypea-queuesizetype"></a><a name="queue__size_type"></a>  queue::size_type  
 キュー内の要素の数を表すことができる符号なし整数型。  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>コメント  
 型のシノニムは、 `size_type` の基本のコンテナー、キューが調整されます。  
  
### <a name="example"></a>例  
  例を参照してください [queue::front](#queue__front) を宣言および使用する方法の例については `size_type`です。  
  
##  <a name="a-namequeuevaluetypea-queuevaluetype"></a><a name="queue__value_type"></a>  queue::value_type  
 キュー内の要素として格納されるオブジェクトの型を表す型。  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>コメント  
 型のシノニムは、 `value_type` の基本のコンテナー、キューが調整されます。  
  
### <a name="example"></a>例  
  
```  
// queue_value_type.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
   // Declares queues with default deque base container  
   queue<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   queue<int> q1;  
   q1.push(AnInt);  
   cout << "The element at the front of the queue is "  
        << q1.front( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the front of the queue is 69.  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)

