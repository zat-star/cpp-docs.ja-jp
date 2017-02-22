---
title: "CSimpleMap クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSimpleMap"
  - "ATL.CSimpleMap"
  - "CSimpleMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMap クラス"
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CSimpleMap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、単純なマップ配列をサポートします。  
  
## 構文  
  
```  
  
      template <   
   class TKey,  
   class TVal,  
   class TEqual = CSimpleMapEqualHelper< TKey, TVal >   
>   
class CSimpleMap  
```  
  
#### パラメーター  
 `TKey`  
 キー要素の型。  
  
 `TVal`  
 値要素の型。  
  
 `TEqual`  
 型 `T`の要素の等価テストを定義する特性でオブジェクト。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CSimpleMap::\_ArrayElementType](../Topic/CSimpleMap::_ArrayElementType.md)|値型の typedef。|  
|[CSimpleMap::\_ArrayKeyType](../Topic/CSimpleMap::_ArrayKeyType.md)|重要な型の typedef。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSimpleMap::CSimpleMap](../Topic/CSimpleMap::CSimpleMap.md)|コンストラクターです。|  
|[CSimpleMap::~CSimpleMap](../Topic/CSimpleMap::~CSimpleMap.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSimpleMap::Add](../Topic/CSimpleMap::Add.md)|マップの配列には、キーと関連する値を追加します。|  
|[CSimpleMap::FindKey](../Topic/CSimpleMap::FindKey.md)|特定のキーを検索します。|  
|[CSimpleMap::FindVal](../Topic/CSimpleMap::FindVal.md)|特定の値を検索します。|  
|[CSimpleMap::GetKeyAt](../Topic/CSimpleMap::GetKeyAt.md)|指定されたキーを取得します。|  
|[CSimpleMap::GetSize](../Topic/CSimpleMap::GetSize.md)|マップ配列のエントリの数を返します。|  
|[CSimpleMap::GetValueAt](../Topic/CSimpleMap::GetValueAt.md)|ある値を取得します。|  
|[CSimpleMap::Lookup](../Topic/CSimpleMap::Lookup.md)|指定したキーに関連付けられた値を返します。|  
|[CSimpleMap::Remove](../Topic/CSimpleMap::Remove.md)|キーと一致する値を削除します。|  
|[CSimpleMap::RemoveAll](../Topic/CSimpleMap::RemoveAll.md)|すべてのキーと値を削除します。|  
|[CSimpleMap::RemoveAt](../Topic/CSimpleMap::RemoveAt.md)|特定のキーと一致する値を削除します。|  
|[CSimpleMap::ReverseLookup](../Topic/CSimpleMap::ReverseLookup.md)|指定された値に関連付けられているキーを返します。|  
|[CSimpleMap::SetAt](../Topic/CSimpleMap::SetAt.md)|値を指定したキーに関連付けられる。|  
|[CSimpleMap::SetAtIndex](../Topic/CSimpleMap::SetAtIndex.md)|特定のキーと値を設定します。|  
  
## 解説  
 `CSimpleMap` はキー要素および関連する値の順序なしの配列を管理する特定の型 `T`の単純なマッピングの配列をサポートします。  
  
 パラメーター `TEqual` は、型の 2 `T`等値の二つの要素に関数を定義する手段を提供します。  [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)に似たクラスを作成して指定された配列の等価テストの動作を変更することができます。  たとえば、ポインターの配列を扱う場合、値を通じて、等値を定義すると便利なポインターが参照します。  既定の実装では **operator\=\=\(\)**を使用します。  
  
 `CSimpleMap` と [CSimpleArray](../../atl/reference/csimplearray-class.md) は、前の ATL のリリースの互換性のために用意されており、より完全に、より効率的なコレクションの実装は [CAtlArray](../../atl/reference/catlarray-class.md) と [CAtlMap](../../atl/reference/catlmap-class.md)によって提供されます。  
  
 ATL と MFC のマップ他のコレクションとは異なり、このクラスには、単純な配列で実行され、検索の検索は、リニア サーチが必要です。  `CAtlMap` は、配列が複数の要素が含まれている場合に使用されます。  
  
## 必要条件  
 **ヘッダー:** atlsimpcoll.h  
  
## 使用例  
 [!CODE [NVC_ATL_Utilities#91](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#91)]  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)