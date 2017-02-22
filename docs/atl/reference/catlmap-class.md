---
title: "CAtlMap クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlMap"
  - "CAtlMap"
  - "ATL::CAtlMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlMap クラス"
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAtlMap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、マップ オブジェクトを作成および管理するためのメソッドが用意されています。  
  
## 構文  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
>  
class CAtlMap  
```  
  
#### パラメーター  
 `K`  
 キー要素の型。  
  
 V  
 値要素の型。  
  
 `KTraits`  
 キー要素のコピーまたは移動するときに使用するコード。  [CElementTraits のクラス](../../atl/reference/celementtraits-class.md) を詳細については、" "を参照してください。  
  
 `VTraits`  
 要素値をコピーまたは移動するときに使用するコード。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CAtlMap::KINARGTYPE](../Topic/CAtlMap::KINARGTYPE.md)|キーが入力引数として渡されたときに使用する型|  
|[CAtlMap::KOUTARGTYPE](../Topic/CAtlMap::KOUTARGTYPE.md)|キーが出力の引数として戻るときに使用される型。|  
|[CAtlMap::VINARGTYPE](../Topic/CAtlMap::VINARGTYPE.md)|入力引数として値が渡されたときに使用する型。|  
|[CAtlMap::VOUTARGTYPE](../Topic/CAtlMap::VOUTARGTYPE.md)|出力の引数として値が渡されたときに使用する型。|  
  
### パブリック クラス  
  
|名前|説明|  
|--------|--------|  
|[CAtlMap::CPair クラス](../Topic/CAtlMap::CPair%20Class.md)|キーと値要素を含むクラス。|  
  
### CPair のデータ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPair::m\_key](../Topic/CAtlMap::CPair::m_key.md)|キー要素を格納するデータ メンバー。|  
|[CPair::m\_value](../Topic/CAtlMap::CPair::m_value.md)|要素値を格納するデータ メンバー。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAtlMap::CAtlMap](../Topic/CAtlMap::CAtlMap.md)|コンストラクターです。|  
|[CAtlMap::~CAtlMap](../Topic/CAtlMap::~CAtlMap.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlMap::AssertValid](../Topic/CAtlMap::AssertValid.md)|が無効 `CAtlMap` ASSERT を発生させるにこのメソッドを呼び出します。|  
|[CAtlMap::DisableAutoRehash](../Topic/CAtlMap::DisableAutoRehash.md)|`CAtlMap` のオブジェクトの自動に再作成することを無効にするには、このメソッドを呼び出します。|  
|[CAtlMap::EnableAutoRehash](../Topic/CAtlMap::EnableAutoRehash.md)|`CAtlMap` のオブジェクトの自動に再作成できるようにするには、このメソッドを呼び出します。|  
|[CAtlMap::GetAt](../Topic/CAtlMap::GetAt.md)|マップ内の指定した位置にある要素を返すには、このメソッドを呼び出します。|  
|[CAtlMap::GetCount](../Topic/CAtlMap::GetCount.md)|マップ要素の数を取得するときにこのメソッドを呼び出します。|  
|[CAtlMap::GetHashTableSize](../Topic/CAtlMap::GetHashTableSize.md)|マップのハッシュ テーブルの Bin の数を判断するためにこのメソッドを呼び出します。|  
|[CAtlMap::GetKeyAt](../Topic/CAtlMap::GetKeyAt.md)|`CAtlMap` のオブジェクトの特定の位置に格納されているキーを取得するときにこのメソッドを呼び出します。|  
|[CAtlMap::GetNext](../Topic/CAtlMap::GetNext.md)|`CAtlMap` のオブジェクトに格納されている次の要素のペアにポインターを取得するときにこのメソッドを呼び出します。|  
|[CAtlMap::GetNextAssoc](../Topic/CAtlMap::GetNextAssoc.md)|次の要素を順番に取得します。|  
|[CAtlMap::GetNextKey](../Topic/CAtlMap::GetNextKey.md)|`CAtlMap` のオブジェクトから次のキーを取得するときにこのメソッドを呼び出します。|  
|[CAtlMap::GetNextValue](../Topic/CAtlMap::GetNextValue.md)|`CAtlMap` のオブジェクトから次の値を取得するときにこのメソッドを呼び出します。|  
|[CAtlMap::GetStartPosition](../Topic/CAtlMap::GetStartPosition.md)|マップのイテレーションを開始するには、このメソッドを呼び出します。|  
|[CAtlMap::GetValueAt](../Topic/CAtlMap::GetValueAt.md)|`CAtlMap` のオブジェクトの特定の位置に格納されている値を取得するときにこのメソッドを呼び出します。|  
|[CAtlMap::InitHashTable](../Topic/CAtlMap::InitHashTable.md)|ハッシュ テーブルを初期化するには、このメソッドを呼び出します。|  
|[CAtlMap::IsEmpty](../Topic/CAtlMap::IsEmpty.md)|空のマップ オブジェクトをテストするには、このメソッドを呼び出します。|  
|[CAtlMap::Lookup](../Topic/CAtlMap::Lookup.md)|`CAtlMap` のオブジェクトのキーまたは値を検索するためにこのメソッドを呼び出します。|  
|[CAtlMap::Rehash](../Topic/CAtlMap::Rehash.md)|再作成にこのメソッドを `CAtlMap` のオブジェクトで呼び出します。|  
|[CAtlMap::RemoveAll](../Topic/CAtlMap::RemoveAll.md)|`CAtlMap` のオブジェクトからすべての要素を削除するには、このメソッドを呼び出します。|  
|[CAtlMap::RemoveAtPos](../Topic/CAtlMap::RemoveAtPos.md)|`CAtlMap` のオブジェクトの指定した位置の要素を削除するには、このメソッドを呼び出します。|  
|[CAtlMap::RemoveKey](../Topic/CAtlMap::RemoveKey.md)|キーが存在 `CAtlMap` のオブジェクトから要素を削除するには、このメソッドを呼び出します。|  
|[CAtlMap::SetAt](../Topic/CAtlMap::SetAt.md)|マップのペアに要素を挿入する場合に、このメソッドを呼び出します。|  
|[CAtlMap::SetOptimalLoad](../Topic/CAtlMap::SetOptimalLoad.md)|`CAtlMap` のオブジェクトの最適な負荷を設定するには、このメソッドを呼び出します。|  
|[CAtlMap::SetValueAt](../Topic/CAtlMap::SetValueAt.md)|`CAtlMap` のオブジェクトの特定の位置に格納されている値を変更するには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAtlMap::operator](../Topic/CAtlMap::operator.md)|置換は `CAtlMap`またはに新しい要素を追加します。|  
  
## 解説  
 `CAtlMap` はキー要素および関連する値の順序なしの配列を管理する特定の型のマッピングの配列をサポートします。  要素は、ハッシュ アルゴリズムを使用して \(キーと値で構成されます\) に格納され、効率的に格納および取得されるように、大量のデータができます。  
  
 `KTraits` と `VTraits` のパラメーターは、要素をコピーするか、または実行に必要な補足コードを含む特性のクラスです。  
  
 `CAtlMap` 代わりに、[CRBMap](../../atl/reference/crbmap-class.md) のクラスによって提供されます。  また`CRBMap` のメモリ入力キーと値は、という一つのさまざまなパフォーマンス特性組み合わせたものです。  項目を挿入するか、キーを検索するか、`CRBMap` のオブジェクトからキーを削除するためにかかる時間は *n は* 要素の数を注文の *ログ \(n\)* です。  `CAtlMap`では、これらすべての操作は、通常、最悪のシナリオが注文 *n.*であるかも知れませんが、定数時間がかかります。  したがって、一般的に、`CAtlMap` は高速です。  
  
 `CRBMap` と `CAtlMap` の他の相違点は、格納されている要素を反復処理すると、明らかになります。  `CRBMap`では、要素は、並べ替えられた順序でアクセスされます。  `CAtlMap`では、要素は指定されていないため、順序は推論できません。  
  
 一部の要素を格納する必要がある場合 [CSimpleMap](../../atl/reference/csimplemap-class.md) の代わりにクラスを使用することを検討してください。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [Marquee サンプル](../../top/visual-cpp-samples.md)   
 [UpdatePV サンプル](../../top/visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)