---
title: "CMapStringToOb クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapStringToOb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapStringToOb クラス"
  - "コレクション クラス, 文字列マップ"
  - "文字列 [C++], クラス (マップの)"
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMapStringToOb クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一意の `CString` オブジェクトを `CObject` へのポインターに割り当てる辞書コレクション クラスです。  
  
## 構文  
  
```  
class CMapStringToOb : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMapStringToOb::CMapStringToOb](../Topic/CMapStringToOb::CMapStringToOb.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMapStringToOb::GetCount](../Topic/CMapStringToOb::GetCount.md)|このマップ内の要素数を返します。|  
|[CMapStringToOb::GetHashTableSize](../Topic/CMapStringToOb::GetHashTableSize.md)|ハッシュ テーブルの要素の数を決定します。|  
|[CMapStringToOb::GetNextAssoc](../Topic/CMapStringToOb::GetNextAssoc.md)|次の要素を順番に取得します。|  
|[CMapStringToOb::GetSize](../Topic/CMapStringToOb::GetSize.md)|このマップ内の要素数を返します。|  
|[CMapStringToOb::GetStartPosition](../Topic/CMapStringToOb::GetStartPosition.md)|最初の要素の位置を返します。|  
|[CMapStringToOb::HashKey](../Topic/CMapStringToOb::HashKey.md)|指定されたキーのハッシュ値を計算します。|  
|[CMapStringToOb::InitHashTable](../Topic/CMapStringToOb::InitHashTable.md)|ハッシュ テーブルを初期化します。|  
|[CMapStringToOb::IsEmpty](../Topic/CMapStringToOb::IsEmpty.md)|マップ空の状態 \(要素\) なしのテスト。|  
|[CMapStringToOb::Lookup](../Topic/CMapStringToOb::Lookup.md)|void ポインターをキーに基づいて void ポインターを検索します。  ポインター値の比較に主に使用するポイントするエンティティではなく。|  
|[CMapStringToOb::LookupKey](../Topic/CMapStringToOb::LookupKey.md)|指定したキー値に関連付けられているキーへの参照を返します。|  
|[CMapStringToOb::RemoveAll](../Topic/CMapStringToOb::RemoveAll.md)|このマップからすべての要素を削除します。|  
|[CMapStringToOb::RemoveKey](../Topic/CMapStringToOb::RemoveKey.md)|キーによって指定された要素を削除します。|  
|[CMapStringToOb::SetAt](../Topic/CMapStringToOb::SetAt.md)|マップに要素を挿入します; 一致するキーがある場合は、既存の要素を置き換えます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CMapStringToOb::operator](../Topic/CMapStringToOb::operator.md)|—マップに要素 `SetAt`の演算子の置換を挿入します。|  
  
## 解説  
 マップに挿入、`CString`\-`CObject*` のペア \(要素\) を文字列を使用して効率的にキー ペアまたはとして `CString` の値を取得したり、削除したりできます。  また、マップのすべての要素を反復処理できます。  
  
 **POSITION** 型の変数はすべてのマップの変化は別のエントリのアクセスに使用されます。  「 **POSITION** を記憶します」エントリを使用し、マップを反復処理できます。  このイテレーションのキー値に基づいて順番であると考えることもあります。; ではありません。  取得する要素のシーケンスは不確定です。  
  
 `CMapStringToOb` は、要素のシリアル化とダンプをサポートするために `IMPLEMENT_SERIAL` のマクロが組み込まれています。  各要素は、マップがオーバーロードされた挿入 \(**\<\<**\) 演算子を使用して、または `Serialize` のメンバー関数のアーカイブに格納され、順番にシリアル化されます。  
  
 マップ \( `CString` の値と `CObject` の内容\) の各要素の診断ダンプを必要とする場合は、1 にダンプ コンテキストの深さを設定するより大きい。  
  
 `CMapStringToOb` のオブジェクトを削除または要素が削除されると、`CString` のオブジェクトと `CObject` のポインターが削除されます。  `CObject` のポインターに参照されるオブジェクトは破棄されません。  
  
 マップのクラスの派生は、リストの派生に似ています。  特殊な目的のクラスの派生リストの図に [&#91;コレクション&#93;](../../mfc/collections.md) ついては、" "を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CMapStringToOb`  
  
## 必要条件  
 **Header:** afxcoll.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr クラス](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord クラス](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr クラス](../Topic/CMapStringToPtr%20Class.md)   
 [CMapStringToString クラス](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb クラス](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr クラス](../../mfc/reference/cmapwordtoptr-class.md)