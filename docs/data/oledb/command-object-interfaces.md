---
title: "コマンド オブジェクト インターフェイス | Microsoft Docs"
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
  - "コマンド オブジェクト インターフェイス [C++]"
  - "コマンド オブジェクト [OLE DB]"
  - "OLE DB [C++], コマンド オブジェクト インターフェイス"
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# コマンド オブジェクト インターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンド オブジェクトは、`IAccessor` インターフェイスを使用してパラメーター バインディングを指定します。  コンシューマーは、`IAccessor::CreateAccessor` を呼び出し、これを `DBBINDING` 構造体の配列に渡します。  `DBBINDING` には、列バインディングに関する情報 \(型や長さなど\) が格納されています。  プロバイダーは構造体を受け取って、データの転送方法と、変換が必要かどうかを判断します。  
  
 `ICommandText` インターフェイスは、テキスト コマンドを指定する手段を提供します。  `ICommandProperties` インターフェイスは、すべてのコマンド プロパティを処理します。  
  
## 参照  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)