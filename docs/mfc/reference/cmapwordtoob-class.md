---
title: "CMapWordToOb クラス | Microsoft Docs"
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
  - "CMapWordToOb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "16 ビット ワードの変換"
  - "CMapWordToOb クラス"
ms.assetid: 9c9bcd76-456f-4cf9-b03c-dd28b49d5e4f
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMapWordToOb クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

16 ビット ワードをキーとした `CObject` ポインターのマップをサポートします。  
  
## 構文  
  
```  
class CMapWordToOb : public CObject  
```  
  
## メンバー  
 `CMapWordToOb` のメンバー関数は [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)クラスのメンバー関数に似ています。  メンバー関数については `CMapStringToOb` クラスの説明を参照してください。  関数のパラメーターまたは戻り値として `char` に `CString` か **const** のポインターが使われている場合は、別の **word**。  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 たとえば、への移動  
  
 `BOOL CMapWordToOb::Lookup( WORD <key>, CObject*& <rValue> ) const;`  
  
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
 `CMapWordToOb` は、要素のシリアル化とダンプをサポートするために `IMPLEMENT_SERIAL` のマクロが組み込まれています。  各要素は、マップがオーバーロードされた挿入 \(**\<\<**\) 演算子を使用して、または `Serialize` のメンバー関数のアーカイブに格納され、順番にシリアル化されます。  
  
 個々の **word**\-`CObject` の要素必要とする場合は、1 にダンプをダンプ コンテキストの深さを設定するより大きい。  
  
 `CMapWordToOb` のオブジェクトを削除または要素が削除されると、`CObject` のポインターが削除されます。  `CObject` のポインターに参照されるオブジェクトは破棄されません。  
  
 `CMapWordToOb`の詳細については、" " [&#91;コレクション&#93;](../../mfc/collections.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CMapWordToOb`  
  
## 必要条件  
 **Header:** afxcoll.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)