---
title: "CMap クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMap クラス"
  - "コレクション クラス, ディクショナリ マップ"
  - "ディクショナリ マップ クラス"
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一意なキーを値に割り当てる辞書コレクション クラスです。  
  
## 構文  
  
```  
template< class KEY, class ARG_KEY, class VALUE, class ARG_VALUE >class CMap : public CObject  
```  
  
#### パラメーター  
 `KEY`  
 キーとして使用するマップにオブジェクトのクラス。  
  
 `ARG` *\_* `KEY`  
 `KEY` の引数に使用するデータ型; 通常 `KEY`への参照。  
  
 `VALUE`  
 マップに格納されているオブジェクトのクラス。  
  
 `ARG` *\_* `VALUE`  
 `VALUE` の引数に使用するデータ型; 通常 `VALUE`への参照。  
  
## メンバー  
  
### パブリック構造体  
  
|名前|説明|  
|--------|--------|  
|[CMap::CPair](../Topic/CMap::CPair.md)|関連するオブジェクトのキー値と値を含む入れ子構造体。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMap::CMap](../Topic/CMap::CMap.md)|キーに値を割り当てるコレクションを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMap::GetCount](../Topic/CMap::GetCount.md)|このマップ内の要素数を返します。|  
|[CMap::GetHashTableSize](../Topic/CMap::GetHashTableSize.md)|ハッシュ テーブルの要素数を返します。|  
|[CMap::GetNextAssoc](../Topic/CMap::GetNextAssoc.md)|次の要素を順番に取得します。|  
|[CMap::GetSize](../Topic/CMap::GetSize.md)|このマップ内の要素数を返します。|  
|[CMap::GetStartPosition](../Topic/CMap::GetStartPosition.md)|最初の要素の位置を返します。|  
|[CMap::InitHashTable](../Topic/CMap::InitHashTable.md)|ハッシュ テーブルを初期化し、サイズを指定します。|  
|[CMap::IsEmpty](../Topic/CMap::IsEmpty.md)|マップ空の状態 \(要素\) なしのテスト。|  
|[CMap::Lookup](../Topic/CMap::Lookup.md)|指定したキーに割り当てられている値を検索します。|  
|[CMap::PGetFirstAssoc](../Topic/CMap::PGetFirstAssoc.md)|最初の要素へのポインターを返します。|  
|[CMap::PGetNextAssoc](../Topic/CMap::PGetNextAssoc.md)|反復の次の要素へのポインターを取得します。|  
|[CMap::PLookup](../Topic/CMap::PLookup.md)|値が指定された値に一致するキーへのポインターを返します。|  
|[CMap::RemoveAll](../Topic/CMap::RemoveAll.md)|このマップからすべての要素を削除します。|  
|[CMap::RemoveKey](../Topic/CMap::RemoveKey.md)|キーによって指定された要素を削除します。|  
|[CMap::SetAt](../Topic/CMap::SetAt.md)|マップに要素を挿入します; 一致するキーがある場合は、既存の要素を置き換えます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CMap::operator](../Topic/CMap::operator.md)|—マップに要素 `SetAt`の演算子の置換を挿入します。|  
  
## 解説  
 マップにキーと値のペア \(要素\) を挿入し、キーを使用して効率的にアクセスするためのペアを取得したり、削除したりできます。  また、マップのすべての要素を反復処理できます。  
  
 型の変数は **POSITION** エントリへの代替アクセスに使用されます。  「 **POSITION** を記憶します」エントリを使用し、マップを反復処理できます。  このイテレーションのキー値に基づいて順番であると考えることもあります。; ではありません。  取得する要素のシーケンスは不確定です。  
  
 このクラスの一部のメンバー関数は、グローバルなヘルパー関数を呼び出します。したがって、`CMap` クラスの主な用途に合わせて、これらのヘルパー関数をカスタマイズする必要があります。  `MFC``Reference`のマクロとグローバル"の [コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md) を参照してください。  
  
 `CMap` は、要素のシリアル化とダンプをサポートするために [CObject::Serialize](../Topic/CObject::Serialize.md) をオーバーライドします。  マップが `Serialize`を使用してアーカイブに格納され、各マップ要素が順番にシリアル化されます。  `SerializeElements` のヘルパー関数の既定の実装では、の書き込みをビットごとにします。  `CObject` などのユーザー定義型から派生したポインターのコレクション項目のシリアル化の詳細については、[方法 : タイプ セーフなコレクションを作成する](../../mfc/how-to-make-a-type-safe-collection.md)を参照してください。  
  
 マップ内の各要素の診断ダンプ \(キーと値\) 必要とする場合は、1 にダンプ コンテキストの深さを設定するより大きい。  
  
 `CMap` のオブジェクトを削除または要素が削除されると、キーと値の両方が削除されます。  
  
 マップのクラスの派生は、リストの派生に似ています。  特殊な目的のクラスの派生リストの図に [&#91;コレクション&#93;](../../mfc/collections.md) ついては、" "を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CMap`  
  
## 必要条件  
 **Header:** afxtempl.h  
  
## 参照  
 [MFC のサンプルが収集されます](../../top/visual-cpp-samples.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)