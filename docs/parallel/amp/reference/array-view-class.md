---
title: "array_view クラス | Microsoft Docs"
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
  - "amp/Concurrency::array_view"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array_view クラス"
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# array_view クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

別のコンテナーに保持されるデータの N 次元のビューを表します。  
  
## <a name="syntax"></a>構文  
  
```  
template <
    typename value_type,  
    int _Rank = 1  
>  
class array_view : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;  
 
template <
    typename value_type,  
    int _Rank  
>  
class array_view<const value_type, _Rank> : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `value_type`  
 `array_view` オブジェクトの要素のデータ型。  
  
 `_Rank`  
 `array_view` オブジェクトのランク。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[array_view::array_view コンス トラクター](#array_view__array_view_constructor)|`array_view` クラスの新しいインスタンスを初期化します。 `array<T,N>` の既定のコンストラクターがありません。 すべてのコンストラクターは、CPU 上のみで実行されるように制限されており、Direct3D ターゲット上で実行することはできません。|  
|[array_view:: ~ array_view デストラクター](#array_view___dtorarray_view_destructor)|`array_view` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[array_view::copy_to メソッド](#array_view__copy_to_method)|`array_view` を呼び出して `copy(*this, dest)` オブジェクトの内容を指定されたコピー先にコピーします。|  
|[array_view::data メソッド](#array_view__data_method)|`array_view` の生データへのポインターを返します。|  
|[array_view::discard_data メソッド](#array_view__discard_data_method)|このビューの基となる現在のデータを破棄します。|  
|[array_view::get_extent メソッド](#array_view__get_extent_method)|array_view オブジェクトの範囲オブジェクトを返します。|  
|[array_view::get_ref メソッド](#array_view__get_ref_method)|インデックス付けされた要素への参照を返します。|  
|[array_view::get_source_accelerator_view メソッド](#array_view__get_source_accelerator_view_method)|返します。、 [accelerator_view](../Topic/accelerator_view%20Class.md) 場所のデータ ソース、 `array_view` が配置されています。|  
|[array_view::refresh メソッド](#array_view__refresh_method)|バインドされたメモリが `array_view` インターフェイスの外部で変更されたことを `array_view` オブジェクトに通知します。 このメソッドの呼び出しによって、すべてのキャッシュされた情報が表示されます。|  
|[array_view::reinterpret_as メソッド](#array_view__reinterpret_as_method)|`array_view` オブジェクトのすべての要素を含む 1 次元配列を返します。|  
|[array_view::section メソッド](#array_view__section_method)|指定された原点に `array_view` オブジェクトのサブセクションを返し、これは必要に応じて範囲が指定されます。|  
|[array_view::synchronize メソッド](#array_view__synchronize_method)|`array_view` オブジェクトへの変更をそのソース データに同期して戻します。|  
|[array_view::synchronize_async メソッド](#array_view__synchronize_async_method)|非同期的に行われた変更を同期化、 [array_view](../../../parallel/amp/reference/array-view-class.md) そのソース データへのオブジェクト。|  
|[array_view::synchronize_to メソッド](#array_view__synchronize_to_method)|変更を同期化、 `array_view` を指定したオブジェクト [accelerator_view](../Topic/accelerator_view%20Class.md)します。|  
|[array_view::synchronize_to_async メソッド](#array_view__synchronize_to_async_method)|非同期的に行われた変更を同期化、 `array_view` を指定したオブジェクト [accelerator_view](../Topic/accelerator_view%20Class.md)します。|  
|[array_view::view_as メソッド](#array_view__view_as_method)|この `array_view` を使用して異なるランクの `array_view` オブジェクトを生成します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[array_view::operator() 演算子](#array_view__operator___operator)|パラメーターによって指定された要素の値を返します。|  
|[array_view::operator[] 演算子](#array_view__operator_at_operator)|パラメーターで指定された要素を返します。|  
|[array_view::operator = 演算子](#array_view__operator_eq_operator)|指定された `array_view` オブジェクトの内容をこのオブジェクトにコピーします。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[array_view::rank 定数](#array_view__rank_constant)|`array_view` オブジェクトのランクを格納します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[array_view::extent データ メンバー](#array_view__extent_data_member)|`extent` オブジェクトの形状を定義する `array_view` オブジェクトを取得します。|  
|[array_view::source_accelerator_view データ メンバー](#array_view__source_accelerator_view_data_member)|取得、 [accelerator_view](../Topic/accelerator_view%20Class.md) 場所のデータ ソース、 `array_view` があります。|  
|[array_view::value_type データ メンバー](#array_view__value_type_data_member)|`array_view` の値型およびバインド配列。|  
  
## <a name="remarks"></a>コメント  
  `array_view` クラスに含まれているデータのビューを表す、 [配列](../../../parallel/amp/reference/array-class.md) オブジェクトまたはのサブセクション、 `array` オブジェクトです。  
  
 ソース データが格納されている (ローカル)、または別のアクセラレータまたはコヒーレンス ドメイン (リモート) 上の、`array_view` オブジェクトにアクセスできます。 オブジェクトにリモートにアクセスすると、ビューは必要に応じてコピーされ、キャッシュされます。 自動キャッシュの効果を除いて、`array_view` オブジェクトには `array` オブジェクトと同様のパフォーマンス プロファイルがあります。 ビューを使用してデータにアクセスする場合、パフォーマンスがわずかに低下します。  
  
 リモートでの使用には次の 3 つの方法があります。  
  
-   システム メモリ ポインターへのビューが渡される、 [parallel_for_each](concurrency%20namespace%20functions.md#parallel_for_each) アクセラレータを呼び出すし、アクセラレータでアクセスします。  
  
-   アクセラレータにある配列へのビューは、別のアクセラレータへの `parallel_for_each` 呼び出しによって渡され、そこでアクセスされます。  
  
-   アクセラレータにある配列へのビューは CPU 上でアクセスされます。  
  
 これらのシナリオのいずれかで、参照されたビューは、リモートの場所へのランタイムによってコピーされ、`array_view` オブジェクトへの呼び出しによって変更される場合は、ローカルの場所へコピーして戻されます。 ランタイムは、変更をコピーして戻す処理を最適化する場合、変更された要素のみをコピーする場合、または変更されない部分もコピーする場合があります。 1 つのデータ ソースで `array_view` オブジェクトが重複すると、リモートの場所での参照整合性の維持が保証されません。  
  
 同じデータ ソースに対するマルチスレッド アクセスを同期する必要があります。  
  
 ランタイムは `array_view` オブジェクトのデータのキャッシュに関連して次の内容を保証します。  
  
-   プログラムの順序での `array` オブジェクトと `array_view` オブジェクトへのすべての完全同期アクセスは、逐次事前発生リレーションシップに従います。  
  
-   単一の `array_view` オブジェクトの同じアクセラレータ上で重複する `array` オブジェクトへのすべての完全同期アクセスは、`array` オブジェクトを使用してエイリアス化されます。 これらは、プログラムの順序に従う合計事前発生リレーションシップを引き起こします。 キャッシュはありません。 `array_view` オブジェクトが異なるアクセラレータで実行されている場合、アクセスの順序は未定義で、競合状態を作成します。  
  
 システム メモリのポインターを使用して `array_view` オブジェクトを作成する場合、`array_view` ポインターのみを使用してビュー `array_view` オブジェクトを変更する必要があります。 また、`refresh()` オブジェクトを使用せずに、基になるネイティブ メモリが直接変更される場合は、システム ポインターに添付されている `array_view` オブジェクトの 1 つに `array_view` を呼び出す必要があります。  
  
 どちらの操作も、基になるネイティブ メモリが変更されていること、およびアクセラレータ内にあるコピーが古くなっていることを `array_view` オブジェクトに通知します。 これらのガイドラインに従う場合、ポインター ベースのビューはデータ並列配列のビューに提供されるビューと同じです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_Array_view_shape`  
  
 `_Array_view_base`  
  
 `array_view`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  
  
##  <a name="a-namearrayviewdtorarrayviewdestructora-arrayviewarrayview-destructor"></a><a name="array_view___dtorarray_view_destructor"></a>  array_view:: ~ array_view デストラクター  
 破棄、 [array_view](../../../parallel/amp/reference/array-view-class.md) オブジェクトです。  
  
```  
~array_view()restrict(amp,cpu);
```  
  
##  <a name="a-namearrayviewarrayviewconstructora-arrayviewarrayview-constructor"></a><a name="array_view__array_view_constructor"></a>  array_view::array_view コンス トラクター  
 新しいインスタンスを初期化、 [array_view](../../../parallel/amp/reference/array-view-class.md) クラスです。  
  
```  
array_view(
    array<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view& _Other)restrict(amp,cpu);

 
explicit array_view(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

 
template <
    typename _Container  
>  
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    _Container& _Src) restrict(cpu);

 
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    value_type* _Src)restrict(amp,cpu);

 
explicit array_view(
    int _E0) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    _Container& _Src,  
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    _Container& _Src) restrict(cpu);

 
explicit array_view(
    int _E0,  
    int _E1) __CPU_ONLY;  
 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    int _E1,  
    _Container& _Src) restrict(cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2) __CPU_ONLY;  
 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    _Container& _Src);

 
explicit array_view(
    int _E0,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
template <
    typename _Arr_type,  
    int _Size  
>  
explicit array_view(
    _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
array_view(
    const array<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view<const value_type, _Rank>& _Src)restrict(amp,cpu);

 
template <
    typename _Container  
>  
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    const _Container& _Src) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    const _Container& _Src,  
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

 
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    const value_type* _Src)restrict(amp,cpu);

 
template <
    typename _Arr_type,  
    int _Size  
>  
explicit array_view(
    const _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    const _Container& _Src);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    int _E1,  
    const _Container& _Src);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    const _Container& _Src);

 
array_view(
    int _E0,  
    const value_type* _Src)restrict(amp,cpu);

 
array_view(
    int _E0,  
    int _E1,  
    const value_type* _Src) restrict(amp,cpu);

 
array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    const value_type* _Src) restrict(amp,cpu);

 
```  
  
### <a name="parameters"></a>パラメーター  
 `_Arr_type`  
 データが提供される C スタイルの配列の要素型。  
  
 `_Container`  
 `data()` メンバーおよび `size()` メンバーをサポートする線形コンテナーを指定する必要があるテンプレート引数。  
  
 `_E0`  
 このセクションの範囲の最上位のコンポーネント。  
  
 `_E1`  
 このセクションの範囲の最上位の次のコンポーネント。  
  
 `_E2`  
 このセクションの範囲の最下位のコンポーネント。  
  
 `_Extent`  
 この `array_view` の各次元の範囲。  
  
 `_Other`  
 新しい `array_view<T,N>` の初期化に使用する `array_view` 型のオブジェクト。  
  
 `_Size`  
 データが提供される C スタイルの配列のサイズ。  
  
 `_Src`  
 新しい配列にコピーされるソース データへのポインター。  
  
##  <a name="a-namearrayviewcopytomethoda-arrayviewcopyto-method"></a><a name="array_view__copy_to_method"></a>  array_view::copy_to メソッド  
 内容をコピー、 [array_view](../../../parallel/amp/reference/array-view-class.md) オブジェクトを呼び出すことによって指定されたコピー先のオブジェクトに `copy(*this, dest)`します。  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const;

 
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 コピー先のオブジェクト。  
  
##  <a name="a-namearrayviewdatamethoda-arrayviewdata-method"></a><a name="array_view__data_method"></a>  array_view::data メソッド  
 ポインターの生データを返し、 [array_view](../../../parallel/amp/reference/array-view-class.md)します。  
  
```  
value_type* data() const restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>戻り値  
 生データへのポインター、 `array_view`です。  
  
##  <a name="a-namearrayviewdiscarddatamethoda-arrayviewdiscarddata-method"></a><a name="array_view__discard_data_method"></a>  array_view::discard_data メソッド  
 このビューの基となる現在のデータを破棄します。 これは、ビューの現在の内容をアクセスしているターゲット `accelerator_view` にコピーしないようにするために使用するランタイムの最適化のためのヒントで、既存の内容が必要ではない場合に使用することをお勧めします。 restrict(amp) コンテキストで使用される場合、このメソッドは実行されません。  
  
```  
void discard_data() const restrict(cpu);
```  
  
##  <a name="a-namearrayviewextentdatamembera-arrayviewextent-data-member"></a><a name="array_view__extent_data_member"></a>  array_view::extent データ メンバー  
 `extent` オブジェクトの形状を定義する `array_view` オブジェクトを取得します。  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namearrayviewgetextentmethoda-arrayviewgetextent-method"></a><a name="array_view__get_extent_method"></a>  array_view::get_extent メソッド  
 返します。、 [エクステント](../Topic/extent%20Class%20\(C++%20AMP\).md) のオブジェクト、 [array_view](../../../parallel/amp/reference/array-view-class.md) オブジェクトです。  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```  
  
### <a name="return-value"></a>戻り値  
  `extent` のオブジェクト、 `array_view` オブジェクト  
  
##  <a name="a-namearrayviewgetrefmethoda-arrayviewgetref-method"></a><a name="array_view__get_ref_method"></a>  array_view::get_ref メソッド  
 _Index によってインデックス付けされた要素への参照を取得します。 CPU の array_view にアクセスするための他のインデックス作成演算子とは異なり、このメソッドは CPU にこの array_view の内容を暗黙的に同期しません。 リモートの場所で array_view にアクセスしたり、この array_view を含むコピー操作を実行したりした後は、このメソッドを呼び出す前に array_view を CPU に明示的に同期する必要があります。 これができない場合は、未定義の動作が発生します。  
  
```  
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 インデックス。  
  
### <a name="return-value"></a>戻り値  
 _Index によってインデックス付けされた要素への参照  
  
##  <a name="a-namearrayviewgetsourceacceleratorviewmethoda-arrayviewgetsourceacceleratorview-method"></a><a name="array_view__get_source_accelerator_view_method"></a>  array_view::get_source_accelerator_view メソッド  
 array_view のデータ ソースが存在する accelerator_view を返します。 array_view にデータ ソースがない場合、この API は runtime_exception をスローします  
  
```  
accelerator_view get_source_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-namearrayviewoperatoroperatora-arrayviewoperator-operator"></a><a name="array_view__operator___operator"></a>  array_view::operator() 演算子  
 パラメーターによって指定された要素の値を返します。  
  
```  
value_type& operator() (
    const index<_Rank>& _Index) const restrict(amp,cpu);

 
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator() (
    int _I) const restrict(amp,cpu);

 
value_type& operator() (
    int _I0,  
    int _I1) const restrict(amp,cpu);

 
value_type& operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp,cpu);

 
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator() (
    int _I) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 要素の場所。  
  
 `_I0`  
 最初の次元のインデックス。  
  
 `_I1`  
 2 番目の次元のインデックス。  
  
 `_I2`  
 3 番目の次元のインデックス。  
  
 `_I`  
 要素の場所。  
  
### <a name="return-value"></a>戻り値  
 パラメーターによって指定された要素の値。  
  
##  <a name="a-namearrayviewoperatoratoperatora-arrayviewoperator-operator"></a><a name="array_view__operator_at_operator"></a>  array_view::operator[] 演算子  
 パラメーターで指定された要素を返します。  
  
```  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

 
value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 インデックス。  
  
 `_I`  
 インデックス。  
  
### <a name="return-value"></a>戻り値  
 インデックスでの要素の値、または最上位の次元に投影される `array_view`。  
  
##  <a name="a-namearrayviewoperatoreqoperatora-arrayviewoperator-operator"></a><a name="array_view__operator_eq_operator"></a>  array_view::operator = 演算子  
 指定した内容をコピー [array_view](../../../parallel/amp/reference/array-view-class.md) オブジェクトをこのオブジェクトにします。  
  
```  
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

 
array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピー元の `array_view` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `array_view` オブジェクトへの参照。  
  
##  <a name="a-namearrayviewrankconstanta-arrayviewrank-constant"></a><a name="array_view__rank_constant"></a>  array_view::rank 定数  
 ランクを格納、 [array_view](../../../parallel/amp/reference/array-view-class.md) オブジェクトです。  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namearrayviewrefreshmethoda-arrayviewrefresh-method"></a><a name="array_view__refresh_method"></a>  array_view::refresh メソッド  
 通知、 [array_view](../../../parallel/amp/reference/array-view-class.md) バインドされたメモリが外部で変更されたオブジェクト、 `array_view` インターフェイスです。 このメソッドの呼び出しによって、すべてのキャッシュされた情報が表示されます。  
  
```  
void refresh() const restrict(cpu);
```  
  
##  <a name="a-namearrayviewsectionmethoda-arrayviewsection-method"></a><a name="array_view__section_method"></a>  array_view::section メソッド  
 サブセクションを返し、 [array_view](../../../parallel/amp/reference/array-view-class.md) 指定された原点、必要に応じて、これはオブジェクトがどの程度消費して指定します。  
  
```  
array_view section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

 
array_view section(
    const Concurrency::index<_Rank>& _Idx) const restrict(amp,cpu);

 
array_view section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _E0) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_E0`  
 このセクションの範囲の最上位のコンポーネント。  
  
 `_E1`  
 このセクションの範囲の最上位の次のコンポーネント。  
  
 `_E2`  
 このセクションの範囲の最下位のコンポーネント。  
  
 `_Ext`  
  [エクステント](../Topic/extent%20Class%20\(C++%20AMP\).md) セクションの範囲を指定するオブジェクト。 原点は 0 です。  
  
 `_Idx`  
  [インデックス](../../../parallel/amp/reference/index-class.md) 原点の位置を指定するオブジェクト。 サブセクションは残りの範囲です。  
  
 `_I0`  
 このセクションの原点の最上位のコンポーネント。  
  
 `_I1`  
 このセクションの原点の最上位の次のコンポーネント。  
  
 `_I2`  
 このセクションの原点の最下位のコンポーネント。  
  
 `_Rank`  
 セクションのランク。  
  
 `_Section_extent`  
  [エクステント](../Topic/extent%20Class%20\(C++%20AMP\).md) セクションの範囲を指定するオブジェクト。  
  
 `_Section_origin`  
  [インデックス](../../../parallel/amp/reference/index-class.md) 原点の位置を指定するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 指定された原点にある `array_view` オブジェクトのサブセクションで、これは必要に応じて範囲が指定されます。 `index` のオブジェクトのみを指定すると、サブセクションには `index` オブジェクトの要素のインデックスより大きなインデックスを持つ関連する範囲のすべての要素が含まれます。  
  
##  <a name="a-namearrayviewsourceacceleratorviewdatamembera-arrayviewsourceacceleratorview-data-member"></a><a name="array_view__source_accelerator_view_data_member"></a>  array_view::source_accelerator_view データ メンバー  
 この array_view が関連付けられているソースの accelerator_view を取得します。  
  
```  
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;  
```  
  
##  <a name="a-namearrayviewsynchronizemethoda-arrayviewsynchronize-method"></a><a name="array_view__synchronize_method"></a>  array_view::synchronize メソッド  
 `array_view` オブジェクトへの変更をそのソース データに同期して戻します。  
  
```  
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize() const restrict(cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Access_type`  
 目的の [access_type](concurrency%20namespace%20enums.md#access_type) ターゲットで [accelerator_view](../Topic/accelerator_view%20Class.md)します。 このパラメーターには `access_type_read` の既定値があります。  
  
##  <a name="a-namearrayviewsynchronizeasyncmethoda-arrayviewsynchronizeasync-method"></a><a name="array_view__synchronize_async_method"></a>  array_view::synchronize_async メソッド  
 非同期的に行われた変更を同期化、 [array_view](../../../parallel/amp/reference/array-view-class.md) そのソース データへのオブジェクト。  
  
```  
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_async() const restrict(cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Access_type`  
 目的の [access_type](concurrency%20namespace%20enums.md#access_type) ターゲットで [accelerator_view](../Topic/accelerator_view%20Class.md)します。 このパラメーターには `access_type_read` の既定値があります。  
  
### <a name="return-value"></a>戻り値  
 操作の完了を待機する予定。  
  
##  <a name="a-namearrayviewsynchronizetomethoda-arrayviewsynchronizeto-method"></a><a name="array_view__synchronize_to_method"></a>  array_view::synchronize_to メソッド  
 この array_view に行われた変更を指定された accelerator_view と同期します。  
  
```  
void synchronize_to(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Accl_view`  
 同期ターゲットの accelerator_view。  
  
 `_Access_type`  
 ターゲットの accelerator_view の必要な access_type。 このパラメーターには access_type_read の既定値があります。  
  
##  <a name="a-namearrayviewsynchronizetoasyncmethoda-arrayviewsynchronizetoasync-method"></a><a name="array_view__synchronize_to_async_method"></a>  array_view::synchronize_to_async メソッド  
 この array_view に行われた変更を指定された accelerator_view と非同期に同期します。  
  
```  
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Accl_view`  
 同期ターゲットの accelerator_view。  
  
 `_Access_type`  
 ターゲットの accelerator_view の必要な access_type。 このパラメーターには access_type_read の既定値があります。  
  
### <a name="return-value"></a>戻り値  
 操作の完了を待機する予定。  
  
##  <a name="a-namearrayviewvaluetypedatamembera-arrayviewvaluetype-data-member"></a><a name="array_view__value_type_data_member"></a>  array_view::value_type データ メンバー  
 array_view の値型およびバインド配列。  
  
```  
typedef typenamevalue_type value_type;  
```  
  
##  <a name="a-namearrayviewviewasmethoda-arrayviewviewas-method"></a><a name="array_view__view_as_method"></a>  array_view::view_as メソッド  
 異なるランクの `array_view` としてこの `array_view` を再解釈します。  
  
```  
template <
    int _New_rank  
>  
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);

 
template <
    int _New_rank  
>  
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank> _View_extent) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_New_rank`  
 新しい `array_view` オブジェクトのランク。  
  
 `_View_extent`  
 変形を行う `extent`。  
  
 `value_type`  
 元の両方の要素のデータ型 [配列](../../../parallel/amp/reference/array-class.md) オブジェクトおよび返された `array_view` オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
  [Array_view](../../../parallel/amp/reference/array-view-class.md) 作成されたオブジェクト。  
  
## <a name="see-also"></a>「  
 [Concurrency 名前空間 (C++ AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
