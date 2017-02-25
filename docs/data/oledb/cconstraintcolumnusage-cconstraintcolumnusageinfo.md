---
title: "CConstraintColumnUsage、CConstraintColumnUsageInfo | Microsoft Docs"
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
  - "m_szConstraintCatalog"
  - "CConstraintColumnUsage"
  - "m_nColumnPropID"
  - "COLUMN_GUID"
  - "CONSTRAINT_NAME"
  - "m_szColumnName"
  - "m_szTableCatalog"
  - "m_szConstraintSchema"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "CONSTRAINT_COLUMN_USAGE"
  - "m_szTableName"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_SCHEMA"
  - "CConstraintColumnUsageInfo"
  - "m_szConstraintName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CConstraintColumnUsage TYPEDEF クラス"
  - "CConstraintColumnUsageInfo パラメーター クラス"
  - "COLUMN_GUID"
  - "COLUMN_NAME"
  - "COLUMN_PROPID"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_COLUMN_USAGE"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "m_guidColumn"
  - "m_nColumnPropID"
  - "m_szColumnName"
  - "m_szConstraintCatalog"
  - "m_szConstraintName"
  - "m_szConstraintSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 7d4d94e8-2025-4fcc-a176-c9b231eca77b
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CConstraintColumnUsage、CConstraintColumnUsageInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パラメーター **CConstraintColumnUsageInfo**クラスを実装するに **CConstraintColumnUsage** typedef クラスを呼び出します。  
  
## 解説  
 typedef クラスの使用の詳細については、" [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) を参照してください。  
  
 このクラスは参照制約、UNIQUE 制約、CHECK 制約とアサーションによって使用され、カタログで定義され、特定のユーザーが所有する列を指定します。  
  
 次の表は、クラスのデータ メンバーとそれらに該当する OLE DB の列の一覧です。  スキーマと列の詳細については、" *OLE DB Programmer's Reference* の [CONSTRAINT\_COLUMN\_USAGE の行セット](https://msdn.microsoft.com/en-us/library/ms724522.aspx) を参照してください。  
  
|データ メンバー|OLE DB の列|  
|--------------|---------------|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
|m\_szConstraintCatalog|CONSTRAINT\_CATALOG|  
|m\_szConstraintSchema|CONSTRAINT\_SCHEMA|  
|m\_szConstraintName|CONSTRAINT\_NAME|  
  
## 要件  
 **ヘッダー:** atldbsch.h  
  
## 参照  
 [CRestrictions クラス](../Topic/CRestrictions%20Class.md)