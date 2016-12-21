---
title: "tiled_extent クラス | Microsoft Docs"
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
  - "amp/Concurrency::tiled_extent"
dev_langs: 
  - "C++"
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
caps.latest.revision: 9
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# tiled_extent クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`tiled_extent` オブジェクトは 3 つの次元のいずれかの `extent` オブジェクトであり、範囲空間を 1、2、または 3 次元のタイルに再分割します。  
  
## 構文  
  
```  
template <  
   int _Dim0,  
   int _Dim1,  
   int _Dim2  
>  
class tiled_extent : public Concurrency::extent<3>;  
  
template <  
   int _Dim0,  
   int _Dim1  
>  
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;  
  
template <  
   int _Dim0  
>  
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;  
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
|[tiled\_extent::tiled\_extent コンストラクター](../Topic/tiled_extent::tiled_extent%20Constructor.md)|`tiled_extent` クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[tiled\_extent::get\_tile\_extent メソッド](../Topic/tiled_extent::get_tile_extent%20Method.md)|`tiled_extent` テンプレート引数 `_Dim0`、`_Dim1`、および `_Dim2` の値をキャプチャする `extent` オブジェクトを返します。|  
|[tiled\_extent::pad メソッド](../Topic/tiled_extent::pad%20Method.md)|タイルの次元によって均等に分割できる範囲を上方調整した新しい `tiled_extent` オブジェクトを返します。|  
|[tiled\_extent::truncate メソッド](../Topic/tiled_extent::truncate%20Method.md)|タイルの次元によって均等に分割できるように範囲を下方調整した新しい `tiled_extent` オブジェクトを返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[tiled\_extent::operator\= 演算子](../Topic/tiled_extent::operator=%20Operator.md)|指定された `tiled_index` オブジェクトの内容をこのオブジェクトにコピーします。|  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[tiled\_extent::tile\_dim0 定数](../Topic/tiled_extent::tile_dim0%20Constant.md)|最上位の次元の長さを格納します。|  
|[tiled\_extent::tile\_dim1 定数](../Topic/tiled_extent::tile_dim1%20Constant.md)|最上位の次の次元の長さを格納します。|  
|[tiled\_extent::tile\_dim2 定数](../Topic/tiled_extent::tile_dim2%20Constant.md)|最下位の次元の長さを格納します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[tiled\_extent::tile\_extent データ メンバー](../Topic/tiled_extent::tile_extent%20Data%20Member.md)|`tiled_extent` テンプレート引数 `_Dim0`、`_Dim1`、および `_Dim2` の値をキャプチャする `extent` オブジェクトを取得します。|  
  
## 継承階層  
 `extent`  
  
 `tiled_extent`  
  
## 必要条件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)