---
title: "CSimpleArray クラス | Microsoft Docs"
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
  - "ATL.CSimpleArray"
  - "ATL::CSimpleArray"
  - "CSimpleArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArray クラス"
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、単純な配列を管理するためのメソッドが用意されています。  
  
## 構文  
  
```  
  
      template <  
   class T,  
   class TEqual = CSimpleArrayEqualHelper< T >  
>   
class CSimpleArray  
```  
  
#### パラメーター  
 `T`  
 配列に格納されるデータの型。  
  
 `TEqual`  
 型 `T`の要素の等価テストを定義する特性でオブジェクト。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSimpleArray::CSimpleArray](../Topic/CSimpleArray::CSimpleArray.md)|単純な配列のコンストラクター。|  
|[CSimpleArray::~CSimpleArray](../Topic/CSimpleArray::~CSimpleArray.md)|単純な配列のデストラクター。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSimpleArray::Add](../Topic/CSimpleArray::Add.md)|配列に新しい要素を追加します。|  
|[CSimpleArray::Find](../Topic/CSimpleArray::Find.md)|配列の要素を検索します。|  
|[CSimpleArray::GetData](../Topic/CSimpleArray::GetData.md)|配列に格納されたデータへのポインターを返します。|  
|[CSimpleArray::GetSize](../Topic/CSimpleArray::GetSize.md)|配列に格納されている要素数を返します。|  
|[CSimpleArray::Remove](../Topic/CSimpleArray::Remove.md)|配列の特定の要素を削除します。|  
|[CSimpleArray::RemoveAll](../Topic/CSimpleArray::RemoveAll.md)|配列のすべての要素を削除します。|  
|[CSimpleArray::RemoveAt](../Topic/CSimpleArray::RemoveAt.md)|指定された配列から要素を削除します。|  
|[CSimpleArray::SetAtIndex](../Topic/CSimpleArray::SetAtIndex.md)|配列の指定要素を設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CSimpleArray::operator](../Topic/CSimpleArray::operator.md)|配列から要素を取得します。|  
|[CSimpleArray::operator \=](../Topic/CSimpleArray::operator%20=.md)|代入演算子。|  
  
## 解説  
 `CSimpleArray` は、特定の型 `T`の単純な配列を作成および管理するためのメソッドを提供します。  
  
 パラメーター `TEqual` は、型の 2 `T`等値の二つの要素に関数を定義する手段を提供します。  [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)に似たクラスを作成して指定された配列の等価テストの動作を変更することができます。  たとえば、ポインターの配列を扱う場合、値を通じて、等値を定義すると便利なポインターが参照します。  既定の実装では **operator\=\(\)**を使用します。  
  
 `CSimpleArray` と [CSimpleMap](../../atl/reference/csimplemap-class.md) は、一部の要素用に設計されています。  配列に複数の要素を含む場合[CAtlArray](../../atl/reference/catlarray-class.md) と [CAtlMap](../../atl/reference/catlmap-class.md) を使用する必要があります。  
  
## 必要条件  
 **ヘッダー:** atlsimpcoll.h  
  
## 使用例  
 [!CODE [NVC_ATL_Utilities#86](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#86)]  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)