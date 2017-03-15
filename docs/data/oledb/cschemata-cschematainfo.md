---
title: "CSchemata、CSchemataInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DEFAULT_CHARACTER_SET_CATALOG"
  - "DEFAULT_CHARACTER_SET_SCHEMA"
  - "m_szCharName"
  - "CSchemataInfo"
  - "m_szCatalog"
  - "m_szCharCatalog"
  - "m_szOwner"
  - "m_szCharSchema"
  - "CSchemata"
  - "m_szName"
  - "DEFAULT_CHARACTER_SET_NAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSchemata TYPEDEF クラス"
  - "CSchemataInfo パラメーター クラス"
  - "DEFAULT_CHARACTER_SET_CATALOG"
  - "DEFAULT_CHARACTER_SET_NAME"
  - "DEFAULT_CHARACTER_SET_SCHEMA"
  - "m_szCatalog"
  - "m_szCharCatalog"
  - "m_szCharName"
  - "m_szCharSchema"
  - "m_szName"
  - "m_szOwner"
ms.assetid: 9d06d65a-c27b-446d-bc42-c7e487b0d9c5
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CSchemata、CSchemataInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パラメーター **CSchemataInfo**クラスを実装するに **CSchemata** typedef クラスを呼び出します。  
  
## 解説  
 typedef クラスの使用の詳細については、" [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) を参照してください。  
  
 このクラスは、特定のユーザーが所有するスキーマを識別します。  
  
 次の表は、クラスのデータ メンバーとそれらに該当する OLE DB の列の一覧です。  スキーマと列の詳細については、" *OLE DB Programmer's Reference* の [スキーマ行セット](https://msdn.microsoft.com/en-us/library/ms716887.aspx) を参照してください。  
  
|データ メンバー|OLE DB の列|  
|--------------|---------------|  
|m\_szCatalog|CATALOG\_NAME|  
|m\_szName|SCHEMA\_NAME|  
|m\_szOwner|SCHEMA\_OWNER|  
|m\_szCharCatalog|DEFAULT\_CHARACTER\_SET\_CATALOG|  
|m\_szCharSchema|DEFAULT\_CHARACTER\_SET\_SCHEMA|  
|m\_szCharName|DEFAULT\_CHARACTER\_SET\_NAME|  
  
## 要件  
 **ヘッダー:** atldbsch.h  
  
## 参照  
 [CRestrictions クラス](../Topic/CRestrictions%20Class.md)