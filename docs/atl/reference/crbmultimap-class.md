---
title: "CRBMultiMap クラス | Microsoft Docs"
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
  - "CRBMultiMap"
  - "ATL.CRBMultiMap"
  - "ATL::CRBMultiMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBMultiMap クラス"
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRBMultiMap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、レッドブラック バイナリ ツリーを使用して複数の値と各キーを関連付けることができる割り当てるマップ構造体を表します。  
  
## 構文  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
> class CRBMultiMap : public CRBTree< K, V, KTraits, VTraits >  
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
|[CRBMultiMap::CRBMultiMap](../Topic/CRBMultiMap::CRBMultiMap.md)|コンストラクターです。|  
|[CRBMultiMap::~CRBMultiMap](../Topic/CRBMultiMap::~CRBMultiMap.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRBMultiMap::FindFirstWithKey](../Topic/CRBMultiMap::FindFirstWithKey.md)|指定したキーを持つ最初の要素の位置を検索するには、このメソッドを呼び出します。|  
|[CRBMultiMap::GetNextValueWithKey](../Topic/CRBMultiMap::GetNextValueWithKey.md)|値を指定したキーに関連付けられているを取得するには、このメソッドを呼び出して位置の値を更新します。|  
|[CRBMultiMap::GetNextWithKey](../Topic/CRBMultiMap::GetNextWithKey.md)|要素を指定したキーに関連付けられているを取得するには、このメソッドを呼び出して位置の値を更新します。|  
|[CRBMultiMap::Insert](../Topic/CRBMultiMap::Insert.md)|マップのペアに要素を挿入する場合に、このメソッドを呼び出します。|  
|[CRBMultiMap::RemoveKey](../Topic/CRBMultiMap::RemoveKey.md)|指定したキーのキー\/値要素をすべて削除するには、このメソッドを呼び出します。|  
  
## 解説  
 `CRBMultiMap` 要素はキーと値の順序の配列を管理する特定の型のマッピングの配列をサポートします。  [CRBMap](../../atl/reference/crbmap-class.md) のクラスとは異なり、各キーには複数の値に関連付けることができます。  
  
 要素は [CRBMultiMap::Insert](../Topic/CRBMultiMap::Insert.md) のメソッドを使用してバイナリ ツリーの構造 \(キーと値で構成されます\) が格納されます。  要素は、指定したキーに一致するすべての要素を削除する [CRBMultiMap::RemoveKey](../Topic/CRBMultiMap::RemoveKey.md) のメソッドを使用して削除できます。  
  
 ツリーを走査することは [CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md)、[CRBTree::GetNext](../Topic/CRBTree::GetNext.md)と [CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md)のようなメソッドで有効になっています。  キーごとによって、複数の値にアクセス [CRBMultiMap::FindFirstWithKey](../Topic/CRBMultiMap::FindFirstWithKey.md)、[CRBMultiMap::GetNextValueWithKey](../Topic/CRBMultiMap::GetNextValueWithKey.md)と [CRBMultiMap::GetNextWithKey](../Topic/CRBMultiMap::GetNextWithKey.md) のメソッドを使用してできます。  次の図の [CRBMultiMap::CRBMultiMap](../Topic/CRBMultiMap::CRBMultiMap.md) の例を実際に参照します。  
  
 `KTraits` と `VTraits` のパラメーターは、要素をコピーするか、または実行に必要な補足コードを含む特性のクラスです。  
  
 `CRBMultiMap` はから派生します [CRBTree](../../atl/reference/crbtree-class.md)、アルゴリズムを使用して、レッドブラック バイナリ ツリーを実行する。  `CRBMultiMap` と `CRBMap` 代わりに、[CAtlMap](../../atl/reference/catlmap-class.md) のクラスによって提供されます。  一部の要素のみを格納する必要がある場合 [CSimpleMap](../../atl/reference/csimplemap-class.md) の代わりにクラスを使用することを検討してください。  
  
 さまざまなコレクション クラスおよび機能およびパフォーマンス特性の詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 継承階層  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CRBTree クラス](../../atl/reference/crbtree-class.md)   
 [CAtlMap クラス](../../atl/reference/catlmap-class.md)   
 [CRBMap クラス](../../atl/reference/crbmap-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)