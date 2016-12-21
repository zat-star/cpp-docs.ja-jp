---
title: "CMapStringToString クラス | Microsoft Docs"
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
  - "CMapStringToString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapStringToString クラス"
  - "コレクション クラス, 文字列マップ"
  - "文字列 [C++], クラス (マップの)"
  - "文字列 [C++], マップ"
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMapStringToString クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CString` オブジェクトをキーとした `CString` オブジェクトのマップをサポートします。  
  
## 構文  
  
```  
class CMapStringToString : public CObject  
```  
  
## メンバー  
 `CMapStringToString` のメンバー関数は [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)クラスのメンバー関数に似ています。  メンバー関数については `CMapStringToOb` クラスの説明を参照してください。  戻り値または出力「」の関数のパラメーターとして `CObject` のポインターが使われている場合は、`char`へのポインターに置き換えてください。  「関数」の入力パラメーターとして `CObject` のポインターが使われている場合は、`char`へのポインターに置き換えてください。  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 たとえば、への移動  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### パブリック構造体  
  
|名前|説明|  
|--------|--------|  
|[CMapStringToString::CPair](../Topic/CMapStringToString::CPair.md)|キー値を含む入れ子構造、関連付けられた文字列の値を追加します。|  
  
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
|[CMapStringToString::PGetFirstAssoc](../Topic/CMapStringToString::PGetFirstAssoc.md)|マップの最初の `CString` へのポインターを取得します。|  
|[CMapStringToString::PGetNextAssoc](../Topic/CMapStringToString::PGetNextAssoc.md)|反復の次の `CString` へのポインターを取得します。|  
|[CMapStringToString::PLookup](../Topic/CMapStringToString::PLookup.md)|値が指定した値と一致する `CString` へのポインターを返します。|  
|[CMapStringToOb::RemoveAll](../Topic/CMapStringToOb::RemoveAll.md)|このマップからすべての要素を削除します。|  
|[CMapStringToOb::RemoveKey](../Topic/CMapStringToOb::RemoveKey.md)|キーによって指定された要素を削除します。|  
|[CMapStringToOb::SetAt](../Topic/CMapStringToOb::SetAt.md)|マップに要素を挿入します; 一致するキーがある場合は、既存の要素を置き換えます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CMapStringToOb::operator](../Topic/CMapStringToOb::operator.md)|—マップに要素 `SetAt`の演算子の置換を挿入します。|  
  
## 解説  
 `CMapStringToString` は、要素のシリアル化とダンプをサポートするために `IMPLEMENT_SERIAL` のマクロが組み込まれています。  各要素は、マップがオーバーロードされた挿入 \(**\<\<**\) 演算子を使用して、または `Serialize` のメンバー関数のアーカイブに格納され、順番にシリアル化されます。  
  
 個々の `CString`\-`CString` の要素必要な場合の 1 にダンプをダンプ コンテキストの深さを設定するより大きい。  
  
 `CMapStringToString` のオブジェクトを削除または要素が削除されると、`CString` のオブジェクトは必要に応じて削除されます。  
  
 `CMapStringToString`の詳細については、" " [&#91;コレクション&#93;](../../mfc/collections.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CMapStringToString`  
  
## 必要条件  
 **Header:** afxcoll.h  
  
## 参照  
 [MFC のサンプルが収集されます](../../top/visual-cpp-samples.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)