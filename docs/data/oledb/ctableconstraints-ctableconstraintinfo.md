---
title: "CTableConstraints、CTableConstraintInfo | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szTableSchema"
  - "CONSTRAINT_TYPE"
  - "m_szCatalog"
  - "CTableConstraints"
  - "m_bInitiallyDeferred"
  - "CONSTRAINT_NAME"
  - "m_szTableCatalog"
  - "m_szType"
  - "m_szSchema"
  - "INITIALLY_DEFERRED"
  - "CTableConstraintInfo"
  - "m_szTableName"
  - "m_bIsDeferrable"
  - "m_szName"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_SCHEMA"
  - "IS_DEFERRABLE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "CONSTRAINT_TYPE"
  - "CTableConstraintInfo パラメーター クラス"
  - "CTableConstraints TYPEDEF クラス"
  - "DESCRIPTION クラスのデータ メンバー"
  - "INITIALLY_DEFERRED"
  - "IS_DEFERRABLE"
  - "m_bInitiallyDeferred"
  - "m_bIsDeferrable"
  - "m_szCatalog"
  - "m_szDescription"
  - "m_szName"
  - "m_szSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "m_szType"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: aaa07ade-0bfa-41d0-94df-8342152a4ff0
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTableConstraints、CTableConstraintInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パラメーター **CTableConstraintInfo**クラスを実装するに **CTableConstraints** typedef クラスを呼び出します。  
  
## 解説  
 typedef クラスの使用の詳細については、" [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) を参照してください。  
  
 このクラスは、カタログに定義された特定のユーザーが所有しているテーブル制約を指定します。  
  
 次の表は、クラスのデータ メンバーとそれらに該当する OLE DB の列の一覧です。  スキーマと列の詳細については、" *OLE DB Programmer's Reference* の [TABLE\_CONSTRAINTS の行セット](https://msdn.microsoft.com/en-us/library/ms715921.aspx) を参照してください。  
  
|データ メンバー|OLE DB の列|  
|--------------|---------------|  
|m\_szCatalog|CONSTRAINT\_CATALOG|  
|m\_szSchema|CONSTRAINT\_SCHEMA|  
|m\_szName|CONSTRAINT\_NAME|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szType|CONSTRAINT\_TYPE|  
|m\_bIsDeferrable|IS\_DEFERRABLE|  
|m\_bInitiallyDeferred|INITIALLY\_DEFERRED|  
|m\_szDescription|DESCRIPTION|  
  
## 要件  
 **ヘッダー:** atldbsch.h  
  
## 参照  
 [CRestrictions クラス](../Topic/CRestrictions%20Class.md)