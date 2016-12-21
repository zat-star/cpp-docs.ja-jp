---
title: "CDynamicStringAccessorW クラス | Microsoft Docs"
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
  - "CDynamicStringAccessorW"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessorW クラス"
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessorW クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データベース スキーマ \(基になる構造\) が不明な場合にデータ ソースにアクセスできます。  
  
## 構文  
  
```  
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;  
```  
  
## 解説  
 これらはすべてのデータが文字列データとしてデータ ストアからアクセスしたが、`CDynamicStringAccessor` は Unicode 文字列データを要求するプロバイダーのフェッチ要求します。  
  
 `CDynamicStringAccessorW` は `CDynamicStringAccessor`から **GetString** と `SetString` を継承します。  使用する場合 `CDynamicStringAccessorW` のこれらのメソッドは、***BaseType*** です **WCHAR**オブジェクト。  
  
## 必要条件  
 **ヘッダー**: atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../Topic/CAccessor%20Class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor クラス](../Topic/CManualAccessor%20Class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)