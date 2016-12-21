---
title: "BEGIN_PROPERTY_SET_EX | Microsoft Docs"
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
  - "BEGIN_PROPERTY_SET_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_PROPERTY_SET_EX マクロ"
ms.assetid: c95e7fab-edce-47b8-b282-200e53a2ea8a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_PROPERTY_SET_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティ セット マップにプロパティ セットの開始位置を示します。  
  
## 構文  
  
```  
  
BEGIN_PROPERTY_SET_EX(  
guid  
, flags )  
```  
  
#### パラメーター  
 `guid`  
 \[\]プロパティの GUID。  
  
 `flags`  
 \[\]、公開したくないプロパティ セットの **UPROPSET\_HIDDEN** またはプロバイダーのスコープ外で定義されているプロパティを公開するプロバイダーの **UPROPSET\_PASSTHROUGH**。  
  
## 使用例  
 [BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)