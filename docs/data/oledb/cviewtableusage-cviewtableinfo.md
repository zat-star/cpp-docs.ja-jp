---
title: "CViewTableUsage、CViewTableInfo | Microsoft Docs"
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
  - "CViewTableInfo"
  - "m_szTableCatalog"
  - "m_szSchema"
  - "m_szTableName"
  - "m_szName"
  - "CViewTableUsage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CViewTableInfo パラメーター クラス"
  - "CViewTableUsage TYPEDEF クラス"
  - "m_szCatalog"
  - "m_szName"
  - "m_szSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 10b74f2a-8010-4f97-acc2-ffce07349981
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CViewTableUsage、CViewTableInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パラメーター **CViewTableInfo**クラスを実装するに **CViewTableUsage** typedef クラスを呼び出します。  
  
## 解説  
 typedef クラスの使用の詳細については、" [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) を参照してください。  
  
 このクラスは、カタログに定義された特定のユーザーがアクセスできる表示されていたテーブルを識別します。  
  
 次の表は、クラスのデータ メンバーとそれらに該当する OLE DB の列の一覧です。  スキーマと列の詳細については、" *OLE DB Programmer's Reference* の [VIEW\_TABLE\_USAGE の行セット](https://msdn.microsoft.com/en-us/library/ms719727.aspx) を参照してください。  
  
|データ メンバー|OLE DB の列|  
|--------------|---------------|  
|m\_szCatalog|VIEW\_CATALOG|  
|m\_szSchema|VIEW\_SCHEMA|  
|m\_szName|VIEW\_NAME|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
  
## 要件  
 **ヘッダー:** atldbsch.h  
  
## 参照  
 [CRestrictions クラス](../Topic/CRestrictions%20Class.md)