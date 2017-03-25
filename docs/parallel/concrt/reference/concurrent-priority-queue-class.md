---
title: "concurrent_priority_queue クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::clear
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::empty
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::get_allocator
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::push
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::size
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::swap
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::try_pop
dev_langs:
- C++
helpviewer_keywords:
- concurrent_priority_queue class
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
caps.latest.revision: 9
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 95b52911135513b0b1e4d84509c80ed3262c1765
ms.lasthandoff: 03/17/2017

---
# <a name="concurrentpriorityqueue-class"></a>concurrent_priority_queue クラス
`concurrent_priority_queue` クラスは、複数のスレッドが項目を同時にプッシュおよびポップできるようにするコンテナーです。 項目は優先順位の順にポップされます。この優先順位は、テンプレート引数として指定されたファンクタによって決まります。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T,
    typename _Compare= std::less<T>,
    typename _Ax = std::allocator<T>
>,
    typename _Ax = std::allocator<T>> class concurrent_priority_queue;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 優先順位キューに格納される要素のデータ型。  
  
 `_Compare`  
 優先順位キュー内の相対順序を決定する並べ替えキーとして&2; つの要素の値を比較関数オブジェクトの型。 この引数は省略可能であり、既定値は二項述語 `less<``T``>` です。  
  
 `_Ax`  
 割り当てと、同時実行の優先順位キュー用のメモリの解放に関する詳細をカプセル化する格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は `allocator<``T``>` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`allocator_type`|同時実行の優先順位キューのアロケーター クラスを表す型。|  
|`const_reference`|同時実行の優先順位キューに格納されている型の要素を指す定数参照を表します型。|  
|`reference`|同時実行の優先順位キューに格納されている型の要素への参照を表す型。|  
|`size_type`|同時実行の優先順位キュー内の要素の数をカウントする型。|  
|`value_type`|同時実行の優先順位キューに格納されているデータ型を表す型。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[concurrent_priority_queue](#ctor)|オーバーロードされます。 同時実行の優先度のキューを作成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[clear](#clear)|同時実行の優先度のすべての要素を消去します。 このメソッドは同時実行セーフではありません。|  
|[empty](#empty)|テスト時に、同時実行の優先順位キューが空の場合、このメソッドが呼び出されます。 このメソッドは同時実行セーフです。|  
|[get_allocator](#get_allocator)|同時実行の優先順位キューの構築に使用されるアロケーターのコピーを返します。 このメソッドは同時実行セーフです。|  
|[push](#push)|オーバーロードされます。 同時実行の優先順位キューに要素を追加します。 このメソッドは同時実行セーフです。|  
|[size](#size)|同時実行の優先順位キュー内の要素の数を返します。 このメソッドは同時実行セーフです。|  
|[swap](#swap)|2 つの同時実行の優先順位キューの内容を交換します。 このメソッドは同時実行セーフではありません。|  
|[try_pop](#try_pop)|削除し、キューが空でない場合は、キューから最高の優先度要素を返します。 このメソッドは同時実行セーフです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator=](#operator_eq)|オーバーロードされます。 別の `concurrent_priority_queue` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドは同時実行セーフではありません。|  
  
## <a name="remarks"></a>コメント  
 詳細については、`concurrent_priority_queue`を参照してください[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `concurrent_priority_queue`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concurrent_priority_queue.h  
  
 **名前空間:** concurrency  
  
##  <a name="clear"></a>オフ 

 同時実行の優先度のすべての要素を消去します。 このメソッドは同時実行セーフではありません。  
  
```
void clear();
```  
  
### <a name="remarks"></a>コメント  
 `clear`同時実行セーフではありません。 他のスレッド メソッドを呼び出していない、同時実行の優先順位キューでこのメソッドを呼び出すとを確認する必要があります。 `clear`メモリは解放されません。  
  
##  <a name="ctor"></a>concurrent_priority_queue 

 同時実行の優先度のキューを作成します。  
  
```
explicit concurrent_priority_queue(
    const allocator_type& _Al = allocator_type());

explicit concurrent_priority_queue(
    size_type _Init_capacity,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_priority_queue(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());

concurrent_priority_queue(
    const concurrent_priority_queue& _Src);

concurrent_priority_queue(
    const concurrent_priority_queue& _Src,
    const allocator_type& _Al);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src,
    const allocator_type& _Al);
```  
  
### <a name="parameters"></a>パラメーター  
 `_InputIterator`  
 入力反復子の型。  
  
 `_Al`  
 このオブジェクトに対して使用するアロケーター クラス。  
  
 `_Init_capacity`  
 `concurrent_priority_queue` オブジェクトの初期容量。  
  
 `_Begin`  
 コピーする要素範囲内の最初の要素の位置。  
  
 `_End`  
 コピーする要素範囲を超える最初の要素の位置。  
  
 `_Src`  
 要素のコピー元または移動元の `concurrent_priority_queue` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 すべてのコンス トラクターは、アロケーター オブジェクトを格納`_Al`優先順位キューを初期化します。  
  
 最初のコンス トラクターは、空の初期優先度キューを指定し、必要に応じてのアロケーターを指定します。  
  
 2 番目のコンス トラクターは、初期の容量を持つ優先度のキューを指定`_Init_capacity`オプションでのアロケーターを指定します。  
  
 3 番目のコンス トラクターは、反復子の範囲で指定される値を指定します。 [ `_Begin`、 `_End`) をオプションとしてのアロケーターを指定します。  
  
 4 番目と&5; 番目のコンス トラクターは、優先順位キューのコピーを指定`_Src`します。  
  
 6 番目と&7; 番目のコンス トラクターは、優先順位キューの移動を指定します。`_Src`します。  
  
##  <a name="empty"></a>空 

 テスト時に、同時実行の優先順位キューが空の場合、このメソッドが呼び出されます。 このメソッドは同時実行セーフです。  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 `true`関数が呼び出された時点で、優先順位キューが空の場合`false`それ以外の場合。  
  
##  <a name="get_allocator"></a>get_allocator 

 同時実行の優先順位キューの構築に使用されるアロケーターのコピーを返します。 このメソッドは同時実行セーフです。  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>戻り値  
 構築するために使用するアロケーターのコピー、`concurrent_priority_queue`オブジェクトです。  
  
##  <a name="operator_eq"></a>演算子 = 

 別の `concurrent_priority_queue` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドは同時実行セーフではありません。  
  
```
concurrent_priority_queue& operator= (const concurrent_priority_queue& _Src);

concurrent_priority_queue& operator= (concurrent_priority_queue&& _Src);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
 ソース `concurrent_priority_queue` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `concurrent_priority_queue` オブジェクトへの参照。  
  
##  <a name="push"></a>プッシュ 

 同時実行の優先順位キューに要素を追加します。 このメソッドは同時実行セーフです。  
  
```
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Elem`  
 同時実行の優先順位キューに追加する要素。  
  
##  <a name="size"></a>サイズ 

 同時実行の優先順位キュー内の要素の数を返します。 このメソッドは同時実行セーフです。  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>戻り値  
 この要素の数`concurrent_priority_queue`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 返されるサイズが、関数への呼び出しによって追加されたすべての要素を含めることが保証`push`します。 ただし、保留中の同時操作の結果は反映されません可能性があります。  
  
##  <a name="swap"></a>スワップ 

 2 つの同時実行の優先順位キューの内容を交換します。 このメソッドは同時実行セーフではありません。  
  
```
void swap(concurrent_priority_queue& _Queue);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Queue`  
 `concurrent_priority_queue`の内容を交換するオブジェクト。  
  
##  <a name="try_pop"></a>try_pop 

 削除し、キューが空でない場合は、キューから最高の優先度要素を返します。 このメソッドは同時実行セーフです。  
  
```
bool try_pop(reference _Elem);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Elem`  
 キューが空でない場合に、最高の優先順位の要素に加えられる変数への参照。  
  
### <a name="return-value"></a>戻り値  
 `true`値がポップされ場合、`false`それ以外の場合。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)




