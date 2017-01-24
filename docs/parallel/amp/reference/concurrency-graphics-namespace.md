---
title: "Concurrency::graphics 名前空間 | Microsoft Docs"
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
  - "amp_graphics/Concurrency::graphics"
  - "amp_short_vectors/Concurrency::graphics"
dev_langs: 
  - "C++"
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency::graphics 名前空間
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

graphics 名前空間は、グラフィックス プログラミング用に設計された型と関数を提供します。  
  
## 構文  
  
```  
namespace graphics;  
```  
  
## メンバー  
  
### 名前空間  
  
|名前|説明|  
|--------|--------|  
|[Concurrency::graphics::direct3d 名前空間](../../../parallel/amp/reference/concurrency-graphics-direct3d-namespace.md)|Direct3D の相互運用のための関数を提供します。|  
  
### Typedef  
  
|名前|説明|  
|--------|--------|  
|`uint`|[uint\_2 クラス](../../../parallel/amp/reference/uint-2-class.md), [uint\_3 クラス](../../../parallel/amp/reference/uint-3-class.md)および [uint\_4 クラス](../../../parallel/amp/reference/uint-4-class.md)の要素型。  `typedef unsigned int uint;` として定義されます。|  
  
### 列挙型  
  
|名前|説明|  
|--------|--------|  
|[address\_mode 列挙型](../Topic/address_mode%20Enumeration.md)|テクスチャ サンプリングでサポートされているアドレス モードを指定します。|  
|[filter\_mode 列挙型](../Topic/filter_mode%20Enumeration.md)|テクスチャ サンプリングでサポートされているフィルター モードを指定します。|  
  
### クラス  
  
|名前|説明|  
|--------|--------|  
|[texture クラス](../Topic/texture%20Class.md)|テクスチャは範囲ドメイン内の accelerator\_view についてのデータ集合体です。  これは、範囲ドメインの各要素に対して 1 つずつの変数のコレクションです。  各変数は、対応する C\+\+ のプリミティブ型 \(unsigned int、int、float、double\)、またはスカラー型の norm、または unorm \(concurrency::graphics で定義\)、または concurrency::graphics で定義されている有効な short ベクター型の値を保持します。|  
|[writeonly\_texture\_view クラス](../Topic/writeonly_texture_view%20Class.md)|writeonly\_texture\_view はテクスチャへの writeonly アクセスを提供します。|  
|[double\_2 クラス](../Topic/double_2%20Class.md)|2 個の `double` 値の short ベクターを表します。|  
|[double\_3 クラス](../../../parallel/amp/reference/double-3-class.md)|3 個の `double` 値の short ベクターを表します。|  
|[double\_4 クラス](../Topic/double_4%20Class.md)|4 個の `double` 値の short ベクターを表します。|  
|[float\_2 クラス](../../../parallel/amp/reference/float-2-class.md)|2 個の `float` 値の short ベクターを表します。|  
|[float\_3 クラス](../../../parallel/amp/reference/float-3-class.md)|3 個の `float` 値の short ベクターを表します。|  
|[float\_4 クラス](../../../parallel/amp/reference/float-4-class.md)|4 個の `float` 値の short ベクターを表します。|  
|[int\_2 クラス](../Topic/int_2%20Class.md)|2 個の `int` 値の short ベクターを表します。|  
|[int\_3 クラス](../../../parallel/amp/reference/int-3-class.md)|3 個の `int` 値の short ベクターを表します。|  
|[int\_4 クラス](../../../parallel/amp/reference/int-4-class.md)|4 個の `int` 値の short ベクターを表します。|  
|[norm\_2 クラス](../../../parallel/amp/reference/norm-2-class.md)|2 個の `norm` 値の short ベクターを表します。|  
|[norm\_3 クラス](../../../parallel/amp/reference/norm-3-class.md)|3 個の `norm` 値の short ベクターを表します。|  
|[norm\_4 クラス](../../../parallel/amp/reference/norm-4-class.md)|4 個の `norm` 値の short ベクターを表します。|  
|[uint\_2 クラス](../../../parallel/amp/reference/uint-2-class.md)|2 個の `uint` 値の short ベクターを表します。|  
|[uint\_3 クラス](../../../parallel/amp/reference/uint-3-class.md)|3 個の `uint` 値の short ベクターを表します。|  
|[uint\_4 クラス](../../../parallel/amp/reference/uint-4-class.md)|4 個の `uint` 値の short ベクターを表します。|  
|[unorm\_2 クラス](../../../parallel/amp/reference/unorm-2-class.md)|2 個の `unorm` 値の short ベクターを表します。|  
|[unorm\_3 クラス](../../../parallel/amp/reference/unorm-3-class.md)|3 個の `unorm` 値の short ベクターを表します。|  
|[unorm\_4 クラス](../../../parallel/amp/reference/unorm-4-class.md)|4 個の `unorm` 値の short ベクターを表します。|  
|[sampler クラス](../../../parallel/amp/reference/sampler-class.md)|テクスチャ サンプリングに使用するサンプラー構成を表します。|  
|[short\_vector 構造体](../../../parallel/amp/reference/short-vector-structure.md)|値の short ベクターの基本実装を提供します。|  
|[short\_vector\_traits 構造体](../../../parallel/amp/reference/short-vector-traits-structure.md)|short ベクターの長さと型の取得を提供します。|  
|[texture\_view クラス](../../../parallel/amp/reference/texture-view-class.md)|テクスチャへの読み取りアクセスおよび書き込みアクセスを提供します。|  
  
### 関数  
  
|名前|説明|  
|--------|--------|  
|[copy 関数](../Topic/copy%20Function.md)|オーバーロードされます。  ソース テクスチャの内容をターゲット ホスト バッファーにコピーします。|  
|[copy\_async 関数](../Topic/copy_async%20Function.md)|オーバーロードされます。  ソース テクスチャの内容をターゲット ホスト バッファーに非同期にコピーします。|  
  
## 必要条件  
 **ヘッダー:** amp\_graphics.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)