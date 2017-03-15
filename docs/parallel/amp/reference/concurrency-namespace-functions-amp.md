---
title: "Concurrency 名前空間の関数 (AMP) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bef0985-cb90-4ece-90b9-66529aec73c9
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: a976cc06b49b10d5bb8dcecb10e114efdd89faa8
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-functions-amp"></a>Concurrency 名前空間の関数 (AMP)
||||  
|-|-|-|  
|[all_memory_fence](#all_memory_fence)|[amp_uninitialize](#amp_uninitialize)|[atomic_compare_exchange](#atomic_compare_exchange)|  
|[atomic_exchange 関数 (C++ AMP)](#atomic_exchange)|[atomic_fetch_add 関数 (C++ AMP)](#atomic_fetch_add)|[atomic_fetch_and 関数 (C++ AMP)](#atomic_fetch_and)|  
|[atomic_fetch_dec](#atomic_fetch_dec)|[atomic_fetch_inc](#atomic_fetch_inc)|[atomic_fetch_max](#atomic_fetch_max)|  
|[atomic_fetch_min](#atomic_fetch_min)|[atomic_fetch_or 関数 (C++ AMP)](#atomic_fetch_or)|[atomic_fetch_sub 関数 (C++ AMP)](#atomic_fetch_sub)|  
|[atomic_fetch_xor 関数 (C++ AMP)](#atomic_fetch_xor)|[copy](#copy)|[copy_async](#copy_async)|  
|[direct3d_abort](#direct3d_abort)|[direct3d_errorf](#direct3d_errorf)|[direct3d_printf](#direct3d_printf)|  
|[global_memory_fence](#global_memory_fence)|[parallel_for_each 関数 (C++ AMP)](#parallel_for_each)|[tile_static_memory_fence](#tile_static_memory_fence)|  
  
##  <a name="a-nameallmemoryfencea--allmemoryfence"></a><a name="all_memory_fence"></a>all_memory_fence  
 すべてのメモリ アクセスが完了するまでタイルのすべてのスレッドの実行をブロックします。 これによって、すべてのメモリ アクセスがスレッド タイルの他のスレッドから参照でき、プログラムの順序で実行されます。  
  
```  
inline void all_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Barrier`  
 `tile_barrier` オブジェクト。  
  
##  <a name="a-nameampuninitializea--ampuninitialize"></a><a name="amp_uninitialize"></a>amp_uninitialize  
 C++ AMP ランタイムを初期化前の状態に戻します。 アプリケーションの有効期間中にこの関数を複数回呼び出すことは有効です。 この関数を呼び出した後でいずれかの C++ AMP API を呼び出すと、C++ AMP のランタイムが再初期化されます。 この関数の複数の呼び出しにまたがって C++ AMP オブジェクトを使用することは無効であり、それにより未定義の動作が発生することに注意してください。 また、この関数と他の AMP API を同時に呼び出すことは無効であり、未定義の動作が発生します。  
  
```  
void __cdecl amp_uninitialize();
```  
  
##  <a name="a-nameatomiccompareexchangea--atomiccompareexchange"></a><a name="atomic_compare_exchange"></a>atomic_compare_exchange  
 1 番目の引数で指定されたメモリ位置に格納されている値を&2; 番目に指定された引数の値と等しいかどうかアトミックに比較し、値が同じ場合、メモリ位置の値は&3; 番目に指定された引数の値に変更されます。  
  
```  
inline bool atomic_compare_exchange(
    _Inout_ int* _Dest,  
    _Inout_ int* _Expected_value,  
    int value  
    ) restrict(amp)

 
inline bool atomic_compare_exchange(
    _Inout_ unsigned int* _Dest,  
    _Inout_ unsigned int* _Expected_value,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 比較される値の&1; つが読み取られ、新しい値 (ある場合) が格納される位置。  
  
 `_Expected_value`  
 比較される&2; 番目の値が読み取られる位置。  
  
 `value`  
 `_Dest` が `_Dest` と等しい場合、`_Expected_value` によって指定したメモリ位置に格納される値。  
  
### <a name="return-value"></a>戻り値  
 操作が正常に終了した場合は `true`。それ以外の場合は `false`。  
  

##  <a name="a-nameatomicexchangea--atomicexchange-function-c-amp"></a><a name="atomic_exchange"></a>atomic_exchange 関数 (C++ AMP)  
 分割不可能な操作としては、先の場所の値を設定します。  
  
```  
inline int atomic_exchange(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_exchange(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)

 
inline float atomic_exchange(
    _Inout_ float* _Dest,  
    float value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 配置される移動先の場所へのポインター。  
  
 `value`  
 新しい値。  
  
### <a name="return-value"></a>戻り値  
 移行先の場所の元の値。  
  

##  <a name="a-nameatomicfetchadda--atomicfetchadd-function-c-amp"></a><a name="atomic_fetch_add"></a>atomic_fetch_add 関数 (C++ AMP)  
 メモリ位置の値に値をアトミックに追加します。  
  
```  
inline int atomic_fetch_add(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_add(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 メモリ位置へのポインター。  
  
 `value`  
 追加する値。  
  
### <a name="return-value"></a>戻り値  
 メモリ位置の元の値。  
  
##  <a name="a-nameatomicfetchanda--atomicfetchand-function-c-amp"></a><a name="atomic_fetch_and"></a>atomic_fetch_and 関数 (C++ AMP)  
 アトミックに、値とメモリ位置の値のビットごとの AND 演算を実行します。  
  
```  
inline int atomic_fetch_and(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_and(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 メモリ位置へのポインター。  
  
 `value`  
 ビットごとの AND の計算に使用する値。  
  
### <a name="return-value"></a>戻り値  
 メモリ位置の元の値。  
  
##  <a name="a-nameatomicfetchdeca--atomicfetchdec"></a><a name="atomic_fetch_dec"></a>atomic_fetch_dec  
 指定したメモリ位置に格納されている値をアトミックにデクリメントします。  
  
```  
inline int atomic_fetch_dec(_Inout_ int* _Dest  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_dec(_Inout_ unsigned int* _Dest) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 デクリメントされる値のメモリ内での位置。  
  
### <a name="return-value"></a>戻り値  
 メモリ位置に格納されている元の値。  
  
##  <a name="a-nameatomicfetchinca--atomicfetchinc"></a><a name="atomic_fetch_inc"></a>atomic_fetch_inc  
 指定されたメモリ位置に格納されている値をアトミックにインクリメントします。  
  
```  
inline int atomic_fetch_inc(_Inout_ int* _Dest) restrict(amp);

 
inline unsigned int atomic_fetch_inc(_Inout_ unsigned int* _Dest) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 インクリメントされる値のメモリでの位置。  
  
### <a name="return-value"></a>戻り値  
 メモリ位置に格納されている元の値。  
  
##  <a name="a-nameatomicfetchmaxa--atomicfetchmax"></a><a name="atomic_fetch_max"></a>atomic_fetch_max  
 最初の引数で指定されたメモリ位置に格納されている値と&2; 番目の引数で指定された値の間での最大値をアトミックに計算し、同じメモリ位置に格納します。  
  
```  
inline int atomic_fetch_max(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_max(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 比較される値の&1; つが読み取られ、2 つの値の最大値が格納される位置。  
  
 `value`  
 指定した位置の値と比較する値。  
  
### <a name="return-value"></a>戻り値  
 指定した位置に格納される元の値。  
  
##  <a name="a-nameatomicfetchmina--atomicfetchmin"></a><a name="atomic_fetch_min"></a>atomic_fetch_min  
 最初の引数で指定されたメモリ位置に格納されている値と&2; 番目の引数で指定された値の間での最小値をアトミックに計算し、同じメモリ位置に格納します。  
  
```  
inline int atomic_fetch_min(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_min(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 比較される値の&1; つが読み取られ、2 つの値の最小値が格納される位置。  
  
 `value`  
 指定した位置の値と比較する値。  
  
### <a name="return-value"></a>戻り値  
 指定した位置に格納される元の値。  
  
##  <a name="a-nameatomicfetchora--atomicfetchor-function-c-amp"></a><a name="atomic_fetch_or"></a>atomic_fetch_or 関数 (C++ AMP)  
 アトミックの値とメモリ位置の値のビットごとの OR 演算を実行します。  
  
```  
inline int atomic_fetch_or(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_or(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 メモリ位置へのポインター。  
  
 `value`  
 ビットごとの OR の計算に使用する値。  
  
### <a name="return-value"></a>戻り値  
 メモリ位置の元の値。  
  
##  <a name="a-nameatomicfetchsuba--atomicfetchsub-function-c-amp"></a><a name="atomic_fetch_sub"></a>atomic_fetch_sub 関数 (C++ AMP)  
 メモリ位置からの値をアトミックに減算します。  
  
```  
inline int atomic_fetch_sub(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_sub(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 配置される移動先の場所へのポインター。  
  
 `value`  
 減算される値です。  
  
### <a name="return-value"></a>戻り値  
 メモリ位置の元の値。  
  
##  <a name="a-nameatomicfetchxora--atomicfetchxor-function-c-amp"></a><a name="atomic_fetch_xor"></a>atomic_fetch_xor 関数 (C++ AMP)  
 アトミックに実行値とメモリ位置のビットごとの XOR 演算します。  
  
```  
inline int atomic_fetch_xor(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_xor(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 メモリ位置へのポインター。  
  
 `value`  
 XOR の計算に使用する値。  
  
### <a name="return-value"></a>戻り値  
 メモリ位置の元の値。  
  
##  <a name="a-namecopya--copy"></a><a name="copy"></a>  copy  
 C++ AMP オブジェクトをコピーします。 すべての同期データ転送の条件が満たされます。 アクセラレータでコードを実行しているときにデータをコピーすることはできません。 この関数の一般的な形式は `copy(src, dest)` です。  
  
```  
template <typename value_type, int _Rank>  
void copy(
    const array<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst,
    InputIterator _SrcLast,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst,  
    array<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
void copy(
    const array<value_type, _Rank>& _Src,
     OutputIterator _DestIter);

 
template <typename value_type, int _Rank>  
void copy(
    const array<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<const value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<const value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst, 
    InputIterator _SrcLast,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
void copy(
    const array_view<value_type, _Rank>& _Src,
    OutputIterator _DestIter);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 コピー先のオブジェクト。  
  
 `_DestIter`  
 コピー先での開始位置の出力反復子。  
  
 `InputIterator`  
 入力列挙子の型。  
  
 `OutputIterator`  
 出力反復子の型。  
  
 `_Rank`  
 コピー元のオブジェクトまたはコピー先のオブジェクトのランク。  
  
 `_Src`  
 コピーするオブジェクト。  
  
 `_SrcFirst`  
 ソース コンテナーへの先頭の反復子。  
  
 `_SrcLast`  
 ソース コンテナーへの終了の反復子。  
  
 `value_type`  
 コピーされた要素のデータ型。  
  
##  <a name="a-namecopyasynca--copyasync"></a><a name="copy_async"></a>copy_async  
 C++ AMP オブジェクトをコピーし、取得、 [completion_future](completion-future-class.md)待機できるオブジェクト。 アクセラレータでコードを実行しているときにデータをコピーすることはできません。  この関数の一般的な形式は `copy(src, dest)` です。  
  
```  
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst, InputIterator _SrcLast,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst,  
    array<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src, OutputIterator _DestIter);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<const value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<const value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst, InputIterator _SrcLast,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src, OutputIterator _DestIter);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 コピー先のオブジェクト。  
  
 `_DestIter`  
 コピー先での開始位置の出力反復子。  
  
 `InputIterator`  
 入力列挙子の型。  
  
 `OutputIterator`  
 出力反復子の型。  
  
 `_Rank`  
 コピー元のオブジェクトまたはコピー先のオブジェクトのランク。  
  
 `_Src`  
 コピーするオブジェクト。  
  
 `_SrcFirst`  
 ソース コンテナーへの先頭の反復子。  
  
 `_SrcLast`  
 ソース コンテナーへの終了の反復子。  
  
 `value_type`  
 コピーされた要素のデータ型。  
  
### <a name="return-value"></a>戻り値  
 待機できる `future<void>`。  
  
##  <a name="a-namedirect3daborta--direct3dabort"></a><a name="direct3d_abort"></a>direct3d_abort  
 制限句 `restrict(amp)` を使用して関数の実行を中止します。 発生させますが、AMP のランタイムが呼び出しを検出、 [runtime_exception](runtime-exception-class.md)例外エラー メッセージが"リファレンス ラスタライザー: シェーダー中止命令ヒット"です。  
  
```  
void direct3d_abort() restrict(amp);
```  
  
##  <a name="a-namedirect3derrorfa--direct3derrorf"></a><a name="direct3d_errorf"></a>direct3d_errorf  
 Visual Studio の出力ウィンドウに書式指定文字列を出力します。 これは制限句 `restrict(amp)` を使用して関数から呼び出されます。 発生させますが、AMP のランタイムが呼び出しを検出、 [runtime_exception](runtime-exception-class.md)例外と同じ書式指定文字列。  
  
```  
void direct3d_errorf(
    const char *,  
 ...) restrict(amp);
```  
  
##  <a name="a-namedirect3dprintfa--direct3dprintf"></a><a name="direct3d_printf"></a>direct3d_printf  
 Visual Studio の出力ウィンドウに書式指定文字列を出力します。 これは制限句 `restrict(amp)` を使用して関数から呼び出されます。  
  
```  
void direct3d_printf(
    const char *,  
 ...) restrict(amp);
```  
  
##  <a name="a-nameglobalmemoryfencea--globalmemoryfence"></a><a name="global_memory_fence"></a>global_memory_fence  
 すべてのグローバル メモリ アクセスが完了するまでタイルのすべてのスレッドの実行をブロックします。 これによって、グローバル メモリのアクセスがスレッド タイルの他のスレッドから参照でき、プログラムの順序で実行されます。  
  
```  
inline void global_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Barrier`  
 tile_barrier オブジェクト  
  
##  <a name="a-nameparallelforeacha--parallelforeach-function-c-amp"></a><a name="parallel_for_each"></a>parallel_for_each 関数 (C++ AMP)  
 計算ドメインを越えて関数を実行します。 詳細については、次を参照してください。 [C++ AMP の概要](../../../parallel/amp/cpp-amp-overview.md)します。  
  
```  
template <int _Rank, typename _Kernel_type>  
void parallel_for_each(
    const extent<_Rank>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, int _Dim2, typename _Kernel_type>  
void parallel_for_each(
    const tiled_extent<_Dim0, _Dim1, _Dim2>& _Compute_domain,
     const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, typename _Kernel_type>  
void parallel_for_each(
    const tiled_extent<_Dim0, _Dim1>& _Compute_domain,
    const _Kernel_type& _Kernel);

 
template <int _Dim0, typename _Kernel_type>  
void parallel_for_each(
    const tiled_extent<_Dim0>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Rank, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const extent<_Rank>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, int _Dim2, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const tiled_extent<_Dim0, _Dim1, _Dim2>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const tiled_extent<_Dim0, _Dim1>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const tiled_extent<_Dim0>& _Compute_domain,  
    const _Kernel_type& _Kernel);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Accl_view`  
 並列計算を実行する `accelerator_view` オブジェクト。  
  
 `_Compute_domain`  
 計算用のデータを含む `extent` オブジェクト。  
  
 `_Dim0`  
 `tiled_extent` オブジェクトの次元。  
  
 `_Dim1`  
 `tiled_extent` オブジェクトの次元。  
  
 `_Dim2`  
 `tiled_extent` オブジェクトの次元。  
  
 `_Kernel`  
 型の引数を受け取るラムダまたは関数オブジェクト"インデックス\<_Rank >"並列計算を実行します。  
  
 `_Kernel_type`  
 ラムダまたはファンクタ。  
  
 `_Rank`  
 範囲のランク。  
  
##  <a name="a-nametilestaticmemoryfencea--tilestaticmemoryfence"></a><a name="tile_static_memory_fence"></a>tile_static_memory_fence  
 すべての未処理の `tile_static` メモリ アクセスが完了するまで、タイルのすべてのスレッドの実行をブロックします。 これによって、`tile_static` メモリ アクセスがスレッド タイルのその他のスレッドに表示され、アクセスをプログラムの順序で実行することができます。  
  
```  
inline void tile_static_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Barrier`  
 tile_barrier オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

