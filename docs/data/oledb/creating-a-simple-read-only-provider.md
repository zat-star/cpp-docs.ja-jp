---
title: "単純な読み取り専用プロバイダーの作成 | Microsoft Docs"
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
  - "OLE DB プロバイダー テンプレート, 作成 (プロバイダーを)"
  - "OLE DB プロバイダー, 作成"
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 単純な読み取り専用プロバイダーの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL プロジェクト ウィザードと ATL OLE DB プロバイダー ウィザードを使用して OLE DB プロバイダーを作成すると、サポートする他の機能を追加できます。  プロバイダーのデザインは、コンシューマーに対してどのような種類のデータをどのような条件のもとで送信するかを検討することから始めます。  コマンド オブジェクト、トランザクション オブジェクト、およびその他の省略可能なオブジェクトをサポートする必要があるかどうかの判断が特に重要です。  あらかじめ適切なデザインを行うと、実装とテストの時間の短縮ができます。  
  
 ここでは、機能を追加する 2 とおりの例を示します。  
  
-   最初の例では、文字列のペアを読み取る[単純な読み取り専用プロバイダーの作成](../../data/oledb/implementing-the-simple-read-only-provider.md)方法を示します。  
  
-   2 番目の例では、`IRowsetLocate` インターフェイスを追加することにより[単純な読み取り専用プロバイダーを拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)する方法を示します。  
  
## 参照  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)