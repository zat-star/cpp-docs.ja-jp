---
title: "単純な読み取り専用プロバイダーの機能の拡張 | Microsoft Docs"
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
  - "IRowsetLocate クラス"
  - "IRowsetLocate クラス, 追加 (OLE DB テンプレート プロバイダーに)"
  - "読み取り専用プロバイダー [C++]"
  - "単純な読み取り専用プロバイダー [C++]"
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 単純な読み取り専用プロバイダーの機能の拡張
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2 番目の例では、 インターフェイスを追加することにより[単純な読み取り専用プロバイダーを拡張](../../data/oledb/implementing-the-simple-read-only-provider.md)する方法を示します。  `IRowsetLocateImpl` は、`IRowsetLocate` インターフェイスの実装を作成し、ブックマーク サポートを追加します。  
  
 プロバイダーのテストが成功したら、このプロバイダーの機能を拡張して、プロバイダーの更新可能化、トランザクションの処理、行フェッチ アルゴリズムのパフォーマンスの向上などを行うことができます。  プロバイダーの機能拡張の大半は、既存の COM オブジェクトへのインターフェイスを追加することによって実現できます。  
  
 ここでは、`CAgentRowset` に `IRowsetLocate` インターフェイスを追加して、行フェッチ機構を拡張する例を示します。  以下の操作手順について説明します。  
  
-   [RMyProviderRowset の継承の変更](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md)  
  
-   [コンシューマーに返される列の動的な判断](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)  
  
## 参照  
 [単純な読み取り専用プロバイダーの作成](../../data/oledb/creating-a-simple-read-only-provider.md)