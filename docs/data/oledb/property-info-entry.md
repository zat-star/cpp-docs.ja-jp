---
title: "PROPERTY_INFO_ENTRY | Microsoft Docs"
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
  - "PROPERTY_INFO_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY マクロ"
ms.assetid: f7bd23d6-52b4-4d6a-aa9a-1fca9834c8dc
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PROPERTY_INFO_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティ セットの特定のプロパティを表します。  
  
## 構文  
  
```  
  
PROPERTY_INFO_ENTRY(  
dwPropID   
)  
  
```  
  
#### パラメーター  
 *dwPropID*  
 \[入力\] プロパティ セット GUID と組み合わせて使用してプロパティを特定する [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) 値。  
  
## 解説  
 このマクロは、`DWORD` 型のプロパティ値を、ATLDB.H で定義された既定値に設定します。 選択した値にプロパティを設定するには、[PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md) を使用します。 プロパティの [VARTYPE](http://msdn.microsoft.com/ja-jp/317b911b-1805-402d-a9cb-159546bc88b4) と [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) を同時に設定するには、[PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md) を使用します。  
  
## 使用例  
 「[BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)