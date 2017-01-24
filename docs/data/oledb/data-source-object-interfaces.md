---
title: "データ ソース オブジェクト インターフェイス | Microsoft Docs"
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
  - "データ ソース オブジェクト [C++]"
  - "データ ソース オブジェクト [C++], インターフェイス"
  - "インターフェイス [C++], 一覧"
  - "インターフェイス [C++], OLE DB"
  - "OLE DB [C++], インターフェイス"
  - "OLE DB プロバイダー テンプレート [C++], オブジェクト インターフェイス"
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# データ ソース オブジェクト インターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次の表は、OLE DB がデータ ソース オブジェクトに対して定義している必須インターフェイスと省略可能なインターフェイスを示しています。  
  
|インターフェイス|必須?|OLE DB テンプレートで実装されていますか?|  
|--------------|---------|------------------------------|  
|`IDBCreateSession`|必須|Yes|  
|`IDBInitialize`|必須|Yes|  
|`IDBProperties`|必須|Yes|  
|[\<caps:sentence id\="tgt14" sentenceid\="731a3344bc1c6b5f8f54d9de3524f18a" class\="tgtSentence"\>IPersist\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms688695)|必須|Yes|  
|[\<caps:sentence id\="tgt17" sentenceid\="63e99e63156fc90f114fa402662387ef" class\="tgtSentence"\>IConnectionPointContainer\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683857)|省略可能|No|  
|`IDBDataSourceAdmin`|省略可能|No|  
|`IDBInfo`|省略可能|No|  
|[\<caps:sentence id\="tgt26" sentenceid\="7e6a12ecd4cb3b1bd45dccf9421ed567" class\="tgtSentence"\>IPersistFile\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms687223)|省略可能|No|  
|`ISupportErrorInfo`|省略可能|No|  
  
 データ ソース オブジェクトは、継承によって、`IDBProperties`、`IDBInitialize`、および `IDBCreateSession` の各インターフェイスを実装します。  追加機能をサポートするかどうかは、これらの実装クラスを継承するかどうかによって決まります。  `IDBDataSourceAdmin` インターフェイスをサポートする場合には、`IDBDataSourceAdminImpl` クラスから継承する必要があります。  
  
## 参照  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)