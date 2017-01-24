---
title: "複数のデュアル インターフェイス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM_INTERFACE_ENTRY_IID マクロ"
  - "COM_INTERFACE_ENTRY2 マクロ"
  - "デュアル インターフェイス, 公開する (複数を)"
  - "IDispatchImpl クラス, 複数のデュアル インターフェイス"
  - "複数のデュアル インターフェイス"
  - "複数のデュアル インターフェイス, 公開 (ATL で)"
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 複数のデュアル インターフェイス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

多重継承のデュアル インターフェイス \(つまり、vtable と遅延バインディングの柔軟性、スクリプト言語、または C\+\+ では、クラスを使用できるようになります\) の利点を結合する場合。  
  
 単一の COM オブジェクトの複数のデュアル インターフェイスを公開することもできますが、それは推奨されません。  複数のデュアル インターフェイスがある場合は、公開された `IDispatch` の 1 種類のインターフェイスだけ必要があります。  使用可能な方法は、このケースに該当するために関数または拡張されたコードの複雑度の損失などの低下を行います。  この方法を検討する開発者は、利点と欠点速度が重視する必要があります。  
  
## 単一の IDispatch インターフェイスの公開  
 `IDispatchImpl`の複数の特化型から派生して単一のオブジェクトの複数のデュアル インターフェイスを公開することができます。  ただし、クライアントが `IDispatch` のインターフェイスに対して問い合わせることが許可されます [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) の `IDispatch`かの実装として使用される基本クラスを指定するマクロ [COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md) \(または\) を使用する必要があります。  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/CPP/multiple-dual-interfaces_1.h)]  
  
 `IDispatch` の 1 種類のインターフェイスだけ公開されるため、`IDispatch` のインターフェイスを通じてのみ、オブジェクトにアクセスできないクライアントは、そのほかのインターフェイス メソッドやプロパティにアクセスします。  
  
## IDispatch の単一の実装への複数のデュアル インターフェイスの結合  
 ATL は `IDispatch`の単一の実装に複数のデュアル インターフェイスを結合するにはサポートされません。  ただし、手動で `QueryInterface` の機能を実行するには、新しいオブジェクトを作成するか、または `IDispatch` のインターフェイスを作成するには、入れ子になったオブジェクトの typeinfo ベースの実装を使用する `IDispatch` の別のインターフェイスの共用体を含むテンプレート クラスの作成など、インターフェイスを組み合わせることにはいくつかの既知の方法があります。  
  
 これらの方法には、名前空間の衝突の問題を持ち、複雑さや保守性です。  複数のデュアル インターフェイスを作成することは推奨されません。  
  
## 参照  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)