---
title: "CCharacterSets、CCharacterSetInfo | Microsoft Docs"
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
  - "m_szCollateName"
  - "m_szCatalog"
  - "DEFAULT_COLLATE_NAME"
  - "m_szCollateSchema"
  - "FORM_OF_USE"
  - "DEFAULT_COLLATE_SCHEMA"
  - "m_szCollateCatalog"
  - "CCharacterSets"
  - "CHARACTER_SET_NAME"
  - "DEFAULT_COLLATE_CATALOG"
  - "CHARACTER_SET_SCHEMA"
  - "m_szFormOfUse"
  - "NUMBER_OF_CHARACTERS"
  - "m_szSchema"
  - "CHARACTER_SET_CATALOG"
  - "CCharacterSetInfo"
  - "m_nNumCharacters"
  - "m_szName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCharacterSetInfo パラメーター クラス"
  - "CCharacterSets TYPEDEF クラス"
  - "CHARACTER_SET_CATALOG"
  - "CHARACTER_SET_NAME"
  - "CHARACTER_SET_SCHEMA"
  - "DEFAULT_COLLATE_CATALOG"
  - "DEFAULT_COLLATE_NAME"
  - "DEFAULT_COLLATE_SCHEMA"
  - "FORM_OF_USE OLE DB 列"
  - "m_nNumCharacters"
  - "m_szCatalog"
  - "m_szCollateCatalog"
  - "m_szCollateName"
  - "m_szCollateSchema"
  - "m_szFormOfUse"
  - "m_szName"
  - "m_szSchema"
  - "NUMBER_OF_CHARACTERS"
ms.assetid: 029d068c-8bb2-4fc0-8709-78ce7f74446e
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCharacterSets、CCharacterSetInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パラメーター **CCharacterSetInfo**クラスを実装するに **CCharacterSets** typedef クラスを呼び出します。  
  
## 解説  
 typedef クラスの使用の詳細については、" [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) を参照してください。  
  
 カタログで定義されているクラスは、特定のユーザーがアクセスできる文字セットを指定します。  
  
 次の表は、クラスのデータ メンバーとそれらに該当する OLE DB の列の一覧です。  スキーマと列の詳細については、" *OLE DB Programmer's Reference* の [CHARACTER\_SETS の行セット](https://msdn.microsoft.com/en-us/library/ms722638.aspx) を参照してください。  
  
|データ メンバー|OLE DB の列|  
|--------------|---------------|  
|m\_szCatalog|CHARACTER\_SET\_CATALOG|  
|m\_szSchema|CHARACTER\_SET\_SCHEMA|  
|m\_szName|CHARACTER\_SET\_NAME|  
|m\_szFormOfUse|FORM\_OF\_USE|  
|m\_nNumCharacters|NUMBER\_OF\_CHARACTERS|  
|m\_szCollateCatalog|DEFAULT\_COLLATE\_CATALOG|  
|m\_szCollateSchema|DEFAULT\_COLLATE\_SCHEMA|  
|m\_szCollateName|DEFAULT\_COLLATE\_NAME|  
  
## 要件  
 **ヘッダー:** atldbsch.h  
  
## 参照  
 [CRestrictions クラス](../Topic/CRestrictions%20Class.md)