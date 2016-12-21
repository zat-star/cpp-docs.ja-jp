---
title: "OLE DB コンシューマーとプロバイダー | Microsoft Docs"
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
  - "OLE DB コンシューマー"
  - "OLE DB コンシューマー, OLE DB データ アーキテクチャ"
  - "OLE DB プロバイダー"
  - "OLE DB プロバイダー, OLE DB データ アーキテクチャ"
  - "OLE DB, データ モデル"
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB コンシューマーとプロバイダー
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB アーキテクチャでは、コンシューマーとプロバイダーの概念が使用されています。  コンシューマーはデータの要求を行います。  プロバイダーは、データを表形式に変換し、コンシューマーに返すことによってこれらの要求に応答します。  コンシューマーが行う呼び出しは、プロバイダーで実装されている必要があります。  
  
 技術的な定義では、コンシューマーは、OLE DB インターフェイスを通じてデータにアクセスする任意のシステムまたはアプリケーション コードです。必ずしも OLE DB コンポーネントではありません。  インターフェイスはプロバイダーで実装されます。  プロバイダーは、データへのアクセスをカプセル化してほかのオブジェクト \(つまりコンシューマー\) に公開する OLE DB インターフェイスを実装するソフトウェア コンポーネントです。  
  
 役割の面から見ると、コンシューマーは、OLE DB インターフェイスでメソッドを呼び出し、OLE DB プロバイダーは、必要な OLE DB インターフェイスを実装します。  
  
 OLE DB では、クライアントやサーバーという用語は使用しません。これらの役割付けが常に \(特に n 層の状況では\) 妥当であるとは限らないからです。  コンシューマーは、他のコンポーネントを処理する層のコンポーネントである場合があるので、コンシューマーをクライアント コンポーネントと呼ぶと混乱を招きます。  また、プロバイダーはサーバーというよりはデータベース ドライバーに近い動作をすることがあります。  
  
## 参照  
 [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)   
 [OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)