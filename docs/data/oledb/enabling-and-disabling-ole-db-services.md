---
title: "OLE DB サービスの有効化と無効化 | Microsoft Docs"
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
  - "OLE DB サービス [OLE DB], 有効化と無効化"
  - "サービス プロバイダー [OLE DB]"
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OLE DB サービスの有効化と無効化
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB サービス コンポーネント マネージャーは、コンシューマーによって指定されたプロパティをプロバイダーでサポートされているプロパティと比較し、各サービス コンポーネントを起動してコンシューマーにより要求された機能拡張を満たすことができるかどうかを判断します。  たとえば、アプリケーションがスクロールできるカーソルを要求しても、プロバイダーが前方向カーソルしかサポートしていない場合、OLE DB サービス コンポーネント マネージャーは、クライアント カーソル エンジン サービス コンポーネントを起動して、スクロールできるようにします。  アプリケーションが、既定ではプロバイダーの行セットでサポートされている機能拡張に依存しているのに、アプリケーションがその機能を要求するプロパティを明示的に設定しない場合、その機能はクライアント カーソル エンジンで返される行セットに表示されない場合があります。  相互運用を可能にするために、アプリケーションは常に、必要に応じて機能拡張を明示的に要求するようにプロパティを設定する必要があります。  
  
 場合によっては、各 OLE DB サービスを無効にして、プロバイダーの特性に関する判断を行う既存のアプリケーションが適切に動作するようにする必要があります。  OLE DB サービスには、各サービスまたはすべてのサービスを接続ごと、または単一プロバイダーを使用しているすべてのアプリケーションに対して無効にする機能があります。  
  
## 参照  
 [OLE DB リソース プールとサービス](../../data/oledb/ole-db-resource-pooling-and-services.md)