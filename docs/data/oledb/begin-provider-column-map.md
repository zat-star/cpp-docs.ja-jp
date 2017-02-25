---
title: "BEGIN_PROVIDER_COLUMN_MAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_PROVIDER_COLUMN_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_PROVIDER_COLUMN_MAP マクロ"
ms.assetid: 506b8c0f-6be9-4c97-ba81-c4b7f7d428fa
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# BEGIN_PROVIDER_COLUMN_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロバイダーの列マップ エントリの開始位置を示します。  
  
## 構文  
  
```  
  
BEGIN_PROVIDER_COLUMN_MAP(  
theClass   
)  
  
```  
  
#### パラメーター  
 `theClass`  
 \[\]クラスの名前は、このマップに属します。  
  
## 使用例  
 サンプル プロバイダーの列マップがあります:  
  
 [!CODE [NVC_OLEDB_Provider#4](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Provider#4)]  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)