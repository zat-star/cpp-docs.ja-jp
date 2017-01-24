---
title: "CReferentialConstraints、CReferentialConstraintInfo | Microsoft Docs"
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
  - "m_szUniqueName"
  - "m_szCatalog"
  - "DELETE_RULE"
  - "m_szUniqueCatalog"
  - "CONSTRAINT_NAME"
  - "CReferentialConstraintInfo"
  - "MATCH_OPTION"
  - "m_szSchema"
  - "m_szDeleteRule"
  - "m_szUpdateRule"
  - "m_szUniqueSchema"
  - "CReferentialConstraints"
  - "m_szName"
  - "CONSTRAINT_CATALOG"
  - "m_szMatchOption"
  - "CONSTRAINT_SCHEMA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "CReferentialConstraintInfo パラメーター クラス"
  - "CReferentialConstraints typedef クラス"
  - "DELETE_RULE"
  - "DESCRIPTION クラスのデータ メンバー"
  - "m_szCatalog"
  - "m_szDeleteRule"
  - "m_szDescription"
  - "m_szMatchOption"
  - "m_szName"
  - "m_szSchema"
  - "m_szUniqueCatalog"
  - "m_szUniqueName"
  - "m_szUniqueSchema"
  - "m_szUpdateRule"
  - "MATCH_OPTION"
ms.assetid: 5d485358-be29-41c2-b0ce-19e023598e73
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CReferentialConstraints、CReferentialConstraintInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パラメーター **CReferentialConstraintInfo**クラスを実装するに **CReferentialConstraints** typedef クラスを呼び出します。  
  
## 解説  
 typedef クラスの使用の詳細については、" [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) を参照してください。  
  
 このクラスは、カタログに定義された特定のユーザーが所有する参照制約を識別します。  
  
 次の表は、クラスのデータ メンバーとそれらに該当する OLE DB の列の一覧です。  スキーマと列の詳細については、" *OLE DB Programmer's Reference* の [REFERENTIAL\_CONSTRAINTS の行セット](https://msdn.microsoft.com/en-us/library/ms719737.aspx) を参照してください。  
  
|データ メンバー|OLE DB の列|  
|--------------|---------------|  
|m\_szCatalog|CONSTRAINT\_CATALOG|  
|m\_szSchema|CONSTRAINT\_SCHEMA|  
|m\_szName|CONSTRAINT\_NAME|  
|m\_szUniqueCatalog|UNIQUE\_CONSTRAINT\_CATALOG|  
|m\_szUniqueSchema|UNIQUE\_CONSTRAINT\_SCHEMA|  
|m\_szUniqueName|UNIQUE\_CONSTRAINT\_NAME|  
|m\_szMatchOption|MATCH\_OPTION|  
|m\_szUpdateRule|UPDATE\_RULE|  
|m\_szDeleteRule|DELETE\_RULE|  
|m\_szDescription|DESCRIPTION|  
  
## 要件  
 **ヘッダー:** atldbsch.h  
  
## 参照  
 [CRestrictions クラス](../Topic/CRestrictions%20Class.md)