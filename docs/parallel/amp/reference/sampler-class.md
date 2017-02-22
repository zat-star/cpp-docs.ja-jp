---
title: "sampler クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# sampler クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

サンプラーのクラスは、テクスチャ サンプリングに使用するサンプリング構成情報を集計します。  
  
## 構文  
  
```  
class sampler;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[sampler::sampler コンストラクター](../Topic/sampler::sampler%20Constructor.md)|オーバーロードされます。  サンプラーのインスタンスを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[sampler::get\_address\_mode メソッド](../Topic/sampler::get_address_mode%20Method.md)|サンプラー オブジェクトに関連付けられている `address_mode` を返します。|  
|[sampler::get\_border\_color メソッド](../Topic/sampler::get_border_color%20Method.md)|サンプラー オブジェクトに関連付けられている境界線の色を返します。|  
|[sampler::get\_filter\_mode メソッド](../Topic/sampler::get_filter_mode%20Method.md)|サンプラー オブジェクトに関連付けられている `filter_mode` を返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[sampler::operator\= 演算子](../Topic/sampler::operator=%20Operator.md)|オーバーロードされます。  代入演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[sampler::address\_mode データ メンバー](../Topic/sampler::address_mode%20Data%20Member.md)|`sampler` オブジェクトのアドレス モードを取得します。|  
|[sampler::border\_color データ メンバー](../Topic/sampler::border_color%20Data%20Member.md)|`sampler` オブジェクトの境界線の色を取得します。|  
|[sampler::filter\_mode データ メンバー](../Topic/sampler::filter_mode%20Data%20Member.md)|`sampler` オブジェクトのフィルター モードを取得します。|  
  
## 継承階層  
 `sampler`  
  
## 必要条件  
 **ヘッダー:** amp\_graphics.h  
  
 **名前空間:** concurrency::graphics  
  
## 参照  
 [Concurrency::graphics 名前空間](../../../parallel/amp/reference/concurrency-graphics-namespace.md)