---
title: "CColumnDomainUsage、CColumnDomainUsageInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szTableSchema"
  - "m_szCatalog"
  - "m_nColumnPropID"
  - "CColumnDomainUsageInfo"
  - "COLUMN_GUID"
  - "DOMAIN_NAME"
  - "m_szColumnName"
  - "DOMAIN_SCHEMA"
  - "DOMAIN_CATALOG"
  - "m_szTableCatalog"
  - "m_szSchema"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "CColumnDomainUsage"
  - "m_szTableName"
  - "m_szName"
  - "COLUMN_DOMAIN_USAGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColumnDomainUsage typedef クラス"
  - "CColumnDomainUsageInfo パラメーター クラス"
  - "COLUMN_DOMAIN_USAGE"
  - "COLUMN_GUID"
  - "COLUMN_NAME"
  - "COLUMN_PROPID"
  - "DOMAIN_CATALOG"
  - "DOMAIN_NAME"
  - "DOMAIN_SCHEMA"
  - "m_guidColumn"
  - "m_nColumnPropID"
  - "m_szCatalog"
  - "m_szColumnName"
  - "m_szName"
  - "m_szSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 5ff331f1-b99c-4002-9e04-367708c5759f
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CColumnDomainUsage、CColumnDomainUsageInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パラメーター **CColumnDomainUsageInfo**クラスを実装するに **CColumnDomainUsage** typedef クラスを呼び出します。  
  
## 解説  
 typedef クラスの使用の詳細については、" [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) を参照してください。  
  
 このクラスは、カタログに定義されるカタログで定義され、特定のユーザーが所有するドメインに依存する列を指定します。  
  
 次の表は、クラスのデータ メンバーとそれらに該当する OLE DB の列の一覧です。  スキーマと列の詳細については、" *OLE DB Programmer's Reference* の [COLUMN\_DOMAIN\_USAGE の行セット](https://msdn.microsoft.com/en-us/library/ms711240.aspx) を参照してください。  
  
|データ メンバー|OLE DB の列|  
|--------------|---------------|  
|m\_szCatalog|DOMAIN\_CATALOG|  
|m\_szSchema|DOMAIN\_SCHEMA|  
|m\_szName|DOMAIN\_NAME|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
  
## 要件  
 **ヘッダー:** atldbsch.h  
  
## 参照  
 [CRestrictions クラス](../Topic/CRestrictions%20Class.md)