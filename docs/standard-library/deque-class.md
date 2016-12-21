---
title: "deque クラス | Microsoft Docs"
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
  - "std.deque"
  - "deque"
  - "std::deque"
  - "deque/std::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "deque クラスの概要の deque クラス"
  - "deque クラス"
ms.assetid: 64842ee5-057a-4063-8c16-4267a0332584
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# deque クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

特定の型の要素をベクターのような線形の配置に整列し、任意の要素への高速なランダム アクセス、およびコンテナーの後ろでの効率的な挿入と削除を行えるようにします。 ただし、ベクターとは異なり、`deque` クラスは、コンテナーの前での効率的な挿入と削除もサポートします。  
  
## <a name="syntax"></a>構文  
  
```unstlib  
template <class Type,   
    class Allocator =allocator<Type>>  
class deque  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Type`  
 deque に格納される要素のデータ型。  
  
 `Allocator`  
 メモリの deque の割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は **allocator \< 種類>***します。*  
  
## <a name="remarks"></a>コメント  
 一般的に、コンテナー型の選択は、アプリケーションにおいて必要な検索および挿入の種類に基づいている必要があります。 [ベクトル](../standard-library/vector-class.md) 任意の要素へのランダム アクセスが非常に高価であり、要素の挿入または削除はときに、シーケンスを管理するための推奨されるコンテナーをする必要がありますがシーケンスの最後に必要です。 リストのコンテナーのパフォーマンスが効率的な場合は、優れた挿入し、シーケンス内で任意の位置における (定数時間) の削除を重視します。 シーケンスの途中でこのような操作を行うには、シーケンス (線形時間) 内の要素数に比例した要素のコピーおよび割り当てが必要になります。  
  
 deque の再割り当ては、メンバー関数がシーケンスの要素を挿入または消去する必要がある場合に発生します。  
  
-   空のシーケンスに要素が挿入されたかを空のシーケンスのままにする要素が消去された場合、以前返された反復子によって [開始](#deque__begin) と [エンド](#deque__end) が無効になります。  
  
-   要素が deque の最初の位置に挿入された場合は、既存の要素を指定するすべての反復子 (参照を除く) が無効になります。  
  
-   要素が、deque の末尾に、挿入されたかどうかは [エンド](#deque__end) とすべての反復子参照がない、無効になる既存の要素を指定します。  
  
-   要素が deque の前で消去された場合は、その反復子と消去された要素へ参照のみが無効になります。  
  
-   最後の要素が deque の末尾から消去された場合は、最後の要素への反復子と消去された要素への参照のみが無効になります。  
  
 それ以外の場合、要素を挿入または消去すると、すべての反復子および参照が無効になります。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[deque](#deque__deque)|構築、 `deque.` の新しい内容を設定する複数のコンス トラクターが用意されて `deque` さまざまな方法で: 空の場合に空の要素の指定した数で読み込む; 移動またはコピーを別の内容を `deque`に 1 つの要素をコピーし、内容をコピーまたは移動、反復子を使用して、;、 `deque`` count` 回です。 一部のコンストラクターでは、要素を作成するためのカスタムの `allocator` を使用できます。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[allocator_type](#deque__allocator_type)|`allocator` オブジェクトの `deque` クラスを表す型。|  
|[const_iterator](#deque__const_iterator)|`deque` 内の要素にアクセスし、読み取ることができるランダム アクセス反復子を `const` として提供する型。|  
|[const_pointer](#deque__const_pointer)|`deque` 内の要素へのポインターを `const.` として提供する型。|  
|[const_reference](#deque__const_reference)|読み取りと他の操作の実行のために、`deque` 内の要素への参照を `const.` として提供する型。|  
|[const_reverse_iterator](#deque__const_reverse_iterator)|`deque` 内の要素にアクセスし、読み取ることができるランダム アクセス反復子を `const` として提供する型。 deque は逆に表示されます。 詳細については、次を参照してください [reverse_iterator クラス。](../standard-library/reverse-iterator-class.md)|  
|[difference_type](#deque__difference_type)|同じ `deque` 内の要素を参照する 2 つのランダム アクセス反復子の違いを提供する型。|  
|[反復子](#deque__iterator)|`deque` 内の任意の要素を読み取り、または変更できるランダム アクセス反復子を提供する型。|  
|[ポインター](#deque__pointer)|`deque` 内の要素へのポインターを提供する型。|  
|[参照](#deque__reference)|`deque` に格納されている要素への参照を提供する型。|  
|[reverse_iterator](#deque__reverse_iterator)|`deque` 内の要素を読み取り、または変更できるランダム アクセス反復子を提供する型。 deque は逆の順序で表示されます。|  
|[size_type](#deque__size_type)|`deque` 内の要素の数をカウントする型。|  
|[value_type](#deque__value_type)|`deque` に格納されているデータ型を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[割り当てる](#deque__assign)|`deque` から要素を消去し、対象の `deque` に要素の新しいシーケンスをコピーします。|  
|[で](#deque__at)|`deque` 内の指定した位置にある要素への参照を返します。|  
|[戻る](#deque__back)|`deque` の最後の要素への参照を返します。|  
|[開始](#deque__begin)|`deque` 内の最初の要素を示すランダム アクセス反復子を返します。|  
|[deque::cbegin](#deque__cbegin)|`deque` 内の最初の要素への定数反復子を返します。|  
|[deque::cend](#deque__cend)|`const` の末尾の次の位置を指し示すランダム アクセス `deque` 反復子を返します。|  
|[オフ](#deque__clear)|`deque` のすべての要素を消去します。|  
|[deque::crbegin](#deque__crbegin)|`deque` 内の最初の要素へのランダム アクセス定数反復子を返します。|  
|[deque::crend](#deque__crend)|`deque` 内の最初の要素へのランダム アクセス定数反復子を返します。|  
|[deque::emplace](#deque__emplace)|指定した位置において、構築された要素を `deque` の適切な場所に挿入します。|  
|[deque::emplace_back](#deque__emplace_back)|構築された要素を `deque` の末尾の適切な場所に追加します。|  
|[deque::emplace_front](#deque__emplace_front)|構築された要素を `deque` の先頭の適切な場所に追加します。|  
|[空](#deque__empty)|`true` に含まれている要素がゼロ個の場合に `deque` を返し、1 つ以上の要素が含まれている場合に `false` を返します。|  
|[終了](#deque__end)|`deque` の末尾の次の位置を指し示すランダム アクセス反復子を返します。|  
|[消去](#deque__erase)|指定した位置から `deque` の要素または要素範囲を削除します。|  
|[前面](#deque__front)|`deque` 内の最初の要素への参照を返します。|  
|[get_allocator](#deque__get_allocator)|`allocator` の構築に使用される `deque` オブジェクトのコピーを返します。|  
|[挿入](#deque__insert)|指定した位置において、`deque` に単一の要素、複数の要素、または要素の範囲を挿入します。|  
|[max_size](#deque__max_size)|`deque` の可能な最大長を返します。|  
|[pop_back](#deque__pop_back)|`deque` の末尾の要素を消去します。|  
|[pop_front](#deque__pop_front)|`deque` の先頭の要素を消去します。|  
|[push_back](#deque__push_back)|`deque` の末尾に要素を追加します。|  
|[push_front](#deque__push_front)|`deque` の先頭に要素を追加します。|  
|[rbegin](#deque__rbegin)|逆順の `deque` 内の最初の要素へのランダム アクセス反復子を返します。|  
|[rend](#deque__rend)|逆順の `deque` 内の最後の要素の次の位置を指し示すランダム アクセス反復子を返します。|  
|[サイズを変更します。](#deque__resize)|`deque` の新しいサイズを指定します。|  
|[deque::shrink_to_fit](#deque__shrink_to_fit)|余分なキャパシティを破棄します。|  
|[サイズ](#deque__size)|`deque` 内の要素数を返します。|  
|[スワップ](#deque__swap)|2 つの `deque` の要素を交換します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 & #91、#93 です。](#deque__operator_at)|指定した位置における `deque` 要素への参照を返します。|  
|[deque::operator =](#deque__operator_eq)|別の `deque` のコピーで `deque` の要素を置き換えます。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー**: \< deque>  
  
##  <a name="a-namedequeallocatortypea-dequeallocatortype"></a><a name="deque__allocator_type"></a>  deque::allocator_type  
 Deque オブジェクトのアロケーター クラスを表す型。  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>コメント  
 **allocator_type** テンプレート パラメーターのシノニムは、 **アロケーター**します。  
  
### <a name="example"></a>例  
  例を参照してください [get_allocator](#deque__get_allocator)します。  
  
##  <a name="a-namedequeassigna-dequeassign"></a><a name="deque__assign"></a>  deque::assign  
 deque から要素を消去し、対象の deque に要素の新しいセットをコピーします。  
  
```  
template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);

void assign(
    size_type Count,  
    const Type& Val);

void assign(
    initializer_list<Type>  
IList);
```  
  
### <a name="parameters"></a>パラメーター  
 `First`  
 deque 引数からコピーされる要素範囲内の最初の要素の位置。  
  
 `Last`  
 deque 引数からコピーされる要素範囲を超える最初の要素の位置。  
  
 `Count`  
 deque に挿入される要素のコピーの数。  
  
 `Val`  
 deque に挿入される要素の値。  
  
 `IList`  
 deque に挿入される initializer_list。  
  
### <a name="remarks"></a>コメント  
 対象の deque 内にある既存の要素が消去されると、`assign` によって、元の deque または他の deque からコピーされる指定の要素範囲が対象の deque に挿入されるか、指定した値の新しい要素のコピーが対象の deque に挿入されます。  
  
### <a name="example"></a>例  
  
```  
// deque_assign.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <initializer_list>  
  
int main()  
{  
    using namespace std;  
    deque <int> c1, c2;  
    deque <int>::const_iterator cIter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    deque<int> d1{ 1, 2, 3, 4 };  
    initializer_list<int> iList{ 5, 6, 7, 8 };  
    d1.assign(iList);  
  
    cout << "d1 = ";  
    for (int i : d1)  
        cout << i;  
    cout << endl;  
  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
    c1.assign(++c2.begin(), c2.end());  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
    c1.assign(7, 4);  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
}  
  
```  
  
```Output  
d1 = 5678c1 =102030c1 =5060c1 =4444444  
```  
  
##  <a name="a-namedequeata-dequeat"></a><a name="deque__at"></a>  deque::at  
 Deque の指定位置にある要素への参照を返します。  
  
```  
reference at(size_type _Pos);

const_reference at(size_type _Pos) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Pos`  
 添字 (または位置番号)、要素の deque 内で参照します。  
  
### <a name="return-value"></a>戻り値  
 場合 `_Pos` 、deque のサイズよりも大きい **で** 例外をスローします。  
  
### <a name="return-value"></a>戻り値  
 場合の戻り値 **で** に割り当てられている、 `const_reference`, 、deque オブジェクトは変更できません。 場合の戻り値 **で** に割り当てられている、 **参照**, 、deque オブジェクトを変更できます。  
  
### <a name="example"></a>例  
  
```  
// deque_at.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const int& i = c1.at( 0 );  
   int& j = c1.at( 1 );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequebacka-dequeback"></a><a name="deque__back"></a>  deque::back  
 Deque の最後の要素への参照を返します。  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>戻り値  
 Deque の最後の要素。 Deque が空の場合、戻り値は未定義です。  
  
### <a name="remarks"></a>コメント  
 場合の戻り値 **戻る** に割り当てられている、 `const_reference`, 、deque オブジェクトは変更できません。 場合の戻り値 **戻る** に割り当てられている、 **参照**, 、deque オブジェクトを変更できます。  
  
 _SECURE_SCL 1 でコンパイルするとき、空の deque の要素にアクセスしようとすると、ランタイム エラーが発生します。  詳細については、「 [Checked Iterators](../standard-library/checked-iterators.md) 」を参照してください。  
  
### <a name="example"></a>例  
  
```  
// deque_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.back( );  
   const int& ii = c1.front( );  
  
   cout << "The last integer of c1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The last integer of c1 is 11  
The next-to-last integer of c1 is 10  
```  
  
##  <a name="a-namedequebegina-dequebegin"></a><a name="deque__begin"></a>  deque::begin  
 Deque の最初の要素を指定する反復子を返します。  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>戻り値  
 Deque または位置を指す、空の deque の最初の要素をアドレス指定ランダム アクセス反復子。  
  
### <a name="remarks"></a>コメント  
 場合の戻り値 **開始** に割り当てられている、 `const_iterator`, 、deque オブジェクトは変更できません。 場合の戻り値 **開始** に割り当てられている、 **反復子**, 、deque オブジェクトを変更できます。  
  
### <a name="example"></a>例  
  
```  
// deque_begin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::const_iterator c1_cIter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is " << *c1_Iter << endl;  
  
 *c1_Iter = 20;  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is now " << *c1_Iter << endl;  
  
   // The following line would be an error because iterator is const  
   // *c1_cIter = 200;  
}  
```  
  
```Output  
The first element of c1 is 1  
The first element of c1 is now 20  
```  
  
##  <a name="a-namedequecbegina-dequecbegin"></a><a name="deque__cbegin"></a>  deque::cbegin  
 範囲内の最初の要素を示す `const` 反復子を返します。  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>戻り値  
 範囲の最初の要素、または空の範囲の末尾の次の位置 (空の範囲の場合、`const`) を指し示す `cbegin() == cend()` ランダム アクセス反復子。  
  
### <a name="remarks"></a>コメント  
 `cbegin` の戻り値で範囲内の要素を変更することはできません。  
  
 `begin()` メンバー関数の代わりにこのメンバー関数を使用して、戻り値が `const_iterator` になることを保証できます。 通常と組み合わせて使用は、 [自動](../cpp/auto-cpp.md) 次の例に示すように、推論キーワードを入力します。 例では、次のように検討します。 `Container` に変更可能な (非 `const`) をサポートする任意の種類のコンテナー `begin()` と `cbegin()`です。  
  
```cpp  
 
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namedequecenda-dequecend"></a><a name="deque__cend"></a>  deque::cend  
 範囲内の最後の要素の次の位置を指す `const` 反復子を返します。  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>戻り値  
 範囲の末尾の次の位置を指し示すランダム アクセス反復子。  
  
### <a name="remarks"></a>コメント  
 `cend` は、反復子が範囲の末尾を超えたかどうかをテストするために使用されます。  
  
 `end()` メンバー関数の代わりにこのメンバー関数を使用して、戻り値が `const_iterator` になることを保証できます。 通常と組み合わせて使用は、 [自動](../cpp/auto-cpp.md) 次の例に示すように、推論キーワードを入力します。 例では、次のように検討します。 `Container` に変更可能な (非 `const`) をサポートする任意の種類のコンテナー `end()` と `cend()`です。  
  
```cpp  
 
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 `cend` によって返された値は逆参照しないでください。  
  
##  <a name="a-namedequecleara-dequeclear"></a><a name="deque__clear"></a>  deque::clear  
 Deque のすべての要素を消去します。  
  
```  
void clear();
```  
  
### <a name="example"></a>例  
  
```  
// deque_clear.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "The size of the deque is initially " << c1.size( ) << endl;  
   c1.clear( );  
   cout << "The size of the deque after clearing is " << c1.size( ) << endl;  
}  
```  
  
```Output  
The size of the deque is initially 3  
The size of the deque after clearing is 0  
```  
  
##  <a name="a-namedequeconstiteratora-dequeconstiterator"></a><a name="deque__const_iterator"></a>  deque::const_iterator  
 ランダム アクセス反復子を提供する型にアクセスして読み取ることができます、 **const** deque 内の要素。  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>コメント  
 `const_iterator` 型で要素の値を変更することはできません。  
  
### <a name="example"></a>例  
  例を参照してください [戻る](#deque__back)します。  
  
##  <a name="a-namedequeconstpointera-dequeconstpointer"></a><a name="deque__const_pointer"></a>  deque::const_pointer  
 deque の `const` 要素へのポインターを提供します。  
  
```unstlib  
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>コメント  
 `const_pointer` 型で要素の値を変更することはできません。  [反復子](#deque__iterator) より一般的に、deque 要素にアクセスするために使用します。  
  
##  <a name="a-namedequeconstreferencea-dequeconstreference"></a><a name="deque__const_reference"></a>  deque::const_reference  
 参照を提供する型、 **const** 要素の読み取りと実行するための deque に格納されている **const** 操作します。  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>コメント  
 `const_reference` 型で要素の値を変更することはできません。  
  
### <a name="example"></a>例  
  
```  
// deque_const_ref.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const deque <int> c2 = c1;  
   const int &i = c2.front( );  
   const int &j = c2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error as c2 is const  
   // c2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequeconstreverseiteratora-dequeconstreverseiterator"></a><a name="deque__const_reverse_iterator"></a>  deque::const_reverse_iterator  
 読み取るいずれかのことができるランダム アクセス反復子を提供する型 **const** deque 内の要素。  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>コメント  
 型 `const_reverse_iterator` 要素の値を変更することはできませんし、逆の順序で deque を反復処理するために使用します。  
  
### <a name="example"></a>例  
  例を参照してください [rbegin](#deque__rbegin) を宣言し、反復子を使用する方法の例です。  
  
##  <a name="a-namedequecrbegina-dequecrbegin"></a><a name="deque__crbegin"></a>  deque::crbegin  
 取り消された deque の最初の要素への定数反復子を返します。  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>戻り値  
 反転された最初の要素を示すランダム アクセス反復子を指す定数逆順 [deque](../standard-library/deque-class.md) 、通常の順序の最後の要素だったものまたは `deque`です。  
  
### <a name="remarks"></a>コメント  
 戻り値が `crbegin` の場合、`deque` オブジェクトは変更できません。  
  
### <a name="example"></a>例  
  
```  
// deque_crbegin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::iterator v1_Iter;  
   deque <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of deque is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed deque is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of deque is 1.  
The first element of the reversed deque is 2.  
```  
  
##  <a name="a-namedequecrenda-dequecrend"></a><a name="deque__crend"></a>  deque::crend  
 取り消された deque 内の最後の要素の次の位置を指す定数反復子を返します。  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>戻り値  
 反転された最後の要素の次の位置を指すランダム アクセス反復子を指す定数逆順 [deque](../standard-library/deque-class.md) (通常の順序の deque 内の最初の要素の前の場所)。  
  
### <a name="remarks"></a>コメント  
 `crend` 使用で反転された `deque` と同様に [array::cend](../standard-library/array-class-stl.md#array__cend) と共に使用される、 `deque`です。  
  
 戻り値を持つ `crend` (適切には減少)、 `deque` オブジェクトは変更できません。  
  
 `crend` 逆順反復子がその deque の末尾に達したかどうかをテストするために使用します。  
  
 `crend` によって返された値は逆参照しないでください。  
  
### <a name="example"></a>例  
  
```  
// deque_crend.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="a-namedequedequea-dequedeque"></a><a name="deque__deque"></a>  deque::deque  
 特定のサイズ、特定の値の要素、または特定のアロケーターを持つ deque を構築します。あるいは他の deque の全体または一部のコピーとして構築します。  
  
```  
deque();

explicit deque(
    const Allocator& Al);

explicit deque(
    size_type Count);

deque(
    size_type Count,  
    const Type& Val);

deque(
    size_type Count,  
    const Type& Val,  
    const Allocator& Al);

deque(
    const deque& Right);

template <class InputIterator>  
deque(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
deque(
 InputIterator First,  
    InputIterator Last,  
    const Allocator& Al);

deque(
    initializer_list<value_type>  
IList,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|`Al`|このオブジェクトに対して使用するアロケーター クラス。|  
|`Count`|構築された deque 内の要素の数。|  
|`Val`|構築された deque の要素の値。|  
|`Right`|構築された deque がコピーになる元の deque。|  
|`First`|コピーする要素範囲内の最初の要素の位置。|  
|`Last`|コピーする要素範囲を超える最初の要素の位置。|  
|`IList`|コピーされる initializer_list。|  
  
### <a name="remarks"></a>コメント  
 すべてのコンス トラクターは、アロケーター オブジェクトを格納 ( `Al`) し、deque を初期化します。  
  
 最初の 2 つのコンス トラクターは、空の初期の deque を指定します。2 つ目は、アロケーターの型もを指定します。 ( `_Al`) を使用します。  
  
 3 番目のコンス トラクターが、指定された数の繰り返しを指定します ( ` count`) クラスの既定値の要素の `Type`です。  
  
 4 番目と 5 番目のコンス トラクターの繰り返しを指定する ( `Count`) の値の要素 ` val`します。  
  
 6 番目のコンストラクターは、deque `Right` のコピーを指定します。  
  
 7 番目と 8 番目のコンストラクターは、deque の範囲 `[First, Last)` をコピーします。  
  
 7 番目のコンストラクターは、deque `Right` を移動します。  
  
 8 番目のコンストラクターは、initializer_list の内容をコピーします。  
  
 コンストラクターでは、暫定的な再割り当てを実行しません。  
  
### <a name="example"></a>例  
  
```  
/ compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <forward_list>  
  
int main()  
{  
    using namespace std;  
  
    forward_list<int> f1{ 1, 2, 3, 4 };  
  
    f1.insert_after(f1.begin(), { 5, 6, 7, 8 });  
  
    deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;  
  
    // Create an empty deque c0  
    deque <int> c0;  
  
    // Create a deque c1 with 3 elements of default value 0  
    deque <int> c1(3);  
  
    // Create a deque c2 with 5 elements of value 2  
    deque <int> c2(5, 2);  
  
    // Create a deque c3 with 3 elements of value 1 and with the   
    // allocator of deque c2  
    deque <int> c3(3, 1, c2.get_allocator());  
  
    // Create a copy, deque c4, of deque c2  
    deque <int> c4(c2);  
  
    // Create a deque c5 by copying the range c4[ first,  last)  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c5(c4.begin(), c4_Iter);  
  
    // Create a deque c6 by copying the range c4[ first,  last) and   
    // c2 with the allocator of deque  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c6(c4.begin(), c4_Iter, c2.get_allocator());  
  
    // Create a deque c8 by copying the contents of an initializer_list  
    // using brace initialization  
    deque<int> c8({ 1, 2, 3, 4 });  
  
    initializer_list<int> iList{ 5, 6, 7, 8 };  
    deque<int> c9( iList);  
  
    cout << "c1 = ";  
    for (int i : c1)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c2 = ";  
    for (int i : c2)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c3 = ";  
    for (int i : c3)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c4 = ";  
    for (int i : c4)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c5 = ";  
    for (int i : c5)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c6 = ";  
    for (int i : c6)  
        cout << i << " ";  
    cout << endl;  
  
    // Move deque c6 to deque c7  
    deque <int> c7(move(c6));  
    deque <int>::iterator c7_Iter;  
  
    cout << "c7 =";  
    for (int i : c7)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c8 = ";  
    for (int i : c8)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c9 = ";  
    for (int i : c9)  
        cout << i << " ";  
    cout << endl;  
  
    int x = 3;  
}  
// deque_deque.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
    using namespace std;  
   deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;  
  
    // Create an empty deque c0  
    deque <int> c0;  
  
    // Create a deque c1 with 3 elements of default value 0  
    deque <int> c1( 3 );  
  
    // Create a deque c2 with 5 elements of value 2  
    deque <int> c2( 5, 2 );  
  
    // Create a deque c3 with 3 elements of value 1 and with the   
    // allocator of deque c2  
    deque <int> c3( 3, 1, c2.get_allocator( ) );  
  
    // Create a copy, deque c4, of deque c2  
    deque <int> c4( c2 );  
  
    // Create a deque c5 by copying the range c4[ first,  last)  
    c4_Iter = c4.begin( );  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c5( c4.begin( ), c4_Iter );  
  
    // Create a deque c6 by copying the range c4[ first,  last) and   
    // c2 with the allocator of deque  
    c4_Iter = c4.begin( );  
   c4_Iter++;  
   c4_Iter++;  
   c4_Iter++;  
   deque <int> c6( c4.begin( ), c4_Iter, c2.get_allocator( ) );  
  
    // Create a deque c8 by copying the contents of an initializer_list  
    // using brace initialization  
    deque<int> c8({ 1, 2, 3, 4 });  
  
        initializer_list<int> iList{ 5, 6, 7, 8 };  
    deque<int> c9( iList);  
  
    cout << "c1 = ";  
    for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
        cout << *c1_Iter << " ";  
    cout << endl;  
  
    cout << "c2 = ";  
    for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
        cout << *c2_Iter << " ";  
    cout << endl;  
  
    cout << "c3 = ";  
    for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
        cout << *c3_Iter << " ";  
    cout << endl;  
  
    cout << "c4 = ";  
    for ( c4_Iter = c4.begin( ); c4_Iter != c4.end( ); c4_Iter++ )  
        cout << *c4_Iter << " ";  
    cout << endl;  
  
    cout << "c5 = ";  
    for ( c5_Iter = c5.begin( ); c5_Iter != c5.end( ); c5_Iter++ )  
        cout << *c5_Iter << " ";  
    cout << endl;  
  
    cout << "c6 = ";  
    for ( c6_Iter = c6.begin( ); c6_Iter != c6.end( ); c6_Iter++ )  
        cout << *c6_Iter << " ";  
    cout << endl;  
  
    // Move deque c6 to deque c7  
    deque <int> c7( move(c6) );  
    deque <int>::iterator c7_Iter;  
  
    cout << "c7 =" ;  
    for ( c7_Iter = c7.begin( ) ; c7_Iter != c7.end( ) ; c7_Iter++ )  
        cout << " " << *c7_Iter;  
    cout << endl;  
  
    cout << "c8 = ";  
    for (int i : c8)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c9 = ";  
    or (int i : c9)  
        cout << i << " ";  
    cout << endl;  
}  
```  
  
##  <a name="a-namedequedifferencetypea-dequedifferencetype"></a><a name="deque__difference_type"></a>  deque::difference_type  
 同じ deque 内の要素を参照する 2 つの反復子の違いを提供する型。  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>コメント  
 `difference_type` は、2 つのポインターの間にある要素数と言い換えることもできます。  
  
### <a name="example"></a>例  
  
```  
// deque_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <deque>  
#include <algorithm>  
  
int main( )   
{  
   using namespace std;  
  
   deque <int> c1;  
   deque <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
   deque <int>::difference_type df_typ1, df_typ2, df_typ3;  
  
   df_typ1 = count( c1_Iter, c2_Iter, 10 );  
   df_typ2 = count( c1_Iter, c2_Iter, 20 );  
   df_typ3 = count( c1_Iter, c2_Iter, 30 );  
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";  
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";  
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";  
}  
```  
  
```Output  
The number '10' is in c1 collection 1 times.  
The number '20' is in c1 collection 2 times.  
The number '30' is in c1 collection 3 times.  
```  
  
##  <a name="a-namedequeemplacea-dequeemplace"></a><a name="deque__emplace"></a>  deque::emplace  
 インプレースで構築された deque の指定した位置に要素を挿入します。  
  
```  
iterator emplace(
    const_iterator _Where,  
    Type&& val);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|`_Where`|内の位置、 [deque](../standard-library/deque-class.md) 最初の要素が挿入されます。|  
|` val`|`deque` に挿入される要素の値。|  
  
### <a name="return-value"></a>戻り値  
 関数は、新しい要素が deque に挿入された位置を指す反復子を返します。  
  
### <a name="remarks"></a>コメント  
 どの挿入操作は、コストが高くなることができますを参照してください `deque` のについて `deque` パフォーマンス。  
  
### <a name="example"></a>例  
  
```  
// deque_emplace.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
vv1[0] = 10 20 30  
```  
  
##  <a name="a-namedequeemplacebacka-dequeemplaceback"></a><a name="deque__emplace_back"></a>  deque::emplace_back  
 Deque の末尾をインプレースで構築された要素を追加します。  
  
```  
void emplace_back(Type&& val);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|` val`|末尾に追加する要素、 [deque](../standard-library/deque-class.md)します。|  
  
### <a name="example"></a>例  
  
```  
// deque_emplace_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
  
   v1.push_back( 1 );  
   if ( v1.size( ) != 0 )  
      cout << "Last element: " << v1.back( ) << endl;  
  
   v1.push_back( 2 );  
   if ( v1.size( ) != 0 )  
      cout << "New last element: " << v1.back( ) << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace_back( move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      cout << "Moved last element: " << vv1[0].back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved last element: 2  
```  
  
##  <a name="a-namedequeemplacefronta-dequeemplacefront"></a><a name="deque__emplace_front"></a>  deque::emplace_front  
 Deque の末尾をインプレースで構築された要素を追加します。  
  
```  
void emplace_front(Type&& val);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|` val`|先頭に追加する要素、 [deque](../standard-library/deque-class.md)します。|  
  
### <a name="example"></a>例  
  
```  
// deque_emplace_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
  
   v1.push_back( 1 );  
   if ( v1.size( ) != 0 )  
      cout << "Last element: " << v1.back( ) << endl;  
  
   v1.push_back( 2 );  
   if ( v1.size( ) != 0 )  
      cout << "New last element: " << v1.back( ) << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace_front( move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      cout << "Moved last element: " << vv1[0].back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved last element: 2  
```  
  
##  <a name="a-namedequeemptya-dequeempty"></a><a name="deque__empty"></a>  deque::empty  
 Deque が空かどうか。  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 **true** deque が空である場合 **false** deque が空でない場合。  
  
### <a name="example"></a>例  
  
```  
// deque_empty.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   if ( c1.empty( ) )  
      cout << "The deque is empty." << endl;  
   else  
      cout << "The deque is not empty." << endl;  
}  
```  
  
```Output  
The deque is not empty.  
```  
  
##  <a name="a-namedequeenda-dequeend"></a><a name="deque__end"></a>  deque::end  
 Deque の最後の要素の次の位置を指す反復子を返します。  
  
```  
const_iterator end() const;

iterator end();
```  
  
### <a name="return-value"></a>戻り値  
 Deque の最後の要素の次の位置を指すランダム アクセス反復子。 Deque が空では、deque::end の場合は、deque::begin に = = です。  
  
### <a name="remarks"></a>コメント  
 **終了** を指す反復子は、deque の終わりに達したかどうかをテストするために使用します。  
  
### <a name="example"></a>例  
  
```  
// deque_end.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_Iter = c1.end( );  
   c1_Iter--;  
   cout << "The last integer of c1 is " << *c1_Iter << endl;  
  
   c1_Iter--;  
 *c1_Iter = 400;  
   cout << "The new next-to-last integer of c1 is " << *c1_Iter << endl;  
  
   // If a const iterator had been declared instead with the line:  
   // deque <int>::const_iterator c1_Iter;  
   // an error would have resulted when inserting the 400  
  
   cout << "The deque is now:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
}  
```  
  
```Output  
The last integer of c1 is 30  
The new next-to-last integer of c1 is 400  
The deque is now: 10 400 30  
```  
  
##  <a name="a-namedequeerasea-dequeerase"></a><a name="deque__erase"></a>  deque::erase  
 指定した位置から deque の要素または要素の範囲を削除します。  
  
```  
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Where`  
 Deque から削除する要素の位置。  
  
 ` first`  
 Deque から削除される最初の要素の位置。  
  
 ` last`  
 最後の要素の次の位置は、deque から削除します。  
  
### <a name="return-value"></a>戻り値  
 削除された場合、要素の後に残る最初の要素を指定するランダム アクセス反復子、またはこのような要素が存在しない場合は、deque の末尾へのポインター。  
  
### <a name="remarks"></a>コメント  
 詳細については **消去**, を参照してください [deque::erase と deque::clear](../misc/deque-erase-and-deque-clear.md)します。  
  
 **消去** は例外をスローします。  
  
### <a name="example"></a>例  
  
```  
// deque_erase.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 40 );  
   c1.push_back( 50 );  
   cout << "The initial deque is: ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
   c1.erase( c1.begin( ) );  
   cout << "After erasing the first element, the deque becomes:  ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
   Iter = c1.begin( );  
   Iter++;  
   c1.erase( Iter, c1.end( ) );  
   cout << "After erasing all elements but the first, deque becomes: ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
}  
```  
  
```Output  
The initial deque is: 10 20 30 40 50   
After erasing the first element, the deque becomes:  20 30 40 50   
After erasing all elements but the first, deque becomes: 20   
```  
  
##  <a name="a-namedequefronta-dequefront"></a><a name="deque__front"></a>  deque::front  
 Deque の最初の要素への参照を返します。  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>戻り値  
 Deque が空の場合、戻り値は定義されていません。  
  
### <a name="remarks"></a>コメント  
 場合の戻り値 `front` に割り当てられている、 `const_reference`, 、deque オブジェクトは変更できません。 場合の戻り値 `front` に割り当てられている、 **参照**, 、deque オブジェクトを変更できます。  
  
 _SECURE_SCL 1 でコンパイルするとき、空の deque の要素にアクセスしようとすると、ランタイム エラーが発生します。  詳細については、「 [Checked Iterators](../standard-library/checked-iterators.md) 」を参照してください。  
  
### <a name="example"></a>例  
  
```  
// deque_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.front( );  
   const int& ii = c1.front( );  
  
   cout << "The first integer of c1 is " << i << endl;  
   i++;  
   cout << "The second integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The first integer of c1 is 10  
The second integer of c1 is 11  
```  
  
##  <a name="a-namedequegetallocatora-dequegetallocator"></a><a name="deque__get_allocator"></a>  deque::get_allocator  
 Deque を構築するために使用するアロケーター オブジェクトのコピーを返します。  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>戻り値  
 Deque で使用されるアロケーター。  
  
### <a name="remarks"></a>コメント  
 Deque クラスのアロケーターは、クラスが記憶域を管理する方法を指定します。 STL コンテナー クラスで提供される既定のアロケーターは、ほとんどのプログラミング要件に対応しています。 独自のアロケーター クラスを作成して使用することは、C++ における高度な作業の 1 つです。  
  
### <a name="example"></a>例  
  
```  
// deque_get_allocator.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // The following lines declare objects that use the default allocator.  
   deque <int> c1;  
   deque <int, allocator<int> > c2 = deque <int, allocator<int> >( allocator<int>( ) );  
  
   // c3 will use the same allocator class as c1  
   deque <int> c3( c1.get_allocator( ) );  
  
   deque <int>::allocator_type xlst = c1.get_allocator( );  
   // You can now call functions on the allocator class used by c1  
}  
```  
  
##  <a name="a-namedequeinserta-dequeinsert"></a><a name="deque__insert"></a>  deque::insert  
 deque の指定された位置に要素、複数の要素、または要素の範囲を挿入します。  
  
```  
iterator insert(
    const_iterator Where,  
    const Type& Val);

iterator insert(
    const_iterator Where,  
    Type&& Val);

void insert(
    iterator Where,  
    size_type Count,  
    const Type& Val);

template <class InputIterator>  
void insert(
    iterator Where,  
    InputIterator First,  
    InputIterator Last);

iterator insert(
    iterator Where,initializer_list<Type>  
IList);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|`Where`|最初の要素が挿入される、ターゲット deque 内の位置。|  
|`Val`|deque に挿入される要素の値。|  
|`Count`|deque に挿入される要素の数。|  
|`First`|コピーされる引数 deque の要素範囲内にある最初の要素の位置。|  
|`Last`|コピーされる引数 deque の要素範囲外にある最初の要素の位置。|  
|`IList`|挿入する要素の initializer_list。|  
  
### <a name="return-value"></a>戻り値  
 最初の 2 つの insert 関数は、新しい要素が deque に挿入される位置を指す反復子を返します。  
  
### <a name="remarks"></a>コメント  
 どの挿入操作も、負荷が大きくなる場合があります。  
  
##  <a name="a-namedequeiteratora-dequeiterator"></a><a name="deque__iterator"></a>  deque::iterator  
 ランダム アクセス反復子を提供する型では、読み取りしたり、deque の要素を変更することができます。  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>コメント  
 型 **反復子** 要素の値を変更するために使用できます。  
  
### <a name="example"></a>例  
  例を参照してください [開始](#deque__begin)します。  
  
##  <a name="a-namedequemaxsizea-dequemaxsize"></a><a name="deque__max_size"></a>  deque::max_size  
 Deque の最大長を返します。  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>戻り値  
 Deque のできる最大の長さ。  
  
### <a name="example"></a>例  
  
```  
// deque_max_size.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::size_type i;  
  
   i = c1.max_size( );  
   cout << "The maximum possible length of the deque is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namedequeoperatorata-dequeoperator"></a><a name="deque__operator_at"></a>  deque::operator[]  
 指定した位置にある deque の要素への参照を返します。  
  
```  
reference operator[](size_type _Pos);

const_reference operator[](size_type _Pos) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Pos`  
 参照されていること、deque 要素の位置。  
  
### <a name="return-value"></a>戻り値  
 位置が指定されている引数の要素への参照。 指定した位置が deque のサイズよりも大きい場合は、結果は未定義です。  
  
### <a name="remarks"></a>コメント  
 場合の戻り値 `operator[]` に割り当てられている、 `const_reference`, 、deque オブジェクトは変更できません。 場合の戻り値 `operator[]` に割り当てられている、 **参照**, 、deque オブジェクトを変更できます。  
  
 _SECURE_SCL 1 でコンパイル、deque の範囲外にある要素にアクセスしようとすると、ランタイム エラーが発生します。  詳細については、「 [Checked Iterators](../standard-library/checked-iterators.md) 」を参照してください。  
  
### <a name="example"></a>例  
  
```  
// deque_op_ref.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   cout << "The first integer of c1 is " << c1[0] << endl;  
   int& i = c1[1];  
   cout << "The second integer of c1 is " << i << endl;  
  
}  
```  
  
```Output  
The first integer of c1 is 10  
The second integer of c1 is 20  
```  
  
##  <a name="a-namedequeoperatoreqa-dequeoperator"></a><a name="deque__operator_eq"></a>  deque::operator =  
 他の deque から要素を使用してこの deque の要素を置き換えます。  
  
```  
deque& operator=(const deque& right);

deque& operator=(deque&& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|` right`|新しい内容を提供する deque。|  
  
### <a name="remarks"></a>コメント  
 最初のオーバーライドからこの deque に要素をコピーする ` right`, 、割り当てのソース。 2 番目のオーバーライドからこの deque に要素を移動する ` right`です。  
  
 オペレーターが実行される前に、この deque に格納されている要素が削除されます。  
  
### <a name="example"></a>例  
  
```  
// deque_operator_as.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
using namespace std;  
  
typedef deque<int> MyDeque;  
  
template<typename MyDeque> struct S;  
  
template<typename MyDeque> struct S<MyDeque&> {  
  static void show( MyDeque& d ) {  
    MyDeque::const_iterator iter;  
    for (iter = d.cbegin(); iter != d.cend(); iter++)  
       cout << *iter << " ";  
    cout << endl;  
  }  
};  
  
template<typename MyDeque> struct S<MyDeque&&> {  
  static void show( MyDeque&& d ) {  
    MyDeque::const_iterator iter;  
    for (iter = d.cbegin(); iter != d.cend(); iter++)  
       cout << *iter << " ";  
cout << " via unnamed rvalue reference " << endl;  
  }  
};  
  
int main( )  
{  
   MyDeque d1, d2;  
  
   d1.push_back(10);  
   d1.push_back(20);  
   d1.push_back(30);  
   d1.push_back(40);  
   d1.push_back(50);  
  
   cout << "d1 = " ;  
   S<MyDeque&>::show( d1 );  
  
   d2 = d1;  
   cout << "d2 = ";  
   S<MyDeque&>::show( d2 );  
  
   cout << "     ";  
   S<MyDeque&&>::show ( move< MyDeque& > (d1) );  
 }  
```  
  
##  <a name="a-namedequepointera-dequepointer"></a><a name="deque__pointer"></a>  deque::pointer  
 内の要素へのポインターを提供する [deque](../standard-library/deque-class.md)します。  
  
```unstlib  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>コメント  
 型 **ポインター** 要素の値を変更するために使用できます。  [反復子](#deque__iterator) より一般的に、deque 要素にアクセスするために使用します。  
  
##  <a name="a-namedequepopbacka-dequepopback"></a><a name="deque__pop_back"></a>  deque::pop_back  
 Deque の末尾から要素を削除します。  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>コメント  
 最後の要素は空でない必要があります。 `pop_back` は例外をスローしません。  
  
### <a name="example"></a>例  
  
```  
// deque_pop_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The last element is: " << c1.back( ) << endl;  
  
   c1.pop_back( );  
   cout << "After deleting the element at the end of the deque, the "  
      "last element is: " << c1.back( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The last element is: 2  
After deleting the element at the end of the deque, the last element is: 1  
```  
  
##  <a name="a-namedequepopfronta-dequepopfront"></a><a name="deque__pop_front"></a>  deque::pop_front  
 Deque の先頭にある要素を削除します。  
  
```  
void pop_front();
```  
  
### <a name="remarks"></a>コメント  
 最初の要素は空でない必要があります。 `pop_front` は例外をスローしません。  
  
### <a name="example"></a>例  
  
```  
// deque_pop_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The second element is: " << c1.back( ) << endl;  
  
   c1.pop_front( );  
   cout << "After deleting the element at the beginning of the "  
      "deque, the first element is: " << c1.front( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The second element is: 2  
After deleting the element at the beginning of the deque, the first element is: 2  
```  
  
##  <a name="a-namedequepushbacka-dequepushback"></a><a name="deque__push_back"></a>  deque::push_back  
 Deque の末尾に要素を追加します。  
  
```  
void push_back(const Type& val);

void push_back(Type&& val);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|` val`|Deque の末尾に追加する要素。|  
  
### <a name="remarks"></a>コメント  
 Deque はままになっている場合は、例外がスローされますされず、例外が再度スローされます。  
  
##  <a name="a-namedequepushfronta-dequepushfront"></a><a name="deque__push_front"></a>  deque::push_front  
 Deque の先頭に要素を追加します。  
  
```  
    void push_front(const Type& val);

void push_front(Type&& val);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|` val`|Deque の先頭に追加する要素。|  
  
### <a name="remarks"></a>コメント  
 Deque はままになっている場合は、例外がスローされますされず、例外が再度スローされます。  
  
### <a name="example"></a>例  
  
```  
// deque_push_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_front( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "First element: " << c1.front( ) << endl;  
  
   c1.push_front( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New first element: " << c1.front( ) << endl;  
  
// move initialize a deque of strings  
   deque <string> c2;  
   string str("a");  
  
   c2.push_front( move( str ) );  
   cout << "Moved first element: " << c2.front( ) << endl;  
}  
```  
  
```Output  
First element: 1  
New first element: 2  
Moved first element: a  
```  
  
##  <a name="a-namedequerbegina-dequerbegin"></a><a name="deque__rbegin"></a>  deque::rbegin  
 取り消された deque の最初の要素を反復子を返します。  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>戻り値  
 反転ランダム アクセス反復子反転 deque の最初の要素をアドレス指定、または通常の順序の deque 内の最後の要素だったものです。  
  
### <a name="remarks"></a>コメント  
 `rbegin` 反転 deque と共に使用されると同様に [開始](#deque__begin) deque と共に使用します。  
  
 場合の戻り値 `rbegin` に割り当てられている、 `const_reverse_iterator`, 、deque オブジェクトは変更できません。 場合の戻り値 `rbegin` に割り当てられている、 `reverse_iterator`, 、deque オブジェクトを変更できます。  
  
 `rbegin` 旧バージョンとの deque を反復処理するために使用します。  
  
### <a name="example"></a>例  
  
```  
// deque_rbegin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::reverse_iterator c1_rIter;  
  
   // If the following line had replaced the line above, an error   
   // would have resulted in the line modifying an element   
   // (commented below) because the iterator would have been const  
   // deque <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rbegin( );  
   cout << "Last element in the deque is " << *c1_rIter << "." << endl;  
  
   cout << "The deque contains the elements: ";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << *c1_Iter << " ";  
   cout << "in that order.";  
   cout << endl;  
  
   // rbegin can be used to iterate through a deque in reverse order  
   cout << "The reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
  
   c1_rIter = c1.rbegin( );  
 *c1_rIter = 40;  // This would have caused an error if a   
                    // const_reverse iterator had been declared as   
                    // noted above  
   cout << "Last element in deque is now " << *c1_rIter << "." << endl;  
}  
```  
  
```Output  
Last element in the deque is 30.  
The deque contains the elements: 10 20 30 in that order.  
The reversed deque is: 30 20 10   
Last element in deque is now 40.  
```  
  
##  <a name="a-namedequereferencea-dequereference"></a><a name="deque__reference"></a>  deque::reference  
 Deque に格納されている要素への参照を提供する型。  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>例  
  
```  
// deque_reference.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const int &i = c1.front( );  
   int &j = c1.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequerenda-dequerend"></a><a name="deque__rend"></a>  deque::rend  
 取り消された deque 内の最後の要素の次の位置を指す反復子を返します。  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>戻り値  
 取り消された deque (通常の順序の deque 内の最初の要素の前の場所) 内の最後の要素の次の位置を指す、逆順のランダム アクセス反復の子です。  
  
### <a name="remarks"></a>コメント  
 `rend` 取り消された deque と共に使用されると同様に [終了](#deque__end) deque と共に使用します。  
  
 場合の戻り値 `rend` に割り当てられている、 `const_reverse_iterator`, 、deque オブジェクトは変更できません。 場合の戻り値 `rend` に割り当てられている、 `reverse_iterator`, 、deque オブジェクトを変更できます。  
  
 `rend` 逆順反復子は、deque の末尾に達しているかどうかをテストするために使用します。  
  
 `rend` によって返された値は逆参照しないでください。  
  
### <a name="example"></a>例  
  
```  
// deque_rend.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::reverse_iterator c1_rIter;  
   // If the following line had replaced the line above, an error  
   // would have resulted in the line modifying an element  
   // (commented below) because the iterator would have been const  
   // deque <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rend( );  
   c1_rIter --; // Decrementing a reverse iterator moves it forward   
                // in the deque (to point to the first element here)  
   cout << "The first element in the deque is: " << *c1_rIter << endl;  
  
   cout << "The deque is: ";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << *c1_Iter << " ";  
   cout << endl;  
  
   // rend can be used to test if an iteration is through all of   
   // the elements of a reversed deque  
   cout << "The reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
  
   c1_rIter = c1.rend( );  
   c1_rIter--; // Decrementing the reverse iterator moves it backward   
               // in the reversed deque (to the last element here)  
 *c1_rIter = 40; // This modification of the last element would   
                   // have caused an error if a const_reverse   
                   // iterator had been declared (as noted above)  
   cout << "The modified reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
}  
```  
  
```Output  
The first element in the deque is: 10  
The deque is: 10 20 30   
The reversed deque is: 30 20 10   
The modified reversed deque is: 30 20 40   
```  
  
##  <a name="a-namedequeresizea-dequeresize"></a><a name="deque__resize"></a>  deque::resize  
 Deque の新しいサイズを指定します。  
  
```  
void resize(size_type _Newsize);

void resize(size_type _Newsize, Type val);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Newsize`  
 Deque の新しいサイズ。  
  
 ` val`  
 新しいサイズが大きい場合は、deque に追加する新しい要素の値を元のサイズ。 この値を省略した場合、新しい要素にはそのクラスの既定値が割り当てられます。  
  
### <a name="remarks"></a>コメント  
 Deque のサイズが要求されたサイズより小さい場合 `_Newsize`, 、要求されたサイズに達するまで、要素が deque に追加します。  
  
 Deque サイズに到達するまで、deque の末尾に近い要素が削除された deque のサイズが要求されたサイズよりも大きい場合は、 `_Newsize`です。  
  
 Deque の現在のサイズが要求されたサイズと同じである場合、処理は行われません。  
  
 [サイズ](#deque__size) deque の現在のサイズが反映されます。  
  
### <a name="example"></a>例  
  
```  
// deque_resize.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{   
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1.resize( 4,40 );  
   cout << "The size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is " << c1.back( ) << endl;  
  
   c1.resize( 5 );  
   cout << "The size of c1 is now: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
  
   c1.resize( 2 );  
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
}  
```  
  
```Output  
The size of c1 is: 4  
The value of the last element is 40  
The size of c1 is now: 5  
The value of the last element is now 0  
The reduced size of c1 is: 2  
The value of the last element is now 20  
```  
  
##  <a name="a-namedequereverseiteratora-dequereverseiterator"></a><a name="deque__reverse_iterator"></a>  deque::reverse_iterator  
 読み取りまたは取り消された deque 内の要素を変更できるランダム アクセス反復子を提供する型。  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>コメント  
 型 `reverse_iterator` は、deque を反復処理するために使用します。  
  
### <a name="example"></a>例  
  Rbegin の例を参照してください。  
  
##  <a name="a-namedequeshrinktofita-dequeshrinktofit"></a><a name="deque__shrink_to_fit"></a>  deque::shrink_to_fit  
 余分なキャパシティを破棄します。  
  
```  
void shrink_to_fit();
```  
  
### <a name="remarks"></a>コメント  
 かどうかをポータブルの方法はありません `shrink_to_fit` で使用されるストレージを削減する、 [deque](../standard-library/deque-class.md)します。  
  
### <a name="example"></a>例  
  
```  
// deque_shrink_to_fit.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   //deque <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   cout << "Current size of v1 = "   
      << v1.size( ) << endl;  
   v1.shrink_to_fit();  
   cout << "Current size of v1 = "   
      << v1.size( ) << endl;  
}  
```  
  
```Output  
Current size of v1 = 1  
Current size of v1 = 1  
```  
  
##  <a name="a-namedequesizea-dequesize"></a><a name="deque__size"></a>  deque::size  
 Deque の要素の数を返します。  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>戻り値  
 Deque の現在の長さ。  
  
### <a name="example"></a>例  
  
```  
// deque_size.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::size_type i;  
  
   c1.push_back( 1 );  
   i = c1.size( );  
   cout << "The deque length is " << i << "." << endl;  
  
   c1.push_back( 2 );  
   i = c1.size( );  
   cout << "The deque length is now " << i << "." << endl;  
}  
```  
  
```Output  
The deque length is 1.  
The deque length is now 2.  
```  
  
##  <a name="a-namedequesizetypea-dequesizetype"></a><a name="deque__size_type"></a>  deque::size_type  
 Deque の要素の数をカウントする型。  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>例  
  例を参照してください [サイズ](#deque__size)します。  
  
##  <a name="a-namedequeswapa-dequeswap"></a><a name="deque__swap"></a>  deque::swap  
 2 つの deque の要素を交換します。  
  
```  
void swap(deque<Type, Allocator>& right);

friend void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right) template <class Type, class Allocator>  
void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 交換する要素を提供する deque またはれる要素が deque のものと交換される deque ` left`します。  
  
 ` left`  
 Deque のものと交換されるれる要素が deque ` right`します。  
  
### <a name="example"></a>例  
  
```  
// deque_swap.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1, c2, c3;  
   deque <int>::iterator c1_Iter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 3 );  
   c2.push_back( 10 );  
   c2.push_back( 20 );  
   c3.push_back( 100 );  
  
   cout << "The original deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.swap( c2 );  
  
   cout << "After swapping with c2, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap( c1,c3 );  
  
   cout << "After swapping with c3, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap<>(c1, c2);  
   cout << "After swapping with c2, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The original deque c1 is: 1 2 3  
After swapping with c2, deque c1 is: 10 20  
After swapping with c3, deque c1 is: 100  
After swapping with c2, deque c1 is: 1 2 3  
```  
  
##  <a name="a-namedequevaluetypea-dequevaluetype"></a><a name="deque__value_type"></a>  deque::value_type  
 Deque に格納されているデータ型を表す型。  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>コメント  
 `value_type` テンプレート パラメーターのシノニムは、 **型**します。  
  
### <a name="example"></a>例  
  
```  
// deque_value_type.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
int main( )   
{  
   using namespace std;  
   deque<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)

