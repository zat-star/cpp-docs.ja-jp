---
title: "CDynamicStringAccessorA クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicStringAccessorA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessorA クラス"
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDynamicStringAccessorA クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データベース スキーマ \(基になる構造\) が不明な場合にデータ ソースにアクセスできます。  
  
## 構文  
  
```  
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## 解説  
 これらはすべてのデータが文字列データとしてデータ ストアからアクセスしたが、`CDynamicStringAccessor` は ANSI 文字列データを要求するプロバイダーのフェッチ要求します。  
  
 `CDynamicStringAccessorA` は `CDynamicStringAccessor`から **GetString** と `SetString` を継承します。  使用する場合 `CDynamicStringAccessorA` のこれらのメソッドは、***BaseType*** です **CHAR**オブジェクト。  
  
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