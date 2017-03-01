---
title: "concurrent_vector クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_vector/Concurrency::concurrent_vector
- concurrent_vector/concurrency::concurrent_vector
dev_langs:
- C++
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: fdc84a03c562a4efa336f62c0cf0a7529c420f95
ms.lasthandoff: 02/24/2017

---
# <a name="concurrentvector-class"></a>concurrent_vector クラス
`concurrent_vector` クラスは、任意の要素にランダムにアクセスできるようにするシーケンス コンテナー クラスです。 これを使用すると、同時実行セーフな追加、要素アクセス、反復子アクセス、および反復子走査の各操作を実行できます。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
 private details::_Concurrent_vector_base_v4;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ベクターに格納される要素のデータ型。  
  
 `_Ax`  
 同時実行ベクターのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は `allocator<``T``>` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`allocator_type`|同時実行ベクターのアロケーター クラスを表す型。|  
|`const_iterator`|読み取ることができるランダム アクセス反復子を提供する型、`const`同時実行ベクターの要素。|  
|`const_pointer`|ポインターを提供する型、`const`同時実行ベクターの要素。|  
|`const_reference`|参照を提供する型、`const`要素の読み取りと実行するための同時実行ベクターに格納されている`const`操作します。|  
|`const_reverse_iterator`|読み取るいずれかのことができるランダム アクセス反復子を提供する型`const`同時実行ベクターの要素。|  
|`difference_type`|同時実行ベクターの&2; つの要素間の署名付きの距離を提供する型。|  
|`iterator`|同時実行ベクターの任意の要素を読み取ることができるランダム アクセス反復子を提供する型。 反復子を使用して、要素の変更は、同時実行セーフではありません。|  
|`pointer`|同時実行ベクター内の要素へのポインターを提供する型。|  
|`reference`|同時実行ベクターに格納されている要素への参照を提供する型。|  
|`reverse_iterator`|逆順の同時実行ベクターの任意の要素を読み取ることができるランダム アクセス反復子を提供する型。 反復子を使用して、要素の変更は、同時実行セーフではありません。|  
|`size_type`|同時実行ベクターの要素の数をカウントする型。|  
|`value_type`|同時実行ベクターに格納されているデータ型を表す型。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[concurrent_vector コンス トラクター](#ctor)|オーバーロードされます。 同時実行ベクターを構築します。|  
|[~ concurrent_vector デストラクター](#dtor)|すべての要素を消去し、この同時実行ベクターを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[assign メソッド](#assign)|オーバーロードされます。 同時実行ベクターの要素を消去し、いずれかを代入`_N`のコピーを`_Item`、反復子の範囲で指定された値、または [ `_Begin`、 `_End`)。 このメソッドは同時実行セーフではありません。|  
|[at メソッド](#at)|オーバーロードされます。 同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは同時実行セーフ読み取り操作とするように動作する、値として、ベクトルを拡大しながらも`_Index`が同時実行ベクターのサイズより小さい。|  
|[back メソッド](#back)|オーバーロードされます。 参照 a または a を返します。`const`最後に、同時実行ベクターの要素を参照します。 同時実行ベクターが空の場合、戻り値は未定義です。 このメソッドは同時実行セーフです。|  
|[begin メソッド](#begin)|オーバーロードされます。 型の反復子を返します`iterator`または`const_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。|  
|[容量メソッド](#capacity)|同時実行ベクターがより多くのメモリを割り当てることがなく拡張できる最大サイズを返します。 このメソッドは同時実行セーフです。|  
|[cbegin メソッド](#cbegin)|型の反復子を返します`const_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。|  
|[cend メソッド](#cend)|型の反復子を返します`const_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。|  
|[clear メソッド](#clear)|同時実行ベクター内のすべての要素を消去します。 このメソッドは同時実行セーフではありません。|  
|[crbegin メソッド](#crbegin)|型の反復子を返します`const_reverse_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。|  
|[crend メソッド](#crend)|型の反復子を返します`const_reverse_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。|  
|[empty メソッド](#empty)|テスト時に、同時実行ベクターが空の場合、このメソッドが呼び出されます。 このメソッドは同時実行セーフです。|  
|[end メソッド](#end)|オーバーロードされます。 型の反復子を返します`iterator`または`const_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。|  
|[front メソッド](#front)|オーバーロードされます。 参照 a または a を返します。 `const` 、同時実行ベクターの最初の要素への参照。 同時実行ベクターが空の場合、戻り値は未定義です。 このメソッドは同時実行セーフです。|  
|[get_allocator メソッド](#get_allocator)|同時実行ベクターを構築するために使用するアロケーターのコピーを返します。 このメソッドは同時実行セーフです。|  
|[grow_by メソッド](#grow_by)|オーバーロードされます。 この同時実行ベクターで`_Delta`要素。 このメソッドは同時実行セーフです。|  
|[grow_to_at_least メソッド](#grow_to_at_least)|以上を持つことになるまでこの同時実行ベクターを拡張`_N`要素。 このメソッドは同時実行セーフです。|  
|[max_size メソッド](#max_size)|同時実行ベクターに格納できる要素の最大数を返します。 このメソッドは同時実行セーフです。|  
|[push_back メソッド](#push_back)|オーバーロードされます。 同時実行ベクターの末尾に指定したアイテムを追加します。 このメソッドは同時実行セーフです。|  
|[rbegin メソッド](#rbegin)|オーバーロードされます。 型の反復子を返します`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。|  
|[rend メソッド](#rend)|オーバーロードされます。 型の反復子を返します`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。|  
|[reserve メソッド](#reserve)|同時実行ベクターをサイズに拡大するには、十分な領域を割り当てる`_N`を後でより多くのメモリを割り当てる必要はありません。 このメソッドは同時実行セーフではありません。|  
|[resize メソッド](#resize)|オーバーロードされます。 要求されたサイズ、削除、または必要に応じて要素を追加するには、同時実行ベクターのサイズを変更します。 このメソッドは同時実行セーフではありません。|  
|[shrink_to_fit メソッド](#shrink_to_fit)|断片化を解消し、メモリ使用量を最適化する同時実行ベクターの内部表現が圧縮されます。 このメソッドは同時実行セーフではありません。|  
|[サイズ メソッド](#size)|同時実行ベクターの要素の数を返します。 このメソッドは同時実行セーフです。|  
|[swap メソッド](#swap)|2 つの同時実行ベクターのコンテンツを交換します。 このメソッドは同時実行セーフではありません。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator[] 演算子](#operator_at)|オーバーロードされます。 同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは同時実行セーフ読み取り操作に対して、またするように動作する、値として、ベクトルを拡大しながら`_Index`が同時実行ベクターのサイズより小さい。|  
|[operator = 演算子](#operator_eq)|オーバーロードされます。 別の `concurrent_vector` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドは同時実行セーフではありません。|  
  
## <a name="remarks"></a>コメント  
 詳細については、`concurrent_vector`を参照してください[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concurrent_vector.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameassigna-assign"></a><a name="assign"></a>割り当てる 

 同時実行ベクターの要素を消去し、いずれかを代入`_N`のコピーを`_Item`、反復子の範囲で指定された値、または [ `_Begin`、 `_End`)。 このメソッドは同時実行セーフではありません。  
  
```
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```  
  
### <a name="parameters"></a>パラメーター  
 `_InputIterator`  
 指定した反復子の型。  
  
 `_N`  
 同時実行ベクターにコピーするアイテムの数。  
  
 `_Item`  
 同時実行ベクターの塗りつぶしに使用される値への参照。  
  
 `_Begin`  
 ソース範囲の最初の要素を指す反復子。  
  
 `_End`  
 1 つ後ろのソース範囲の最後の要素を指す反復子。  
  
### <a name="remarks"></a>コメント  
 `assign`同時実行セーフではありません。 他のスレッド メソッドを呼び出していない同時実行ベクターをこのメソッドを呼び出すとを確認する必要があります。  
  
##  <a name="a-nameata-at"></a><a name="at"></a>で 

 同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは同時実行セーフ読み取り操作とするように動作する、値として、ベクトルを拡大しながらも`_Index`が同時実行ベクターのサイズより小さい。  
  
```
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 取得する要素のインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置にある項目への参照。  
  
### <a name="remarks"></a>コメント  
 関数のバージョン`at`以外を返す`const`の参照は、要素へのさまざまなスレッドから同時に書き込みを使用することはできません。 さまざまな同期オブジェクトは、同時読み取りを同期し、同じデータ要素への書き込み操作に使用する必要があります。  
  
 メソッドをスロー`out_of_range`場合`_Index`が同時実行ベクターのサイズ以上と`range_error`ベクトルの破損部分のインデックスが含まれる場合。 ベクターが切断される方法の詳細については、「[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)します。  
  
##  <a name="a-namebacka-back"></a><a name="back"></a>戻る 

 参照 a または a を返します。`const`最後に、同時実行ベクターの要素を参照します。 同時実行ベクターが空の場合、戻り値は未定義です。 このメソッドは同時実行セーフです。  
  
```
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>戻り値  
 参照または`const`最後に、同時実行ベクターの要素を参照します。  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>開始 

 型の反復子を返します`iterator`または`const_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`iterator`または`const_iterator`同時実行ベクターの先頭にします。  
  
##  <a name="a-namecapacitya-capacity"></a><a name="capacity"></a>容量 

 同時実行ベクターがより多くのメモリを割り当てることがなく拡張できる最大サイズを返します。 このメソッドは同時実行セーフです。  
  
```
size_type capacity() const;
```  
  
### <a name="return-value"></a>戻り値  
 最大サイズを同時実行ベクターがより多くのメモリを割り当てることがなく拡張できます。  
  
### <a name="remarks"></a>コメント  
 C++ 標準ライブラリとは異なり`vector`、`concurrent_vector`より多くのメモリを割り当てる場合は、オブジェクトが既存の要素を移動しません。  
  
##  <a name="a-namecbegina-cbegin"></a><a name="cbegin"></a>cbegin 

 型の反復子を返します`const_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`const_iterator`同時実行ベクターの先頭にします。  
  
##  <a name="a-namecenda-cend"></a><a name="cend"></a>cend 

 型の反復子を返します`const_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`const_iterator`同時実行ベクターの末尾にします。  
  
##  <a name="a-namecleara-clear"></a><a name="clear"></a>オフ 

 同時実行ベクター内のすべての要素を消去します。 このメソッドは同時実行セーフではありません。  
  
```
void clear();
```  
  
### <a name="remarks"></a>コメント  
 `clear`同時実行セーフではありません。 他のスレッド メソッドを呼び出していない同時実行ベクターをこのメソッドを呼び出すとを確認する必要があります。 `clear`内部の配列は解放されません。 内部の配列を解放するには、関数を呼び出して`shrink_to_fit`後`clear`します。  
  
##  <a name="a-namectora-concurrentvector"></a><a name="ctor"></a>concurrent_vector 

 同時実行ベクターを構築します。  
  
```
explicit concurrent_vector(
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector(
    const concurrent_vector<T,
    M>& _Vector,
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    concurrent_vector&& _Vector);

explicit concurrent_vector(
    size_type _N);

concurrent_vector(
    size_type _N,
    const_reference _Item,
    const allocator_type& _Al = allocator_type());

template<class _InputIterator>
concurrent_vector(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());
```  
  
### <a name="parameters"></a>パラメーター  
 `M`  
 ソース ベクターのアロケーターの型。  
  
 `_InputIterator`  
 入力反復子の型。  
  
 `_Al`  
 このオブジェクトに対して使用するアロケーター クラス。  
  
 `_Vector`  
 要素のコピー元または移動元の `concurrent_vector` オブジェクト。  
  
 `_N`  
 `concurrent_vector` オブジェクトの初期容量。  
  
 `_Item`  
 構築されたオブジェクトの要素の値。  
  
 `_Begin`  
 コピーする要素範囲内の最初の要素の位置。  
  
 `_End`  
 コピーする要素範囲を超える最初の要素の位置。  
  
### <a name="remarks"></a>コメント  
 すべてのコンストラクターは、アロケーター オブジェクト `_Al` を格納し、ベクターを初期化します。  
  
 最初のコンス トラクターは、空の初期ベクターを指定し、アロケーターの型を明示的に指定します。 使用されます。  
  
 2 つ目および&3; つ目のコンストラクターは、同時実行ベクター `_Vector` のコピーを指定します。  
  
 4 番目のコンストラクターは、同時実行ベクター `_Vector` の移動を指定します。  
  
 5 番目のコンス トラクターが、指定された数の繰り返しを指定します ( `_N`) クラスの既定値の要素の`T`です。  
  
 6 番目のコンス トラクターは、指定の繰り返し ( `_N`) の値の要素`_Item`します。  
  
 最後のコンス トラクターは、反復子の範囲で指定される値を指定します。 [ `_Begin`、 `_End`)。  
  
##  <a name="a-namedtora-concurrentvector"></a><a name="dtor"></a>~ concurrent_vector 

 すべての要素を消去し、この同時実行ベクターを破棄します。  
  
```
~concurrent_vector();
```  
  
##  <a name="a-namecrbegina-crbegin"></a><a name="crbegin"></a>crbegin 

 型の反復子を返します`const_reverse_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。  
  
```
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`const_reverse_iterator`同時実行ベクターの先頭にします。  
  
##  <a name="a-namecrenda-crend"></a><a name="crend"></a>crend 

 型の反復子を返します`const_reverse_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。  
  
```
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`const_reverse_iterator`同時実行ベクターの末尾にします。  
  
##  <a name="a-nameemptya-empty"></a><a name="empty"></a>空 

 テスト時に、同時実行ベクターが空の場合、このメソッドが呼び出されます。 このメソッドは同時実行セーフです。  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 `true`関数が呼び出された時点で、ベクターが空の場合`false`それ以外の場合。  
  
##  <a name="a-nameenda-end"></a><a name="end"></a>終わり 

 型の反復子を返します`iterator`または`const_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`iterator`または`const_iterator`同時実行ベクターの末尾にします。  
  
##  <a name="a-namefronta-front"></a><a name="front"></a>前面 

 参照 a または a を返します。 `const` 、同時実行ベクターの最初の要素への参照。 同時実行ベクターが空の場合、戻り値は未定義です。 このメソッドは同時実行セーフです。  
  
```
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>戻り値  
 参照や`const`同時実行ベクターの最初の要素への参照。  
  
##  <a name="a-namegetallocatora-getallocator"></a><a name="get_allocator"></a>get_allocator 

 同時実行ベクターを構築するために使用するアロケーターのコピーを返します。 このメソッドは同時実行セーフです。  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>戻り値  
 構築するために使用するアロケーターのコピー、`concurrent_vector`オブジェクトです。  
  
##  <a name="a-namegrowbya-growby"></a><a name="grow_by"></a>grow_by 

 この同時実行ベクターで`_Delta`要素。 このメソッドは同時実行セーフです。  
  
```
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Delta`  
 オブジェクトに追加する要素の数。  
  
 `_Item`  
 使用して、新しい要素を初期化する値。  
  
### <a name="return-value"></a>戻り値  
 最初の項目を指す反復子が追加されます。  
  
### <a name="remarks"></a>コメント  
 場合`_Item`が指定されていない、新しい要素が構築された既定です。  
  
##  <a name="a-namegrowtoatleasta-growtoatleast"></a><a name="grow_to_at_least"></a>grow_to_at_least 

 以上を持つことになるまでこの同時実行ベクターを拡張`_N`要素。 このメソッドは同時実行セーフです。  
  
```
iterator grow_to_at_least(size_type _N);
```  
  
### <a name="parameters"></a>パラメーター  
 `_N`  
 新しい最小サイズ、`concurrent_vector`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 インデックス位置にある要素に追加されたシーケンスの先頭を指す反復子`_N`要素は付加しない場合。  
  
##  <a name="a-namemaxsizea-maxsize"></a><a name="max_size"></a>max_size 

 同時実行ベクターに格納できる要素の最大数を返します。 このメソッドは同時実行セーフです。  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>戻り値  
 要素の最大数、`concurrent_vector`オブジェクトを保持できます。  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

 別の `concurrent_vector` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドは同時実行セーフではありません。  
  
```
concurrent_vector& operator= (
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector& operator= (
    const concurrent_vector<T, M>& _Vector);

concurrent_vector& operator= (
    concurrent_vector&& _Vector);
```  
  
### <a name="parameters"></a>パラメーター  
 `M`  
 ソース ベクターのアロケーターの型。  
  
 `_Vector`  
 ソース `concurrent_vector` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `concurrent_vector` オブジェクトへの参照。  
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>演算子 

 同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは同時実行セーフ読み取り操作に対して、またするように動作する、値として、ベクトルを拡大しながら`_Index`が同時実行ベクターのサイズより小さい。  
  
```
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 取得する要素のインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置にある項目への参照。  
  
### <a name="remarks"></a>コメント  
 バージョンの`operator []`以外を返す`const`の参照は、要素へのさまざまなスレッドから同時に書き込みを使用することはできません。 さまざまな同期オブジェクトは、同時読み取りを同期し、同じデータ要素への書き込み操作に使用する必要があります。  
  
 確実に実行されるチェックなしの境界`_Index`は同時実行ベクターに有効なインデックスです。  
  
##  <a name="a-namepushbacka-pushback"></a><a name="push_back"></a>push_back 

 同時実行ベクターの末尾に指定したアイテムを追加します。 このメソッドは同時実行セーフです。  
  
```
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Item`  
 追加する値。  
  
### <a name="return-value"></a>戻り値  
 アイテムを指す反復子が追加されます。  
  
##  <a name="a-namerbegina-rbegin"></a><a name="rbegin"></a>rbegin 

 型の反復子を返します`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。  
  
```
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの先頭にします。  
  
##  <a name="a-namerenda-rend"></a><a name="rend"></a>rend 

 型の反復子を返します`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。  
  
```
reverse_iterator rend();

const_reverse_iterator rend() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの末尾にします。  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>予約 

 同時実行ベクターをサイズに拡大するには、十分な領域を割り当てる`_N`を後でより多くのメモリを割り当てる必要はありません。 このメソッドは同時実行セーフではありません。  
  
```
void reserve(size_type _N);
```  
  
### <a name="parameters"></a>パラメーター  
 `_N`  
 領域を予約する要素の数。  
  
### <a name="remarks"></a>コメント  
 `reserve`同時実行セーフではありません。 他のスレッド メソッドを呼び出していない同時実行ベクターをこのメソッドを呼び出すとを確認する必要があります。 メソッドが返された後に、同時実行ベクターの容量は、要求された予約を超える可能性があります。  
  
##  <a name="a-nameresizea-resize"></a><a name="resize"></a>サイズを変更します。 

 要求されたサイズ、削除、または必要に応じて要素を追加するには、同時実行ベクターのサイズを変更します。 このメソッドは同時実行セーフではありません。  
  
```
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```  
  
### <a name="parameters"></a>パラメーター  
 `_N`  
 Concurrent_vector の新しいサイズ。  
  
 `val`  
 新しい要素の値は、新しいサイズが元のサイズより大きいかどうか、ベクターに追加します。 値を省略すると、新しいオブジェクトには、その型の既定値は割り当てられます。  
  
### <a name="remarks"></a>コメント  
 コンテナーのサイズが要求されたサイズよりも小さい場合は、要求されたサイズに達するまで、ベクターに要素が追加されます。 コンテナー サイズに到達するまでに、コンテナーの末尾に近い要素が削除されたコンテナーのサイズが要求されたサイズよりも大きい場合は、`_N`です。 コンテナーの現在のサイズが要求されたサイズと同じ場合は、何も実行されません。  
  
 `resize`同時実行安全ではありません。 他のスレッド メソッドを呼び出していない同時実行ベクターをこのメソッドを呼び出すとを確認する必要があります。  
  
##  <a name="a-nameshrinktofita-shrinktofit"></a><a name="shrink_to_fit"></a>shrink_to_fit 

 断片化を解消し、メモリ使用量を最適化する同時実行ベクターの内部表現が圧縮されます。 このメソッドは同時実行セーフではありません。  
  
```
void shrink_to_fit();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは内部的に再割り当て、メモリの移動の要素すべての反復子を無効にします。 `shrink_to_fit`同時実行セーフではありません。 他のスレッド メソッドを呼び出していない同時実行ベクターをこの関数を呼び出すときを確認する必要があります。  
  
##  <a name="a-namesizea-size"></a><a name="size"></a>サイズ 

 同時実行ベクターの要素の数を返します。 このメソッドは同時実行セーフです。  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>戻り値  
 この要素の数`concurrent_vector`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 返されるサイズが、関数への呼び出しにより追加されたすべての要素を含めることが保証`push_back`、またはこのメソッドを呼び出す前に完了した操作を拡大します。 ただし、割り当てられている要素を含める場合もが、同時呼び出しの拡張メソッドのいずれかを構築中。  
  
##  <a name="a-nameswapa-swap"></a><a name="swap"></a>スワップ 

 2 つの同時実行ベクターのコンテンツを交換します。 このメソッドは同時実行セーフではありません。  
  
```
void swap(concurrent_vector& _Vector);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Vector`  
 `concurrent_vector`の内容を交換するオブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)




