---
title: "tiled_index クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::tiled_index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tiled_index クラス"
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# tiled_index クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

[tiled\_extent](../../../parallel/amp/reference/tiled-extent-class.md) オブジェクトにインデックスを提供します。  このクラスには、ローカル タイルの原点およびグローバル原点を基準として要素にアクセスするためのプロパティがあります。  タイル スペースの詳細については、「[タイルの使用](../../../parallel/amp/using-tiles.md)」を参照してください。  
  
## 構文  
  
```  
template <  
   int _Dim0,  
   int _Dim1 = 0,  
   int _Dim2 = 0  
>  
class tiled_index : public _Tiled_index_base<3>;  
  
template <  
   int _Dim0,  
   int _Dim1  
>  
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;  
  
template <  
   int _Dim0  
>  
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;  
```  
  
#### パラメーター  
 `_Dim0`  
 最上位の次元の長さ。  
  
 `_Dim1`  
 最上位の次の次元の長さ。  
  
 `_Dim2`  
 最下位の次元の長さ。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[tiled\_index::tiled\_index コンストラクター](../Topic/tiled_index::tiled_index%20Constructor.md)|`tile_index` クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[tiled\_index::get\_tile\_extent メソッド](../Topic/tiled_index::get_tile_extent%20Method.md)|[tiled\_index](../../../parallel/amp/reference/tiled-index-class.md) テンプレート引数 `_Dim0`、`_Dim1`、および `_Dim2` の値を持つ [extent](../Topic/extent%20Class%20\(C++%20AMP\).md) オブジェクトを返します。|  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[tiled\_index::barrier 定数](../Topic/tiled_index::barrier%20Constant.md)|スレッドの現在のタイルのバリアを表す [tile\_barrier](../Topic/tile_barrier%20Class.md) オブジェクトを格納します。|  
|||  
|[tiled\_index::global 定数](../Topic/tiled_index::global%20Constant.md)|[grid](http://msdn.microsoft.com/ja-jp/f7d1b6a6-586c-4345-b09a-bfc26c492cb0) オブジェクトのグローバル インデックスを表すランク 1、2、または 3 の [index](../../../parallel/amp/reference/index-class.md) オブジェクトを格納します。|  
|[tiled\_index::local 定数](../Topic/tiled_index::local%20Constant.md)|[tiled\_extent](../../../parallel/amp/reference/tiled-extent-class.md) オブジェクトの現在のタイルの相対インデックスを表すランク 1、2、または 3 の `index` オブジェクトを格納します。|  
|[tiled\_index::rank 定数](../Topic/tiled_index::rank%20Constant.md)|[tiled\_index](../../../parallel/amp/reference/tiled-index-class.md) オブジェクトのランクを格納します。|  
|[tiled\_index::tile 定数](../Topic/tiled_index::tile%20Constant.md)|`tiled_extent` オブジェクトの現在のタイルの座標を表すランク 1、2、または 3 の `index` オブジェクトを格納します。|  
|[tiled\_index::tile\_dim0 定数](../Topic/tiled_index::tile_dim0%20Constant.md)|最上位の次元の長さを格納します。|  
|[tiled\_index::tile\_dim1 定数](../Topic/tiled_index::tile_dim1%20Constant.md)|最上位の次の次元の長さを格納します。|  
|[tiled\_index::tile\_dim2 定数](../Topic/tiled_index::tile_dim2%20Constant.md)|最下位の次元の長さを格納します。|  
|[tiled\_index::tile\_origin 定数](../Topic/tiled_index::tile_origin%20Constant.md)|`tiled_extent` オブジェクトの現在のタイルの原点のグローバル座標を表すランク 1、2、または 3 の `index` オブジェクトを格納します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[tiled\_index::tile\_extent データ メンバー](../Topic/tiled_index::tile_extent%20Data%20Member.md)|[tiled\_index](../../../parallel/amp/reference/tiled-index-class.md) テンプレート引数 [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md) テンプレート引数 `_Dim0`、`_Dim1`、および `_Dim2` の値を持つ [extent](../Topic/extent%20Class%20\(C++%20AMP\).md) オブジェクトを取得します。|  
  
## 継承階層  
 `_Tiled_index_base`  
  
 `tiled_index`  
  
## 必要条件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)