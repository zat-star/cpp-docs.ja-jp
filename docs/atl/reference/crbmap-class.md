---
title: "CRBMap クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CRBMap"
  - "CRBMap"
  - "ATL::CRBMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBMap クラス"
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRBMap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、レッドブラック バイナリ ツリーを使用して、マップ構造体を表します。  
  
## 構文  
  
```  
  
      template<   
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >   
> class CRBMap : public CRBTree< K, V, KTraits, VTraits >  
```  
  
#### パラメーター  
 `K`  
 キー要素の型。  
  
 *V*  
 値要素の型。  
  
 `KTraits`  
 キー要素のコピーまたは移動するときに使用するコード。  [CElementTraits のクラス](../../atl/reference/celementtraits-class.md) を詳細については、" "を参照してください。  
  
 `VTraits`  
 要素値をコピーまたは移動するときに使用するコード。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CRBMap::CRBMap](../Topic/CRBMap::CRBMap.md)|コンストラクターです。|  
|[CRBMap::~CRBMap](../Topic/CRBMap::~CRBMap.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRBMap::Lookup](../Topic/CRBMap::Lookup.md)|`CRBMap` のオブジェクトのキーまたは値を検索するためにこのメソッドを呼び出します。|  
|[CRBMap::RemoveKey](../Topic/CRBMap::RemoveKey.md)|キーが存在 `CRBMap` のオブジェクトから要素を削除するには、このメソッドを呼び出します。|  
|[CRBMap::SetAt](../Topic/CRBMap::SetAt.md)|マップのペアに要素を挿入する場合に、このメソッドを呼び出します。|  
  
## 解説  
 `CRBMap` はキー要素および関連する値の順序の配列を管理する特定の型のマッピングの配列をサポートします。  各キーには 1 種類の関連する値だけを指定できます。  要素は [CRBMap::SetAt](../Topic/CRBMap::SetAt.md) のメソッドを使用してバイナリ ツリーの構造 \(キーと値で構成されます\) が格納されます。  要素は、特定のキー値を持つ要素を削除する [CRBMap::RemoveKey](../Topic/CRBMap::RemoveKey.md) のメソッドを使用して削除できます。  
  
 ツリーを走査することは [CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md)、[CRBTree::GetNext](../Topic/CRBTree::GetNext.md)と [CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md)のようなメソッドで有効になっています。  
  
 `KTraits` と `VTraits` のパラメーターは、要素をコピーするか、または実行に必要な補足コードを含む特性のクラスです。  
  
 `CRBMap` はから派生します [CRBTree](../../atl/reference/crbtree-class.md)、アルゴリズムを使用して、レッドブラック バイナリ ツリーを実行する。  [CRBMultiMap](../../atl/reference/crbmultimap-class.md) は、各キーの複数の値を可能にするさまざまです。  これは `CRBTree`から派生しすぎると、`CRBMap`は多くの機能を共有します。  
  
 両方の `CRBMap` と `CRBMultiMap` 代わりに、[CAtlMap](../../atl/reference/catlmap-class.md) のクラスによって提供されます。  一部の要素のみを格納する必要がある場合 [CSimpleMap](../../atl/reference/csimplemap-class.md) の代わりにクラスを使用することを検討してください。  
  
 さまざまなコレクション クラスおよび機能およびパフォーマンス特性の詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 継承階層  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CRBTree クラス](../../atl/reference/crbtree-class.md)   
 [CAtlMap クラス](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap クラス](../../atl/reference/crbmultimap-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)