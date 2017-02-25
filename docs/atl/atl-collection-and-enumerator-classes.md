---
title: "ATL コレクションと列挙子のクラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コレクション クラス, ATL"
  - "列挙子, ATL クラス"
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL コレクションと列挙子のクラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL は、と列挙子がコレクションを実行するのに役立つ次のクラスを提供します。  
  
|Class|説明|  
|-----------|--------|  
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|コレクション インターフェイスの実装|  
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|列挙子インターフェイスの実装 \(STL 互換性のあるコンテナーに格納されているデータを仮定します\)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|列挙子インターフェイスの実装 \(配列に格納されているデータを仮定します\)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|列挙子オブジェクトの実装 \(`IEnumOnSTLImpl`使用\)|  
|[CComEnum](../atl/reference/ccomenum-class.md)|列挙子オブジェクトの実装 \(`CComEnumImpl`使用\)|  
|[コピー\(\_C\)](../Topic/ATL%20Copy%20Policy%20Classes.md)|コピー ポリシー クラス|  
|[\_CopyInterface](../Topic/ATL%20Copy%20Policy%20Classes.md)|コピー ポリシー クラス|  
|[CAdapt](../atl/reference/cadapt-class.md)|アダプター クラス \(非表示 **operator &**`CComPtr`、STL コンテナーに格納する `CComQIPtr`と `CComBSTR` を許可します\)|  
  
## 参照  
 [コレクションと列挙子](../atl/atl-collections-and-enumerators.md)