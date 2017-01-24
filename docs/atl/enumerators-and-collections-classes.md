---
title: "列挙子とコレクション クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "列挙子, ATL クラス"
ms.assetid: fcd093b2-98bf-444d-94ab-9a55520a5051
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 列挙子とコレクション クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のクラスは、COM のコレクションと列挙型をサポートします:  
  
-   [CComEnum](../atl/reference/ccomenum-class.md) は、配列に基づいた COM 列挙子オブジェクトを定義します。  
  
-   [CComEnumImpl](../atl/reference/ccomenumimpl-class.md) が列挙される項目が配列に格納されている COM 列挙子インターフェイスの実装を提供します。  
  
-   [CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md) は、STL コレクションに基づいた COM 列挙子オブジェクトを定義します。  
  
-   [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md) が列挙される項目が STL 互換性のあるコンテナーに格納されている COM 列挙子インターフェイスの実装を提供します。  
  
-   [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md) は **Count**、**\[アイテム\]**を実装し、コレクション `_NewEnum` のプロパティは、インターフェイスです。  
  
## 関連トピック  
 [ATL のコレクションと列挙子](../atl/atl-collections-and-enumerators.md)  
  
## 参照  
 [クラスの概要](../atl/atl-class-overview.md)