---
title: "プロバイダーのサービスの有効化と無効化 | Microsoft Docs"
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
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# プロバイダーのサービスの有効化と無効化
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既定では、OLE DB の各サービスは、単一のプロバイダーにアクセスするすべてのアプリケーションに対して有効または無効にできます。  これを行うには、有効または無効にするサービスを指定する次のような `DWORD` 値を持つ **OLEDB\_SERVICES** レジストリ エントリをプロバイダーの CLSID の下に追加します。  
  
|既定の有効なサービス|キーワード値|  
|----------------|------------|  
|すべてのサービス \(既定\)|0xffffffff|  
|プールと自動確保を除くすべて|0xfffffffe|  
|クライアント カーソルを除くすべて|0xfffffffb|  
|プール、自動確保、およびクライアント カーソルを除くすべて|0xfffffff0|  
|サービスなし|0x00000000|  
|集約なし、すべてのサービスを無効化|\<存在しないキー\>|  
  
## 参照  
 [OLE DB サービスの有効化と無効化](../../data/oledb/enabling-and-disabling-ole-db-services.md)