---
title: "プロバイダーでサポートされないデータの変換 | Microsoft Docs"
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
  - "OLE DB プロバイダー テンプレート, サポートされないデータ型"
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロバイダーでサポートされないデータの変換
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンシューマーが、プロバイダーでサポートされていないデータ型を要求すると、OLE DB プロバイダー テンプレートの `IRowsetImpl::GetData` のコードは Msdadc.dll を呼び出してデータ型を変換します。  
  
 データ変換を必要とする `IRowsetChange` などのインターフェイスを実装する場合は、Msdaenum.dll を呼び出して変換を実行できます。  例として、Atldb.h で定義されている `GetData` を使用します。  
  
## 参照  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)