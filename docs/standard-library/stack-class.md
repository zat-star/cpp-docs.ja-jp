---
title: "stack クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::stack"
  - "std.stack"
  - "stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "スタック、stack クラス"
  - "stack クラス"
ms.assetid: 02151c1e-eab0-41b8-be94-a839ead78ecf
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# stack クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

基になるコンテナー型に最も新しく追加された要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。 stack クラスは、スタック操作のみがコンテナーで実行されることが明確であることが重要な場合に使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Type, class Container= deque <Type>>  
class stack  
```  
  
#### <a name="parameters"></a>パラメーター  
 *Type*  
 スタックに格納される要素のデータ型。  
  
 `Container`  
 スタックを実装するために使用する基になるコンテナーの型。 既定値は、クラス `deque`*\< 種類>*します。  
  
## <a name="remarks"></a>コメント  
 クラスの要素 **型** 最初のテンプレートで規定されているスタック オブジェクトのパラメーターが指定と同じ意味 [value_type](#stack__value_type) 基になるコンテナー クラス内の要素の型を一致させる必要があります **コンテナー** 、2 番目のテンプレート パラメーターで規定します。  **型** その型のオブジェクトをコピーして、その型の変数に値を割り当てることができるように、割り当てることがあります。  
  
 スタックの適切なの基になるコンテナー クラスには、 [deque](../standard-library/deque-class.md), 、[list クラス](../standard-library/list-class.md), と [vector クラス](../standard-library/vector-class.md), 、またはその他のシーケンス コンテナーの操作をサポートする **戻る**, 、`push_back`, 、および `pop_back`です。 基になるコンテナー クラスは、コンテナー アダプター内にカプセル化されます。コンテナー アダプターは、限られた一連のシーケンス コンテナーのメンバーの関数のみをパブリック インターフェイスとして公開します。  
  
 スタック オブジェクトは比較可能な場合に等しいかどうかと場合にのみ、クラスの要素 **型** は等しいかどうかを比較し、以下の場合にのみと同等の場合よりもクラスの要素 **型** が小さい-匹敵するよりもします。  
  
-   stack クラスは、後入れ先出し (LIFO) のデータ構造をサポートしています。 思い描くのに助けとなるのは、積み重ねられた皿です。 要素 (皿) は、積み重ねの一番上からのみ挿入、検査、または削除できます。積み重ねの一番上に相当するのは、基本のコンテナーの末尾にある最後の要素です。 一番上の要素にのみアクセスできる制限があることが、stack クラスを使用する理由です。  
  
-    [Queue クラス](../standard-library/queue-class.md) では、先入れ先出し (FIFO) のデータ構造をサポートしています。 思い描くのに助けとなるのは、銀行の窓口で並んでいる人です。 要素 (人々) は、列の一番後ろに追加され、列の一番前から取り除くことができます。 列の一番前と一番後ろの両方を検査できます。 このように一番前と一番後ろの要素にのみアクセスできる制限があることが、queue クラスを使用する理由です。  
  
-    [Priority_queue クラス](../standard-library/priority-queue-class.md) が常に最大の要素上の位置にその要素を並べ替えます。 要素の挿入、および先頭の要素の検査と削除をサポートしています。 思い描くのに助けとなるのは、年齢、身長、またはその他の条件によって整列している人です。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[スタック](#stack__stack)|空であるか、基本のコンテナー オブジェクトのコピーである `stack` を構築します。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[container_type](#stack__container_type)|`stack` によって適合されるように、基本のコンテナーを提供する型。|  
|[size_type](#stack__size_type)|`stack` 内の要素の数を表すことができる符号なし整数型。|  
|[value_type](#stack__value_type)|`stack` 内に要素として格納されるオブジェクトの種類を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[空](#stack__empty)|`stack` が空かどうかをテストします。|  
|[pop](#stack__pop)|`stack` の先頭から要素を削除します。|  
|[プッシュ](#stack__push)|`stack` の先頭に要素を追加します。|  
|[サイズ](#stack__size)|`stack` 内の要素数を返します。|  
|[ページのトップへ](#stack__top)|`stack` の先頭にある要素への参照を返します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \< スタック>  
  
 **名前空間:** std  
  
##  <a name="a-namestackcontainertypea-stackcontainertype"></a><a name="stack__container_type"></a>  stack::container_type  
 合わせて実行する基本のコンテナーを提供する型。  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター `Container` のシノニムです。 次の 3 つのすべての STL シーケンス コンテナー クラス: vector クラス、list クラス、および既定のクラスの deque: スタック オブジェクトの基本のコンテナーとして使用するための要件を満たしています。 これらの要件を満たすユーザー定義の型も使用できます。  
  
 詳細については `Container`, の「解説」セクションを参照してください、 [stack クラス](../standard-library/stack-class.md) トピックです。  
  
### <a name="example"></a>例  
  例を参照してください [stack::stack](#stack__stack) を宣言および使用する方法の例については `container_type`です。  
  
##  <a name="a-namestackemptya-stackempty"></a><a name="stack__empty"></a>  stack::empty  
 スタックが空かどうか。  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 **true** スタックが空である場合 **false** スタックが空でない場合。  
  
### <a name="example"></a>例  
  
```  
// stack_empty.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack <int> s1, s2;  
  
   s1.push( 1 );  
  
   if ( s1.empty( ) )  
      cout << "The stack s1 is empty." << endl;  
   else  
      cout << "The stack s1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The stack s2 is empty." << endl;  
   else  
      cout << "The stack s2 is not empty." << endl;  
}  
```  
  
```Output  
The stack s1 is not empty.  
The stack s2 is empty.  
```  
  
##  <a name="a-namestackpopa-stackpop"></a><a name="stack__pop"></a>  stack::pop  
 スタックの先頭から要素を削除します。  
  
```  
void pop();
```  
  
### <a name="remarks"></a>コメント  
 スタックは、空ではないメンバー関数の適用先である必要があります。 スタックの一番上は最近追加された要素によって占有されている位置で、コンテナーの末尾にある最後の要素です。  
  
### <a name="example"></a>例  
  
```  
// stack_pop.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
  
   s1.pop( );  
  
   i = s1.size( );  
   cout << "After a pop, the stack length is "   
        << i << "." << endl;  
  
   i = s1.top( );  
   cout << "After a pop, the element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
After a pop, the stack length is 2.  
After a pop, the element at the top of the stack is 20.  
```  
  
##  <a name="a-namestackpusha-stackpush"></a><a name="stack__push"></a>  stack::push  
 スタックの最上位の末尾に要素を追加します。  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>パラメーター  
 ` val`  
 スタックの先頭に追加する要素。  
  
### <a name="remarks"></a>コメント  
 スタックの一番上は最近追加された要素によって占有されている位置で、コンテナーの末尾にある最後の要素です。  
  
### <a name="example"></a>例  
  
```  
// stack_push.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
```  
  
##  <a name="a-namestacksizea-stacksize"></a><a name="stack__size"></a>  stack::size  
 スタック内の要素の数を返します。  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>戻り値  
 現在、スタックの長さ。  
  
### <a name="example"></a>例  
  
```  
// stack_size.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
   stack <int>::size_type i;  
  
   s1.push( 1 );  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   s1.push( 2 );  
   i = s1.size( );  
   cout << "The stack length is now " << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 1.  
The stack length is now 2.  
```  
  
##  <a name="a-namestacksizetypea-stacksizetype"></a><a name="stack__size_type"></a>  stack::size_type  
 スタック内の要素の数を表すことができる符号なし整数型。  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>コメント  
 型のシノニムは、 `size_type` 、基本適合コンテナーのスタックによってです。  
  
### <a name="example"></a>例  
  例を参照してください [サイズ](#stack__size) を宣言および使用する方法の例については `size_type`です。  
  
##  <a name="a-namestackstacka-stackstack"></a><a name="stack__stack"></a>  stack::stack  
 空またはコンテナーの基本クラスのコピーであるスタックを構築します。  
  
```  
stack();

explicit stack(const container_type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 構築されたスタックのコピーであることに元のコンテナーです。  
  
### <a name="example"></a>例  
  
```  
// stack_stack.cpp  
// compile with: /EHsc  
#include <stack>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares stack with default deque base container  
   stack <char> dsc1;  
  
   //Explicitly declares a stack with deque base container  
   stack <char, deque<char> > dsc2;  
  
   // Declares a stack with vector base containers  
   stack <int, vector<int> > vsi1;  
  
   // Declares a stack with list base container  
   stack <int, list<int> > lsi;  
  
   // The second member function copies elements from a container  
   vector<int> v1;  
   v1.push_back( 1 );  
   stack <int, vector<int> > vsi2( v1 );  
   cout << "The element at the top of stack vsi2 is "  
        << vsi2.top( ) << "." << endl;  
}  
```  
  
```Output  
The element at the top of stack vsi2 is 1.  
```  
  
##  <a name="a-namestacktopa-stacktop"></a><a name="stack__top"></a>  stack::top  
 スタックの上部にある要素への参照を返します。  
  
```  
reference top();

const_reference top() const;
```  
  
### <a name="return-value"></a>戻り値  
 スタックの上部にあるコンテナーの最後の要素への参照。  
  
### <a name="remarks"></a>コメント  
 スタックは、空ではないメンバー関数の適用先である必要があります。 スタックの一番上は最近追加された要素によって占有されている位置で、コンテナーの末尾にある最後の要素です。  
  
 場合の戻り値 **上部** に割り当てられている、 `const_reference`, 、スタック オブジェクトは変更できません。 場合の戻り値 **上部** に割り当てられている、 **参照**, 、スタック オブジェクトを変更できます。  
  
### <a name="example"></a>例  
  
```  
// stack_top.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 1 );  
   s1.push( 2 );  
  
   int& i = s1.top( );  
   const int& ii = s1.top( );  
  
   cout << "The top integer of the stack s1 is "  
        << i << "." << endl;  
   i--;  
   cout << "The next integer down is "<< ii << "." << endl;  
}  
```  
  
```Output  
The top integer of the stack s1 is 2.  
The next integer down is 1.  
```  
  
##  <a name="a-namestackvaluetypea-stackvaluetype"></a><a name="stack__value_type"></a>  stack::value_type  
 スタック内の要素として格納されるオブジェクトの型を表す型。  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>コメント  
 型のシノニムは、 `value_type` 、基本適合コンテナーのスタックによってです。  
  
### <a name="example"></a>例  
  
```  
// stack_value_type.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   stack<int> s1;  
   s1.push( AnInt );  
   cout << "The element at the top of the stack is "  
        << s1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the stack is 69.  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)

