---
title: "concurrent_unordered_set クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_unordered_set/concurrency::concurrent_unordered_set
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_set class
ms.assetid: c61f9a9a-4fd9-491a-9251-e300737ecf4b
caps.latest.revision: 12
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
ms.sourcegitcommit: 19244e5527207f852256e646abd18ad298fb28cd
ms.openlocfilehash: d4454b69c7fba76787068757aa4ff5b486904f2a
ms.lasthandoff: 02/24/2017

---
# <a name="concurrentunorderedset-class"></a>concurrent_unordered_set クラス
`concurrent_unordered_set`クラスは K. 型の要素の可変長シーケンスを制御する同時実行セーフなコンテナー同時実行セーフであることができるように、シーケンスが表される要素アクセス、反復子アクセス、反復子走査の各操作を追加します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename K,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>
>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>> class concurrent_unordered_set : public details::_Concurrent_hash<details::_Concurrent_unordered_set_traits<K,
    details::_Hash_compare<K,
 _Hasher,
    key_equality>,
 _Allocator_type,
    false>>;
```   
  
#### <a name="parameters"></a>パラメーター  
 `K`  
 キーの型。  
  
 `_Hasher`  
 ハッシュ関数のオブジェクト型。 この引数は省略可能であり、既定値は `std::hash<``K``>` です。  
  
 `key_equality`  
 等価比較関数のオブジェクト型。 この引数は省略可能であり、既定値は `std::equal_to<``K``>` です。  
  
 `_Allocator_type`  
 同時実行順序なしのセットのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は `std::allocator<``K``>` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`allocator_type`|ストレージを管理するためのアロケーターの型です。|  
|`const_iterator`|被制御シーケンスの定数反復子の型です。|  
|`const_local_iterator`|被制御シーケンスの定数バケット反復子の型です。|  
|`const_pointer`|要素への定数ポインターの型です。|  
|`const_reference`|要素への定数参照の型です。|  
|`difference_type`|2 つの要素間の距離を表す、符号付きの型です。|  
|`hasher`|ハッシュ関数の型です。|  
|`iterator`|被制御シーケンスの反復子の型です。|  
|`key_equal`|比較関数の型です。|  
|`key_type`|順序付けキーの型です。|  
|`local_iterator`|被制御シーケンスのバケット反復子の型です。|  
|`pointer`|要素へのポインターの型です。|  
|`reference`|要素への参照の型です。|  
|`size_type`|2 つの要素間の距離を表す、符号なしの型です。|  
|`value_type`|要素の型。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[concurrent_unordered_set コンス トラクター](#ctor)|オーバーロードされます。 同時実行順序なしのセットを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[hash_function メソッド](#hash_function)|格納されているハッシュ関数オブジェクトを返します。|  
|[insert メソッド](#insert)|オーバーロードされます。 要素を `concurrent_unordered_set` オブジェクトに追加します。|  
|[key_eq メソッド](#key_eq)|格納された等価比較関数のオブジェクトを返します。|  
|[swap メソッド](#swap)|2 つの `concurrent_unordered_set` オブジェクトのコンテンツを交換します。 このメソッドは同時実行セーフではありません。|  
|[unsafe_erase メソッド](#unsafe_erase)|オーバーロードされます。 `concurrent_unordered_set` から指定した位置にある要素を削除します。 このメソッドは同時実行セーフではありません。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator = 演算子](#operator_eq)|オーバーロードされます。 別の `concurrent_unordered_set` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドは同時実行セーフではありません。|  
  
## <a name="remarks"></a>コメント  
 詳細については、`concurrent_unordered_set`を参照してください[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_set`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concurrent_unordered_set.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>開始 

 同時実行コンテナーの最初の要素を指す反復子を返します。 このメソッドは同時実行セーフです。  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>戻り値  
 同時実行コンテナーの最初の要素を指す反復子。  
  
##  <a name="a-namecbegina-cbegin"></a><a name="cbegin"></a>cbegin 

 同時実行コンテナーの最初の要素を指す定数反復子を返します。 このメソッドは同時実行セーフです。  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>戻り値  
 同時実行コンテナーの最初の要素に定数反復子。  
  
##  <a name="a-namecenda-cend"></a><a name="cend"></a>cend 

 同時実行コンテナーの最後の要素の次の位置を指す定数反復子を返します。 このメソッドは同時実行セーフです。  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>戻り値  
 位置を同時実行コンテナーの最後の要素を指す定数反復子。  
  
##  <a name="a-namecleara-clear"></a><a name="clear"></a>オフ 

 同時実行コンテナー内のすべての要素を消去します。 この関数は、同時実行セーフではありません。  
  
```
void clear();
```  
  
##  <a name="a-namectora-concurrentunorderedset"></a><a name="ctor"></a>concurrent_unordered_set 

 同時実行順序なしのセットを構築します。  
  
```
explicit concurrent_unordered_set(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_set(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_set(_Iterator first,
    _Iterator last,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_set(
    const concurrent_unordered_set& _Uset);

concurrent_unordered_set(
    const concurrent_unordered_set& _Uset,
    const allocator_type& _Allocator);

concurrent_unordered_set(
    concurrent_unordered_set&& _Uset);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Iterator`  
 入力反復子の型。  
  
 `_Number_of_buckets`  
 この順序なしのセットのバケットの初期数。  
  
 `_Hasher`  
 この順序なしのセットのハッシュ関数。  
  
 `key_equality`  
 この順序なしのセットに対して等値比較関数。  
  
 `_Allocator`  
 この順序なしのセットのアロケーター。  
  
 `first`  
 `last`  
 `_Uset`  
 要素のコピー元または移動元の `concurrent_unordered_set` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 すべてのコンス トラクターは、アロケーター オブジェクトを格納`_Allocator`と順序なしのセットを初期化します。  
  
 最初のコンス トラクターでは、空の初期セットを指定し、明示的に指定、バケット数ハッシュ関数、等しいかどうかの関数やアロケーターを入力するためします。  
  
 2 番目のコンス トラクターでは、順序なしのセットのためのアロケーターを指定します。  
  
 3 番目のコンス トラクターは、反復子の範囲で指定される値を指定します。 [ `_Begin`、 `_End`)。  
  
 4 番目と&5; 番目のコンス トラクターは、同時実行順序なしのセットのコピーを指定します。`_Uset`します。  
  
 最後のコンス トラクターは、同時実行順序なしのセットの移動を指定`_Uset`します。  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>カウント 

 指定したキーに一致する要素の数をカウントします。 この関数は、同時実行セーフです。  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `KVal`  
 検索対象のキー。  
  
### <a name="return-value"></a>戻り値  
 コンテナーにキーが表示される回数の合計を回数です。  
  
##  <a name="a-nameemptya-empty"></a><a name="empty"></a>空 

 要素が存在しないかどうかをテストします。 このメソッドは同時実行セーフです。  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 `true`同時実行コンテナーが空である場合`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 同時実行の挿入が存在する場合、同時実行コンテナーが空かどうかは、戻り値があっても読み取る前にこの関数の呼び出し直後に変更できます。  
  
##  <a name="a-nameenda-end"></a><a name="end"></a>終わり 

 同時実行コンテナーの最後の要素の次の位置を指す反復子を返します。 このメソッドは同時実行セーフです。  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>戻り値  
 同時実行コンテナーの最後の要素の次の位置を指す反復子。  
  
##  <a name="a-nameequalrangea-equalrange"></a><a name="equal_range"></a>equal_range 

 指定したキーに一致する範囲を検索します。 この関数は、同時実行セーフです。  
  
```
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `KVal`  
 検索するキー値。  
  
### <a name="return-value"></a>戻り値  
 A[ペア](http://msdn.microsoft.com/en-us/32e72d66-3020-4cb9-92c3-f7a5fa7998ff)ここで最初の要素は、先頭を指す反復子は、2 番目の要素は、範囲の末尾を指す反復子。  
  
### <a name="remarks"></a>コメント  
 同時実行の挿入開始反復子と末尾の反復子の間に挿入される追加のキーが発生することができます。  
  
##  <a name="a-namefinda-find"></a><a name="find"></a>検索 

 指定したキーに一致する要素を検索します。 この関数は、同時実行セーフです。  
  
```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `KVal`  
 検索するキー値。  
  
### <a name="return-value"></a>戻り値  
 場所を指す反復子の指定したキーに一致する最初の要素または反復子`end()`このような要素が存在しない場合。  
  
##  <a name="a-namegetallocatora-getallocator"></a><a name="get_allocator"></a>get_allocator 

 この同時実行コンテナーの格納されたアロケーター オブジェクトを返します。 このメソッドは同時実行セーフです。  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>戻り値  
 この同時実行コンテナーの格納されたアロケーター オブジェクト。  
  
##  <a name="a-namehashfunctiona-hashfunction"></a><a name="hash_function"></a>hash_function 

 格納されているハッシュ関数オブジェクトを返します。  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>戻り値  
 格納されているハッシュ関数オブジェクト。  
  
##  <a name="a-nameinserta-insert"></a><a name="insert"></a>挿入 

 要素を `concurrent_unordered_set` オブジェクトに追加します。  
  
```
std::pair<iterator,
    bool> insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
std::pair<iterator,
    bool> insert(
    V&& value);

template<class V>
typename std::enable_if<!std::is_same<const_iterator,
    typename std::remove_reference<V>::type>::value,
    iterator>::type insert(
    const_iterator _Where,
    V&& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Iterator`  
 反復子の型を挿入するために使用します。  
  
 `V`  
 セットに挿入される値の型。  
  
 `value`  
 挿入する値。  
  
 `_Where`  
 挿入ポイントを検索する開始位置。  
  
 `first`  
 挿入する範囲の先頭。  
  
 `last`  
 挿入する範囲の末尾。  
  
### <a name="return-value"></a>戻り値  
 反復子とブール値を含むペア。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー関数では、キーを持つ、大小の順序で要素 X が存在するかどうかを判断`value`します。 場合は、このような要素 X を作成しで初期化`value`します。 反復子を判断し、 `where` X を指定します。挿入が発生したかどうか、関数を返します`std::pair(where, true)`します。 それ以外を返します`std::pair(where, false)`します。  
  
 2 番目のメンバー関数は、挿入を返します ( `value`) を使用して、`_Where`挿入ポイントを検索する被制御シーケンス内の第一歩として。  
  
 3 番目のメンバー関数は、範囲からの要素値のシーケンスを挿入します。 [ `first`、 `last`)。  
  
 最後の&2; つのメンバー関数の動作は同じことを除いて、最初の&2; つに`value`を使用して、挿入する値を作成します。  
  
##  <a name="a-namekeyeqa-keyeq"></a><a name="key_eq"></a>key_eq 

 格納された等価比較関数のオブジェクトを返します。  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>戻り値  
 格納された等価比較関数のオブジェクト。  
  
##  <a name="a-nameloadfactora-loadfactor"></a><a name="load_factor"></a>load_factor 

 計算し、コンテナーの現在のテーブル占有率を返します。 テーブル占有率は、バケットの数で割った値コンテナー内の要素の数です。  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーのテーブル占有率。  
  
##  <a name="a-namemaxloadfactora-maxloadfactor"></a><a name="max_load_factor"></a>max_load_factor 

 取得またはコンテナーの最大テーブル占有率を設定します。 コンテナーの内部テーブルを拡張するまで、バケット内で最大テーブル占有率は要素の最大数です。  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Newmax`  
  
### <a name="return-value"></a>戻り値  
 1 つ目のメンバー関数は、格納されている最大テーブル占有率を返します。 2 番目のメンバー関数は、値は返されませんが、スロー、 [out_of_range](../../../standard-library/out-of-range-class.md)例外の場合は、指定したテーブル占有率が正しくありません.  
  
##  <a name="a-namemaxsizea-maxsize"></a><a name="max_size"></a>max_size 

 アロケーターによって決定される、同時実行コンテナーの最大サイズを返します。 このメソッドは同時実行セーフです。  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>戻り値  
 この同時実行コンテナーに挿入できる要素の最大数。  
  
### <a name="remarks"></a>コメント  
 この上限値実際にどのようなコンテナー実際に保持できるよりも高い場合があります。  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

 別の `concurrent_unordered_set` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドは同時実行セーフではありません。  
  
```
concurrent_unordered_set& operator= (const concurrent_unordered_set& _Uset);

concurrent_unordered_set& operator= (concurrent_unordered_set&& _Uset);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Uset`  
 ソース `concurrent_unordered_set` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `concurrent_unordered_set` オブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 同時実行順序なしのセット内の既存の要素を消去した後`operator=`コピーまたは移動の内容`_Uset`セットを順序なしの同時にします。  
  
##  <a name="a-namerehasha-rehash"></a><a name="rehash"></a>rehash 

 ハッシュ テーブルをリビルドします。  
  
```
void rehash(size_type _Buckets);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Buckets`  
 目的のバケットの数。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、バケット数を `_Buckets` 以上に変更し、必要に応じて、ハッシュ テーブルをリビルドします。 バケット数は、2 のべき乗である必要があります。 場合いない 2 の累乗を最も近い 2 の累乗に切り上げられますされます。  
  
 スローされた、 [out_of_range](../../../standard-library/out-of-range-class.md)例外のバケットの数が無効な場合 (0 またはバケットの最大数より大きい)。  
  
##  <a name="a-namesizea-size"></a><a name="size"></a>サイズ 

 この同時実行コンテナーの要素の数を返します。 このメソッドは同時実行セーフです。  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>戻り値  
 コンテナー内の項目の数。  
  
### <a name="remarks"></a>コメント  
 同時実行の挿入が存在する場合は、同時実行コンテナーの要素の数は、戻り値があっても読み取る前にこの関数を呼び出した直後後変更できます。  
  
##  <a name="a-nameswapa-swap"></a><a name="swap"></a>スワップ 

 2 つの `concurrent_unordered_set` オブジェクトのコンテンツを交換します。 このメソッドは同時実行セーフではありません。  
  
```
void swap(concurrent_unordered_set& _Uset);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Uset`  
 `concurrent_unordered_set`交換するオブジェクト。  
  
##  <a name="a-nameunsafebegina-unsafebegin"></a><a name="unsafe_begin"></a>unsafe_begin 

 特定のバケットのこのコンテナー内の最初の要素を反復子を返します。  
  
```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Bucket`  
 バケットのインデックス。  
  
### <a name="return-value"></a>戻り値  
 バケットの先頭を指す反復子。  
  
##  <a name="a-nameunsafebucketa-unsafebucket"></a><a name="unsafe_bucket"></a>unsafe_bucket 

 このコンテナー内に特定のキーがマップされるバケットのインデックスを返します。  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `KVal`  
 検索対象の要素キー。  
  
### <a name="return-value"></a>戻り値  
 このコンテナー内のキーのバケットのインデックス。  
  
##  <a name="a-nameunsafebucketcounta-unsafebucketcount"></a><a name="unsafe_bucket_count"></a>unsafe_bucket_count 

 このコンテナーの現在のバケット数を返します。  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>戻り値  
 現在このコンテナー内のバケットの数。  
  
##  <a name="a-nameunsafebucketsizea-unsafebucketsize"></a><a name="unsafe_bucket_size"></a>unsafe_bucket_size 

 このコンテナーの特定のバケット内の項目の数を返します。  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Bucket`  
 検索するバケット。  
  
### <a name="return-value"></a>戻り値  
 現在このコンテナー内のバケットの数。  
  
##  <a name="a-nameunsafecbegina-unsafecbegin"></a><a name="unsafe_cbegin"></a>unsafe_cbegin 

 特定のバケットのこのコンテナー内の最初の要素を反復子を返します。  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Bucket`  
 バケットのインデックス。  
  
### <a name="return-value"></a>戻り値  
 バケットの先頭を指す反復子。  
  
##  <a name="a-nameunsafecenda-unsafecend"></a><a name="unsafe_cend"></a>unsafe_cend 

 位置を特定のバケットの最後の要素を指す反復子を返します。  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Bucket`  
 バケットのインデックス。  
  
### <a name="return-value"></a>戻り値  
 バケットの先頭を指す反復子。  
  
##  <a name="a-nameunsafeenda-unsafeend"></a><a name="unsafe_end"></a>unsafe_end 

 特定のバケットのこのコンテナーの最後の要素を反復子を返します。  
  
```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Bucket`  
 バケットのインデックス。  
  
### <a name="return-value"></a>戻り値  
 バケットの末尾を指す反復子。  
  
##  <a name="a-nameunsafeerasea-unsafeerase"></a><a name="unsafe_erase"></a>unsafe_erase 

 `concurrent_unordered_set` から指定した位置にある要素を削除します。 このメソッドは同時実行セーフではありません。  
  
```
iterator unsafe_erase(
    const_iterator _Where);

size_type unsafe_erase(
    const key_type& KVal);

iterator unsafe_erase(
    const_iterator first,
    const_iterator last);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Where`  
 消去する反復子の位置。  
  
 `KVal`  
 消去するキー値。  
  
 `first`  
 `last`  
  
### <a name="return-value"></a>戻り値  
 最初の&2; つのメンバー関数は、削除された要素の後に残る最初の要素を指定する反復子を返すか、[メソッドを終了](#end)() このような要素が存在しない場合。 3 つ目のメンバー関数は削除する要素の数を返します。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー関数は、`_Where` が指す要素を削除します。 2 番目のメンバー関数は、範囲内の要素の削除 [ `_Begin`、 `_End`)。  
  
 3 番目のメンバー関数で区切られた範囲内の要素を削除する[equal_range メソッド](#equal_range)(KVal)。  
  
##  <a name="a-nameunsafemaxbucketcounta-unsafemaxbucketcount"></a><a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count 

 このコンテナーのバケットの最大数を返します。  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>戻り値  
 このコンテナー内のバケットの最大数。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)




