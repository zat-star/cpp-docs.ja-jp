---
title: "OLE DB アプリケーションでのリソース プール | Microsoft Docs"
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
  - "OLE DB プロバイダー, リソース プール"
  - "OLE DB サービス [OLE DB], リソース プール"
  - "OLE DB, リソース プール"
  - "リソース プール [OLE DB], サービス"
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OLE DB アプリケーションでのリソース プール
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーションのプールを利用するには、**IDataInitialize** または **IDBPromptInitialize** を通じてデータ ソースを取得することにより OLE DB サービスが起動していることを確認する必要があります。  `CoCreateInstance` を直接使用し、プロバイダーの CLSID に基づいてプロバイダーを呼び出す場合は、OLE DB サービスは起動しません。  
  
 OLE DB サービスは、**IDataInitialize** または **IDBPromptInitialize** への参照が保持されている限り、または接続が使用中である限り、接続されたデータ ソースのプールを維持します。  COM\+ 1.0 サービスまたはインターネット インフォメーション サービス \(IIS: Internet Information Services\) の環境では、プールは自動的に維持されます。  アプリケーションが COM\+ 1.0 サービスまたは IIS 環境の外部でプールを利用する場合は、**IDataInitialize** または **IDBPromptInitialize** への参照を保持するか、少なくとも 1 つの接続を持続する必要があります。  アプリケーションにより最後の接続が解放されたときにプールが破棄されないようにするには、アプリケーションが有効な間は参照を保持するか接続を持続します。  
  
 OLE DB サービスは、`Initialize` が呼び出された場合に接続が引き出されるプールを識別します。  接続がプールから引き出された後は、別のプールには移動できません。  したがって、`Initialize` を呼び出す前に、プロバイダー固有のインターフェイスに対して `UnInitialize` や `QueryInterface` を呼び出すなど、初期化情報を変更する処理をアプリケーションで行うことは避けてください。  また、**DBPROMPT\_NOPROMPT** 以外のプロンプト値で確立された接続はプールされません。  ただし、プロンプトを通じて確立された接続から取得された初期化文字列は、同じデータ ソースへの追加のプール接続を確立するために使用できます。  
  
 一部のプロバイダーは、セッションごとに独立した接続を確立する必要があります。  これらの追加接続は、分散トランザクションがある場合、そこで別個に確保する必要があります。  OLE DB サービスは、データ ソースごとに 1 つのセッションをキャッシュおよび再利用しますが、アプリケーションが 1 つのデータ ソースから一度に複数のセッションを要求した場合、プロバイダーは追加の接続を確立することになり、プールされていない追加のトランザクションを確保することになります。  実際には、単一データ ソースから複数のセッションを作成するよりも、プール環境で各セッションに別個のデータ ソースを作成する方が効率的です。  
  
 最後に、ADO は OLE DB サービスを自動的に利用するため、ADO を使用して接続を確立でき、その場合はプールと確保が自動的に行われます。  
  
## 参照  
 [OLE DB リソース プールとサービス](../../data/oledb/ole-db-resource-pooling-and-services.md)