---
title: "Concurrency 名前空間 (C++ AMP) | Microsoft Docs"
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
  - "amp/Concurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Concurrency 名前空間"
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
caps.latest.revision: 28
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency 名前空間 (C++ AMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

データ並列ハードウェアでの C++ コードの実行を高速化するクラスと関数を提供します。 詳細については、次を参照してください [C++ AMP の概要。](../../../parallel/amp/cpp-amp-overview.md)  
  
## <a name="syntax"></a>構文  
  
```  
namespace Concurrency;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="namespaces"></a>名前空間  
  
|名前|説明|  
|----------|-----------------|  
|[Concurrency::direct3d 名前空間](../../../parallel/amp/reference/concurrency-direct3d-namespace.md)|D3D の相互運用性をサポートする関数を提供します。 AMP コードでの計算に D3D のリソースをシームレスに使用できるようになり、AMP で作成したリソースを D3D コードで使用することができ、冗長な中間コピーを作成する必要がありません。 C++ AMP を使用して、DirectX アプリケーションの計算中心のセクションの処理をインクリメントに加速し、AMP の計算から生成されるデータに対して D3D API を使用することができます。|  
|[Concurrency::fast_math 名前空間](../../../parallel/amp/reference/concurrency-fast-math-namespace.md)|`fast_math` 名前空間の関数は C99 に準拠していません。 各関数の各単精度のバージョンのみが用意されています。 これらの関数は DirectX 組み込み関数を使用します。これは、`precise_math` 名前空間の対応する関数よりも高速で、アクセラレータでの倍精度の拡張サポートを必要としませんが、正確さに欠けます。 C99 コードとのソース レベルの互換性のための各関数には 2 つのバージョンがあります。どちらのバージョンも単精度の値を受け取り、返します。|  
|[Concurrency::graphics 名前空間](../../../parallel/amp/reference/concurrency-graphics-namespace.md)|グラフィックス プログラミング用に設計された型と関数を提供します。|  
|[Concurrency::precise_math 名前空間](../Topic/Concurrency::precise_math%20Namespace.md)|`precise_math` 名前空間の関数は C99 に準拠しています。 各関数の単精度バージョンと倍精度のバージョンの両方が含まれます。 単精度関数を含む、これらの関数ではアクセラレータでの倍精度の拡張サポートが必要です。|  
  
### <a name="classes"></a>クラス  
  
|名前|説明|  
|----------|-----------------|  
|[accelerator クラス](../../../parallel/amp/reference/accelerator-class.md)|物理的に DP に最適化されたコンピューティング ノードの抽象化を表します。|  
|[accelerator_view クラス](../Topic/accelerator_view%20Class.md)|C ++. AMP のデータ並列アクセラレータでの仮想デバイスの抽象化を表します。|  
|[accelerator_view_removed クラス](../../../parallel/amp/reference/accelerator-view-removed-class.md)|基になる DirectX の呼び出しが Windows のタイムアウト検出と回復機構が原因で失敗した場合にスローされる例外。|  
|[array クラス](../../../parallel/amp/reference/array-class.md)|グリッド ドメインの `accelerator_view` のデータ集合体。 これは、グリッド ドメインの各要素に対して 1 つずつの変数のコレクションです。 各変数はいずれかの C++ 型に対応する値を保持します。|  
|[array_view クラス](../../../parallel/amp/reference/array-view-class.md)|array\<T,N> 内のデータに対するビューを表します。|  
|[completion_future クラス](../Topic/completion_future%20Class.md)|C++ AMP 非同期操作に対応する予定を表します。|  
|[extent クラス](../Topic/extent%20Class%20\(C++%20AMP\).md)|原点が 0 である N 次元空間の境界を指定する N 個の整数値のベクターを表します。 座標ベクターの値は最上位から最下位へ順に並べ替えられます。 たとえば、デカルトの 3 次元空間では、範囲ベクター (7,5,3) は、z 座標の範囲が 0 ～ 7、y 座標の範囲が 0 ～ 5、x 座標の範囲が 0 ～ 3 である空間を表します。|  
|[index クラス](../../../parallel/amp/reference/index-class.md)|N 次元のインデックス位置を定義します。|  
|[invalid_compute_domain クラス](../../../parallel/amp/reference/invalid-compute-domain-class.md)|ランタイムが、`parallel_for_each` 呼び出しサイトで指定された計算ドメインを使用してカーネルを起動できない場合にスローされる例外。|  
|[out_of_memory クラス](../../../parallel/amp/reference/out-of-memory-class.md)|システムまたはデバイスのメモリ不足のためにメソッドが失敗した場合にスローされる例外。|  
|[runtime_exception クラス](../Topic/runtime_exception%20Class.md)|C++ AMP ライブラリの例外の基本型。|  
|[tile_barrier クラス](../Topic/tile_barrier%20Class.md)|システムによってのみ作成できる機能クラスであり、`parallel_for_each` パラメーターの一部として、タイルの `tiled_index` ラムダに渡されます。 これは 1 つのメソッド、`wait()` を提供します。その目的は、スレッド グループ (タイル) で実行されるスレッドの実行を同期することです。|  
|[tiled_extent クラス](../../../parallel/amp/reference/tiled-extent-class.md)|`tiled_extent` オブジェクトは 3 つの次元のいずれかの `extent` オブジェクトであり、範囲空間を 1、2、または 3 次元のタイルに再分割します。|  
|[tiled_index クラス](../../../parallel/amp/reference/tiled-index-class.md)|`tiled_grid` オブジェクトにインデックスを提供します。 このクラスには、ローカル タイルの原点およびグローバル原点を基準として要素にアクセスするためのプロパティがあります。|  
|[uninitialized_object クラス](../../../parallel/amp/reference/uninitialized-object-class.md)|初期化されていないオブジェクトが使用される場合にスローされる例外です。|  
|[unsupported_feature クラス](../../../parallel/amp/reference/unsupported-feature-class.md)|サポートされていない機能が使用される場合にスローされる例外です。|  
  
### <a name="enumerations"></a>列挙  
  
|名前|説明|  
|----------|-----------------|  
|[access_type 列挙型](../Topic/access_type%20Enumeration.md)|データ アクセスの種類を指定します。|  
|[queuing_mode 列挙型](../../../parallel/amp/reference/queuing-mode-enumeration.md)|アクセラレータでサポートされているキュー モードを指定します。|  
  
### <a name="operators"></a>演算子  
  
|演算子|説明|  
|--------------|-----------------|  
|[operator = 演算子 (C++ AMP)](../Topic/operator==%20Operator%20\(C++%20AMP\).md)|指定したデータ構造が等しいかどうかを判断します。|  
|[operator! = 演算子 (C++ AMP)](../Topic/operator!=%20Operator%20\(C++%20AMP\).md)|指定したデータ構造が等しくないかどうかを判断します。|  
|[operator + 演算子 (C++ AMP)](../Topic/operator+%20Operator%20\(C++%20AMP\).md)|指定された引数の要素ごとの合計を計算します。|  
|[operator-演算子 (C++ AMP)](../Topic/operator-%20Operator%20\(C++%20AMP\)1.md)|指定された引数の要素ごとの差を計算します。|  
|[operator * 演算子 (C++ AMP)](../Topic/operator*%20Operator%20\(C++%20AMP\).md)|指定された引数の要素ごとの積を計算します。|  
|[operator/演算子 (C++ AMP)](../Topic/operator-%20Operator%20\(C++%20AMP\)2.md)|指定された引数のコンポーネントごとの商を計算します。|  
|[operator % 演算子 (C++ AMP)](../Topic/operator%25%20Operator%20\(C++%20AMP\).md)|2 番目の指定された引数による 1 番目の指定された引数の剰余を計算します。|  
  
### <a name="functions"></a>関数  
  
|名前|説明|  
|----------|-----------------|  
|[all_memory_fence 関数](../Topic/all_memory_fence%20Function.md)|すべてのメモリ アクセスが完了するまでタイルのすべてのスレッドの実行をブロックします。|  
|[amp_uninitialize 関数](../Topic/amp_uninitialize%20Function.md)|C++ AMP ランタイムを初期化前の状態に戻します。|  
|[atomic_compare_exchange 関数](../Topic/atomic_compare_exchange%20Function.md)|オーバーロードされます。 指定した位置に格納されている値が 1 番目の指定された値と同じ場合、2 番目の指定された値は分割不可能な操作として同じ位置に格納されます。|  
|[atomic_exchange 関数](../Topic/atomic_exchange%20Function%20\(C++%20AMP\).md)|オーバーロードされます。 指定した位置に格納された値を分割不可能な操作として指定された値に設定します。|  
|[atomic_fetch_add 関数](../Topic/atomic_fetch_add%20Function%20\(C++%20AMP\).md)|オーバーロードされます。 指定した位置に格納された値をその値および分割不可能な操作として指定された値の合計に設定します。|  
|[atomic_fetch_and 関数](../Topic/atomic_fetch_and%20Function%20\(C++%20AMP\).md)|オーバーロードされます。 指定された位置に格納されている値をその値と分割不可能な操作として指定された値のビットごとの `and` に設定します。|  
|[atomic_fetch_dec 関数](../Topic/atomic_fetch_dec%20Function.md)|オーバーロードされます。 指定した位置に格納されている値をデクリメントし、分割不可能な操作としてしてその結果を同じ位置に格納します。|  
|[atomic_fetch_inc 関数](../Topic/atomic_fetch_inc%20Function.md)|オーバーロードされます。 指定した位置に格納されている値をインクリメントし、分割不可能な操作としてその結果を同じ位置に格納します。|  
|[atomic_fetch_max 関数](../Topic/atomic_fetch_max%20Function.md)|オーバーロードされます。 指定された位置に格納された値を、その値および分割不可能な操作として指定された値の大きい方の値に設定します。|  
|[atomic_fetch_min 関数](../Topic/atomic_fetch_min%20Function.md)|オーバーロードされます。 指定された位置に格納された値をその値および分割不可能な操作として指定された値の小さい方の値に設定します。|  
|[atomic_fetch_or 関数](../Topic/atomic_fetch_or%20Function%20\(C++%20AMP\).md)|オーバーロードされます。 指定された位置に格納されている値をその値と分割不可能な操作として指定された値のビットごとの `or` に設定します。|  
|[atomic_fetch_sub 関数](../Topic/atomic_fetch_sub%20Function%20\(C++%20AMP\).md)|オーバーロードされます。 指定された位置に格納された値を、その値と分割不可能な操作として指定された値の差に設定します。|  
|[atomic_fetch_xor 関数](../Topic/atomic_fetch_xor%20Function%20\(C++%20AMP\).md)|オーバーロードされます。 指定された位置に格納されている値をその値と分割不可能な操作として指定された値のビットごとの `xor` に設定します。|  
|[copy 関数](../Topic/copy%20Function.md)|C++ AMP オブジェクトをコピーします。 すべての同期データ転送の条件が満たされます。 アクセラレータでコードを実行しているときにデータをコピーすることはできません。 この関数の一般的な形式は `copy(src, dest)` です。|  
|[copy_async 関数](../Topic/copy_async%20Function.md)|C++ AMP オブジェクトをコピーし、返します [completion_future](../Topic/completion_future%20Class.md) 待機できます。 アクセラレータでコードを実行しているときにデータはコピーできません。 この関数の一般的な形式は `copy(src, dest)` です。|  
|[direct3d_abort 関数](../Topic/direct3d_abort%20Function.md)|制限句 `restrict(amp)` がある関数の実行を中止します。|  
|[direct3d_errorf 関数](../Topic/direct3d_errorf%20Function.md)|書式指定文字列を Visual Studio **出力** ウィンドウおよびを発生させる、 [runtime_exception](../Topic/runtime_exception%20Class.md) がある、同じ書式指定文字列します。|  
|[direct3d_printf 関数](../Topic/direct3d_printf%20Function.md)|Visual Studio に書式指定文字列出力 **出力** ウィンドウです。 これは制限句 `restrict(amp)` がある関数から呼び出されます。|  
|[global_memory_fence 関数](../Topic/global_memory_fence%20Function.md)|すべてのグローバル メモリ アクセスが完了するまでタイルのすべてのスレッドの実行をブロックします。|  
|[parallel_for_each 関数 (C++ AMP)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)|計算ドメインを越えて関数を実行します。|  
|[tile_static_memory_fence 関数](../Topic/tile_static_memory_fence%20Function.md)|`tile_static` メモリ アクセスが完了するまでタイルのすべてのスレッドの実行をブロックします。|  
  
## <a name="constants"></a>定数  
  
|名前|説明|  
|----------|-----------------|  
|[HLSL_MAX_NUM_BUFFERS 定数](../Topic/HLSL_MAX_NUM_BUFFERS%20Constant.md)|DirectX で許容される最大バッファー数。|  
|[MODULENAME_MAX_LENGTH 定数](../Topic/MODULENAME_MAX_LENGTH%20Constant.md)|モジュール名の最大長を格納します。 この値は、コンパイラとランタイムで同じにする必要があります。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** amp.h  
  
## <a name="see-also"></a>参照  
 [リファレンス (C++ AMP)](../../../parallel/amp/reference/reference-cpp-amp.md)



