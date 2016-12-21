---
title: "array クラス | Microsoft Docs"
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
  - "amp/Concurrency::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array クラス"
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
caps.latest.revision: 31
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# array クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

データをアクセラレータに移動するために使用するデータ コンテナーを表します。  
  
## <a name="syntax"></a>構文  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
friend class array;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `value_type`  
 データの要素型。  
  
 `_Rank`  
 配列のランク。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[array::array コンス トラクター](#array__array_constructor)|`array` クラスの新しいインスタンスを初期化します。|  
|[配列:: ~ array デストラクター](#array___dtorarray_destructor)|`array` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[array::copy_to メソッド](#array__copy_to_method)|array の内容を別の array にコピーします。|  
|[array::data メソッド](#array__data_method)|配列の生データへのポインターを返します。|  
|[array::get_accelerator_view メソッド](#array__get_accelerator_view_method)|返します。、 [accelerator_view](../Topic/accelerator_view%20Class.md) 配列が割り当てられた場所を表すオブジェクト。 このプロパティは CPU 上でのみアクセスできます。|  
|[array::get_associated_accelerator_view メソッド](#array__get_associated_accelerator_view_method)|2 番目の取得 [accelerator_view](../Topic/accelerator_view%20Class.md) をインスタンス化するステージング コンス トラクターが呼び出されたときに、パラメーターとして渡されるオブジェクト、 [配列](../../../parallel/amp/reference/array-class.md) オブジェクトです。|  
|[array::get_cpu_access_type メソッド](#array__get_cpu_access_type_method)|返します。、 [access_type](access_type%20Enumeration.md) の配列。 このメソッドは CPU 上でのみアクセスできます。|  
|[array::get_extent メソッド](#array__get_extent_method)|返します。、 [エクステント](../Topic/extent%20Class%20\(C++%20AMP\).md) 配列のオブジェクト。|  
|[array::reinterpret_as メソッド](#array__reinterpret_as_method)|`array` オブジェクトのすべての要素を含む 1 次元配列を返します。|  
|[array::section メソッド](#array__section_method)|サブセクションを返し、 [配列](../../../parallel/amp/reference/array-class.md) 指定された原点、必要に応じて、これはオブジェクトがどの程度消費して指定します。|  
|[array::view_as メソッド](#array__view_as_method)|返します。、 [array_view](../../../parallel/amp/reference/array-view-class.md) から作成されたオブジェクト、 `array` オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[array::operator std::vector&lt;value_type&gt; 演算子](#array__operator_std__vector_lt__value_type_gt__operator)|使用して `copy(*this, vector)` へ暗黙的に変換、配列、std::[ベクトル](../../../standard-library/vector-class.md) オブジェクトです。|  
|[array::operator() 演算子](#array__operator___operator)|パラメーターによって指定された要素の値を返します。|  
|[array::operator[] 演算子](#array__operator_at_operator)|指定したインデックス位置にある要素を返します。|  
|[array::operator = 演算子](#array__operator_eq_operator)|指定された `array` オブジェクトの内容をこのオブジェクトにコピーします。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[array::rank 定数](#array__rank_constant)|配列のランクを格納します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[array::accelerator_view データ メンバー](#array__accelerator_view_data_member)|取得、 [accelerator_view](../Topic/accelerator_view%20Class.md) 配列が割り当てられた場所を表すオブジェクト。 このプロパティは CPU 上でのみアクセスできます。|  
|[array::associated_accelerator_view データ メンバー](#array__associated_accelerator_view_data_member)|2 番目の取得 [accelerator_view](../Topic/accelerator_view%20Class.md) をインスタンス化するステージング コンス トラクターが呼び出されたときに、パラメーターとして渡されるオブジェクト、 [配列](../../../parallel/amp/reference/array-class.md) オブジェクトです。|  
|[array::cpu_access_type データ メンバー](#array__cpu_access_type_data_member)|取得、 [access_type](access_type%20Enumeration.md) CPU が配列の記憶域にアクセスする方法を表します。|  
|[array::extent データ メンバー](#array__extent_data_member)|配列の図形を定義する範囲を取得します。|  
  
## <a name="remarks"></a>コメント  
 種類 `array<T,N>` 、密で正規を表します (ギザギザにならず) *N*-アクセラレータや CPU などの特定の場所に配置されている次元の配列。 配列の要素のデータ型は `T` で、ターゲット アクセラレータと互換性のある型である必要があります。 ランクは `N` であり、配列のランクは静的に決定され、型の一部です。配列の範囲は、ランタイムによって決定され、`extent<N>` クラスを使用して表されます。  
  
 いくつかの機能は、ランク 1、2、および 3 で `array` オブジェクトに特化していますが、配列はどの次元数も指定できます。 次元の引数を省略すると、既定値は 1 です。  
  
 配列データはメモリ内に連続して配置されます。 最下位の次元で "1" 異なる要素はメモリでは隣接しています。  
  
 配列が別の配列にコピーされる場合は詳細コピーが実行されるため、配列は論理的に値型であると見なされます。 2 つの配列が同じデータを指すことはありません。  
  
 `array<T,N>` 型はいくつかのシナリオで使用されます。  
  
-   アクセラレータの計算で使用できるデータ コンテナーとして。  
  
-   ホスト CPU にメモリを保持するデータ コンテナーとして (他の配列との間でコピーするために使用できます)。  
  
-   ホストとデバイス間のコピーの高速の仲介役として機能するステージング オブジェクトとして。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `array`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  
  
##  <a name="a-namearraydtorarraydestructora-arrayarray-destructor"></a><a name="array___dtorarray_destructor"></a>  配列:: ~ array デストラクター  
 `array` オブジェクトを破棄します。  
  
```  
~array() restrict(cpu);
```  
  
##  <a name="a-namearrayacceleratorviewdatamembera-arrayacceleratorview-data-member"></a><a name="array__accelerator_view_data_member"></a>  array::accelerator_view データ メンバー  
 取得、 [accelerator_view](../Topic/accelerator_view%20Class.md) 配列が割り当てられた場所を表すオブジェクト。 このプロパティは CPU 上でのみアクセスできます。  
  
```  
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;  
```  
  
##  <a name="a-namearrayarrayconstructora-arrayarray-constructor"></a><a name="array__array_constructor"></a>  array::array コンス トラクター  
 新しいインスタンスを初期化、 [array クラス](../../../parallel/amp/reference/array-class.md)します。 `array<T,N>` の既定のコンストラクターがありません。 すべてのコンストラクターは CPU でのみ実行されます。 これらは、Direct3D ターゲットで実行することはできません。  
  
```  
explicit array(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

 
explicit array(
    int _E0) restrict(cpu);

 
explicit array(
    int _E0,  
    int _E1) restrict(cpu);

 
explicit array(
    int _E0,  
    int _E1,  
    int _E2) restrict(cpu);

 
array(
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
array(
    int _E0,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
array(
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
array(
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
array(
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
array(
    int _E0,  
    accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
array(
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
array(
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
explicit array(
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);

 
array(
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
array(
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av,  
    accelerator_view _Associated_Av) restrict(cpu);

 
array(
    const array& _Other) restrict(cpu);

 
array(
    array&& _Other) restrict(cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Associated_Av`  
 配列の優先ターゲットの位置を指定する accelerator_view。  
  
 `_Av`  
  [Accelerator_view](../Topic/accelerator_view%20Class.md) 配列の位置を指定するオブジェクト。  
  
 `_Cpu_access_type`  
 必要な [access_type](access_type%20Enumeration.md)  CPU 上の配列。 このパラメーターには、CPU の `access_type_auto` 決定をランタイムに任せる `access_type` の既定値があります。 配列の実際の CPU `access_type` は `get_cpu_access_type` メソッドを使用してクエリを実行できます。  
  
 `_Extent`  
 配列の各次元の範囲。  
  
 `_E0`  
 このセクションの範囲の最上位のコンポーネント。  
  
 `_E1`  
 このセクションの範囲の最上位の次のコンポーネント。  
  
 `_E2`  
 このセクションの範囲の最下位のコンポーネント。  
  
 `_InputIterator`  
 入力列挙子の型。  
  
 `_Src`  
 コピーするオブジェクト。  
  
 `_Src_first`  
 ソース コンテナーへの先頭の反復子。  
  
 `_Src_last`  
 ソース コンテナーへの終了の反復子。  
  
 `_Other`  
 その他のデータ ソース。  
  
 `_Rank`  
 セクションのランク。  
  
 `value_type`  
 コピーされた要素のデータ型。  
  
##  <a name="a-namearrayassociatedacceleratorviewdatamembera-arrayassociatedacceleratorview-data-member"></a><a name="array__associated_accelerator_view_data_member"></a>  array::associated_accelerator_view データ メンバー  
 2 番目の取得 [accelerator_view](../Topic/accelerator_view%20Class.md) をインスタンス化するステージング コンス トラクターが呼び出されたときに、パラメーターとして渡されるオブジェクト、 [配列](../../../parallel/amp/reference/array-class.md) オブジェクトです。  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="a-namearraycopytomethoda-arraycopyto-method"></a><a name="array__copy_to_method"></a>  array::copy_to メソッド  
 内容をコピー、 [配列](../../../parallel/amp/reference/array-class.md) 間 `array`します。  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const ;  
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
  [Array_view](../../../parallel/amp/reference/array-view-class.md) コピー先のオブジェクト。  
  
##  <a name="a-namearraycpuaccesstypedatamembera-arraycpuaccesstype-data-member"></a><a name="array__cpu_access_type_data_member"></a>  array::cpu_access_type データ メンバー  
 この配列に許可されている CPU access_type を取得します。  
  
```  
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;  
```  
  
##  <a name="a-namearraydatamethoda-arraydata-method"></a><a name="array__data_method"></a>  array::data メソッド  
 ポインターの生データを返し、 [配列](../../../parallel/amp/reference/array-class.md)します。  
  
```  
value_type* data() restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>戻り値  
 配列の生データへのポインター。  
  
##  <a name="a-namearrayextentdatamembera-arrayextent-data-member"></a><a name="array__extent_data_member"></a>  array::extent データ メンバー  
 取得、 [エクステント](../Topic/extent%20Class%20\(C++%20AMP\).md) の形状を定義するオブジェクト、 [配列](../../../parallel/amp/reference/array-class.md)します。  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namearraygetacceleratorviewmethoda-arraygetacceleratorview-method"></a><a name="array__get_accelerator_view_method"></a>  array::get_accelerator_view メソッド  
 返します。、 [accelerator_view](../Topic/accelerator_view%20Class.md) 、場所を表すオブジェクトを、 [配列](../../../parallel/amp/reference/array-class.md) オブジェクトが割り当てられます。 このプロパティは CPU 上でのみアクセスできます。  
  
```  
Concurrency::accelerator_view get_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>戻り値  
  `accelerator_view` 、場所を表すオブジェクトを [配列](../../../parallel/amp/reference/array-class.md) オブジェクトが割り当てられます。  
  
##  <a name="a-namearraygetassociatedacceleratorviewmethoda-arraygetassociatedacceleratorview-method"></a><a name="array__get_associated_accelerator_view_method"></a>  array::get_associated_accelerator_view メソッド  
 2 番目の取得 [accelerator_view](../Topic/accelerator_view%20Class.md) をインスタンス化するステージング コンス トラクターが呼び出されたときに、パラメーターとして渡されるオブジェクト、 [配列](../../../parallel/amp/reference/array-class.md) オブジェクトです。  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const ;  
```  
  
### <a name="return-value"></a>戻り値  
 2 番目 [accelerator_view](../Topic/accelerator_view%20Class.md) ステージング コンス トラクターに渡されるオブジェクト。  
  
##  <a name="a-namearraygetcpuaccesstypemethoda-arraygetcpuaccesstype-method"></a><a name="array__get_cpu_access_type_method"></a>  array::get_cpu_access_type メソッド  
 この配列に対して許可される CPU access_type を返します。  
  
```  
access_type get_cpu_access_type() const restrict(cpu);
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-namearraygetextentmethoda-arraygetextent-method"></a><a name="array__get_extent_method"></a>  array::get_extent メソッド  
 返します。、 [エクステント](../Topic/extent%20Class%20\(C++%20AMP\).md) のオブジェクト、 [配列](../../../parallel/amp/reference/array-class.md)します。  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```  
  
### <a name="return-value"></a>戻り値  
  `extent` のオブジェクト、 [配列](../../../parallel/amp/reference/array-class.md)します。  
  
##  <a name="a-namearrayoperatorstdvectorltvaluetypegtoperatora-arrayoperator-stdvectorltvaluetypegt-operator"></a><a name="array__operator_std__vector_lt__value_type_gt__operator"></a>  array::operator std::vector&lt;value_type&gt; 演算子  
 使用して `copy(*this, vector)` std::vector オブジェクトに配列を暗黙的に変換します。  
  
'' 演算子 std::vector \< value_type > () const restrict (cpu) です。
```  
  
### Parameters  
 `value_type`  
 The data type of the elements of the vector.  
  
### Return Value  
 An object of type `vector<T>` that contains a copy of the data that is contained in the array.  
  
##  <a name="array__operator___operator"></a>  array::operator() Operator  
 Returns the element value that is specified by the parameters.  
  
```  
value_type & operator() (const index \< _Rank > & _Index) restrict(amp,cpu) です。

 
const value_type & operator() (const index \< _Rank > & _Index) const restrict(amp,cpu) です。

 
value_type & operator() (int _I0、int _I1) restrict(amp,cpu) です。

 
const value_type & operator() (int _I0、int _I1) const restrict(amp,cpu) です。

 
value_type & operator() (int _I0、int _I1、int _I2) restrict(amp,cpu) です。

 
const value_type & operator() (int _I0、int _I1、int _I2) const restrict(amp,cpu) です。

 
typename details::_Projection_result_type \< value_type、_Rank >:: _Result_type operator() (int _I) restrict(amp,cpu) です。

 
typename details::_Projection_result_type \< value_type、_Rank >:: _Const_result_type operator() (int _I) const restrict(amp,cpu) です。
```  
  
### Parameters  
 `_Index`  
 The location of the element.  
  
 `_I0`  
 The most significant component of the origin of this section.  
  
 `_I1`  
 The next-to-most-significant component of the origin of this section.  
  
 `_I2`  
 The least significant component of the origin of this section.  
  
 `_I`  
 The location of the element.  
  
### Return Value  
 The element value specified by the parameters.  
  
##  <a name="array__operator_at_operator"></a>  array::operator[] Operator  
 Returns the element that is at the specified index.  
  
```  
value_type & 演算子 (const index \< _Rank > & _Index) restrict(amp,cpu) です。

 
const value_type & 演算子 (const index \< _Rank > & _Index) const restrict(amp,cpu) です。

 
typename details::_Projection_result_type \< value_type、_Rank >:: _Result_type 演算子[](int _I) restrict(amp,cpu) です。

 
typename details::_Projection_result_type \< value_type、_Rank >:: _Const_result_type 演算子[](int _I) const restrict(amp,cpu) です。
```  
  
### Parameters  
 `_Index`  
 The index.  
  
 `_I`  
 The index.  
  
### Return Value  
 The element that is at the specified index.  
  
##  <a name="array__operator_eq_operator"></a>  array::operator= Operator  
 Copies the contents of the specified [array](../../../parallel/amp/reference/array-class.md) object.  
  
```  
& 演算子で配列 (const 配列 & _Other) = restrict (cpu) です。

 
& 演算子で配列 = (配列 & & _Other) restrict (cpu) です。

 
& 演算子で配列 = (const array_view \< const value_type、_Rank > & _Src) restrict (cpu) です。
```  
  
### Parameters  
 `_Other`  
 The `array` object to copy from.  
  
 `_Src`  
 The `array` object to copy from.  
  
### Return Value  
 A reference to this `array` object.  
  
##  <a name="array__rank_constant"></a>  array::rank Constant  
 Stores the rank of the [array](../../../parallel/amp/reference/array-class.md).  
  
```  
静的な const int ランク = _Rank です。  
```  
  
##  <a name="array__section_method"></a>  array::section Method  
 Returns a subsection of the [array](../../../parallel/amp/reference/array-class.md) object that is at the specified origin and, optionally, that has the specified extent.  
  
```  
array_view \< value_type、_Rank > セクション (const Concurrency::index \< _Rank > & _Section_origin、  
    const Concurrency::extent \< _Rank > & _Section_extent) restrict(amp,cpu) です。

 
array_view \< const value_type、_Rank > セクション (const Concurrency::index \< _Rank > & _Section_origin、  
    const Concurrency::extent \< _Rank > & _Section_extent) const restrict(amp,cpu) です。

 
array_view \< value_type、_Rank > セクション (const Concurrency::extent \< _Rank > & 展開) restrict(amp,cpu) です。

 
array_view \< const value_type、_Rank > セクション (const Concurrency::extent \< _Rank > & 展開) const restrict(amp,cpu) です。

 
array_view \< value_type、_Rank > セクション (const index \< _Rank > & _Idx) restrict(amp,cpu) です。

 
array_view \< const value_type、_Rank > セクション (const index \< _Rank > & _Idx) const restrict(amp,cpu) です。

 
array_view \< value_type 1 > セクション (int _I0、  
    int _E0) restrict(amp,cpu) です。

 
array_view \< const value_type、1 > セクション (int _I0、  
    restrict(amp,cpu) の const int _E0) です。

 
array_view \< value_type 2 > セクション (int _I0、  
    int _I1  
    int _E0  
    int _E1) restrict(amp,cpu) です。

 
array_view \< const value_type、2 > セクション (int _I0、  
    int _I1  
    int _E0  
    restrict(amp,cpu) の const int _E1) です。

 
array_view \< value_type 3 > セクション (int _I0、  
    int _I1  
    int _I2  
    int _E0  
    int _E1  
    int _E2) restrict(amp,cpu) です。

 
array_view \< const value_type、3 > セクション (int _I0、  
    int _I1  
    int _I2  
    int _E0  
    int _E1  
    restrict(amp,cpu) の const int _E2) です。
```  
  
### Parameters  
 `_E0`  
 The most significant component of the extent of this section.  
  
 `_E1`  
 The next-to-most-significant component of the extent of this section.  
  
 `_E2`  
 The least significant component of the extent of this section.  
  
 `_Ext`  
 The [extent](../Topic/extent%20Class%20\(C++%20AMP\).md) object that specifies the extent of the section. The origin is 0.  
  
 `_Idx`  
 The [index](../../../parallel/amp/reference/index-class.md) object that specifies the location of the origin. The subsection is the rest of the extent.  
  
 `_I0`  
 The most significant component of the origin of this section.  
  
 `_I1`  
 The next-to-most-significant component of the origin of this section.  
  
 `_I2`  
 The least significant component of the origin of this section.  
  
 `_Rank`  
 The rank of the section.  
  
 `_Section_extent`  
 The [extent](../Topic/extent%20Class%20\(C++%20AMP\).md) object that specifies the extent of the section.  
  
 `_Section_origin`  
 The [index](../../../parallel/amp/reference/index-class.md) object that specifies the location of the origin.  
  
 `value_type`  
 The data type of the elements that are copied.  
  
### Return Value  
 Returns a subsection of the `array` object that is at the specified origin and, optionally, that has the specified extent. When only the `index` object is specified, the subsection contains all elements in the associated grid that have indexes that are larger than the indexes of the elements in the `index` object.  
  
##  <a name="array__view_as_method"></a>  array::view_as Method  
 Reinterprets this array as an [array_view](../../../parallel/amp/reference/array-view-class.md) of a different rank.  
  
```  
テンプレート \< int _New_rank  
>  
array_view \< value_type、_New_rank > view_as (const Concurrency::extent \< _New_rank > & _View_extent) restrict(amp,cpu) です。

 
テンプレート \< int _New_rank  
>  
array_view \< const value_type、_New_rank > view_as (const Concurrency::extent \< _New_rank > & _View_extent) const restrict(amp,cpu) です。
```  
  
### Parameters  
 `_New_rank`  
 The rank of the `extent` object passed as a parameter.  
  
 `_View_extent`  
 The extent that is used to construct the new [array_view](../../../parallel/amp/reference/array-view-class.md) object.  
  
 `value_type`  
 The data type of the elements in both the original [array](../../../parallel/amp/reference/array-class.md) object and the returned `array_view` object.  
  
### Return Value  
 The [array_view](../../../parallel/amp/reference/array-view-class.md) object that is constructed.  
  
## See Also  
 [Concurrency Namespace (C++ AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
