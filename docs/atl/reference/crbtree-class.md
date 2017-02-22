---
title: "CRBTree クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CRBTree"
  - "CRBTree"
  - "ATL::CRBTree"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBTree クラス"
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CRBTree クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、レッドブラック ツリーを作成および利用するためのメソッドが用意されています。  
  
## 構文  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
> class CRBTree  
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
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CRBTree::KINARGTYPE](../Topic/CRBTree::KINARGTYPE.md)|キーが入力引数として渡されたときに使用する型。|  
|[CRBTree::KOUTARGTYPE](../Topic/CRBTree::KOUTARGTYPE.md)|キーが出力の引数として戻るときに使用される型。|  
|[CRBTree::VINARGTYPE](../Topic/CRBTree::VINARGTYPE.md)|入力引数として値が渡されたときに使用する型。|  
|[CRBTree::VOUTARGTYPE](../Topic/CRBTree::VOUTARGTYPE.md)|出力の引数として値が渡されたときに使用する型。|  
  
### パブリック クラス  
  
|名前|説明|  
|--------|--------|  
|[CRBTree::CPair クラス](../Topic/CRBTree::CPair%20Class.md)|キーと値要素を含むクラス。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CRBTree::~CRBTree](../Topic/CRBTree::~CRBTree.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRBTree::FindFirstKeyAfter](../Topic/CRBTree::FindFirstKeyAfter.md)|次のキーを使用して要素の位置を検索するには、このメソッドを呼び出します。|  
|[CRBTree::GetAt](../Topic/CRBTree::GetAt.md)|ツリーの特定の位置にある要素を取得するときにこのメソッドを呼び出します。|  
|[CRBTree::GetCount](../Topic/CRBTree::GetCount.md)|ツリー内の要素数を取得するときにこのメソッドを呼び出します。|  
|[CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md)|ツリーの先頭の要素の位置の値を取得するときにこのメソッドを呼び出します。|  
|[CRBTree::GetKeyAt](../Topic/CRBTree::GetKeyAt.md)|ツリーの特定の位置からキーを取得するときにこのメソッドを呼び出します。|  
|[CRBTree::GetNext](../Topic/CRBTree::GetNext.md)|`CRBTree` のオブジェクトに格納されている要素へのポインターを取得するには、このメソッドを呼び出して次の要素の位置を進めます。|  
|[CRBTree::GetNextAssoc](../Topic/CRBTree::GetNextAssoc.md)|マップに格納されている要素のキーと値を取得し、次の要素の位置を移動するために、このメソッドを呼び出します。|  
|[CRBTree::GetNextKey](../Topic/CRBTree::GetNextKey.md)|ツリーに格納されている要素のキーを取得し、次の要素の位置を移動するために、このメソッドを呼び出します。|  
|[CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md)|ツリーに格納されている要素の値を取得して、次の要素の位置を移動するために、このメソッドを呼び出します。|  
|[CRBTree::GetPrev](../Topic/CRBTree::GetPrev.md)|`CRBTree` のオブジェクトに格納されている要素へのポインターを取得するときにこのメソッドを呼び出します。次に直前の要素と位置を更新します。|  
|[CRBTree::GetTailPosition](../Topic/CRBTree::GetTailPosition.md)|ツリーの末尾で要素の位置の値を取得するときにこのメソッドを呼び出します。|  
|[CRBTree::GetValueAt](../Topic/CRBTree::GetValueAt.md)|`CRBTree` のオブジェクトの特定の位置に格納されている値を取得するときにこのメソッドを呼び出します。|  
|[CRBTree::IsEmpty](../Topic/CRBTree::IsEmpty.md)|空のツリーのオブジェクトをテストするには、このメソッドを呼び出します。|  
|[CRBTree::RemoveAll](../Topic/CRBTree::RemoveAll.md)|**CRBTree** のオブジェクトからすべての要素を削除するには、このメソッドを呼び出します。|  
|[CRBTree::RemoveAt](../Topic/CRBTree::RemoveAt.md)|**CRBTree** のオブジェクトの指定した位置の要素を削除するには、このメソッドを呼び出します。|  
|[CRBTree::SetValueAt](../Topic/CRBTree::SetValueAt.md)|`CRBTree` のオブジェクトの特定の位置に格納されている値を変更するには、このメソッドを呼び出します。|  
  
## 解説  
 は、レッドブラック ツリー、つまり」ツリーの高さを「分散されるされないようにするには、ノードごとについての追加のビットを育たないし、極端に大きな影響を与えずパフォーマンスに使用する 2 バイナリ サーチ ツリーです。  
  
 このテンプレート クラスは [CRBMap](../../atl/reference/crbmap-class.md) と [CRBMultiMap](../../atl/reference/crbmultimap-class.md)で使用できるように設計されています。  構成するメソッドの大半を `CRBTree`これらの派生クラスによって提供されます。  
  
 さまざまなコレクション クラスおよび機能およびパフォーマンス特性の詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)