---
title: "PROPERTY_INFO_ENTRY_VALUE | Microsoft Docs"
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
  - "PROPERTY_INFO_ENTRY_VALUE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY_VALUE マクロ"
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PROPERTY_INFO_ENTRY_VALUE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティ セットの特定のプロパティを表します。  
  
## 構文  
  
```  
  
PROPERTY_INFO_ENTRY_VALUE(  
dwPropID  
, value )  
```  
  
#### パラメーター  
 *dwPropID*  
 \[\]プロパティを識別するためにプロパティ セット GUID とともに使用できる A [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) 値。  
  
 *value*  
 \[\]型 `DWORD`プロパティ値。  
  
## 解説  
 このマクロを使用すると、直接型 `DWORD`プロパティの値を指定できます。  ATLDB.H で定義されている既定値にプロパティを設定するには [PROPERTY\_INFO\_ENTRY](../../data/oledb/property-info-entry.md)を使用します。  値を、プロパティのフラグを設定するには、オプションは、[PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md)を使用します。  
  
## 使用例  
 [BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)