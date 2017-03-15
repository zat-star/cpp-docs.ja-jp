---
title: "トランザクション オブジェクト インターフェイス | Microsoft Docs"
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
  - "インターフェイス, 一覧"
  - "インターフェイス, OLE DB"
  - "OLE DB プロバイダー テンプレート, オブジェクト インターフェイス"
  - "OLE DB プロバイダー, トランザクション サポート"
  - "OLE DB, インターフェイス"
  - "トランザクション オブジェクト インターフェイス"
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# トランザクション オブジェクト インターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

トランザクション オブジェクトは、データ ソースに対する分割不可能な作業単位を定義し、それらの作業単位が相互にどのように関連するかを指定します。  このオブジェクトは、OLE DB プロバイダー テンプレートで直接にはサポートされません。つまり、独自のオブジェクトを作成する必要があります。  
  
 次の表は、OLE DB がトランザクション オブジェクトに対して定義している必須インターフェイスと省略可能なインターフェイスを示しています。  
  
|インターフェイス|必須?|OLE DB テンプレートで実装されていますか?|  
|--------------|---------|------------------------------|  
|[\<caps:sentence id\="tgt7" sentenceid\="63e99e63156fc90f114fa402662387ef" class\="tgtSentence"\>IConnectionPointContainer\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683857)|必須|No|  
|[\<caps:sentence id\="tgt10" sentenceid\="f5097e646bb93cceb560c38e13953a89" class\="tgtSentence"\>ITransaction\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|必須|No|  
|[\<caps:sentence id\="tgt13" sentenceid\="130702210bcc45e1afd88b1f2aae1a0b" class\="tgtSentence"\>ISupportErrorInfo\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|省略可能|No|  
  
## 参照  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)