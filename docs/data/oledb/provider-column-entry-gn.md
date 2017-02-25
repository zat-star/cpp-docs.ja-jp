---
title: "PROVIDER_COLUMN_ENTRY_GN | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_COLUMN_ENTRY_GN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_GN マクロ"
ms.assetid: be77ba85-634c-4e28-832f-d2fa40413254
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# PROVIDER_COLUMN_ENTRY_GN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロバイダーでサポートされる特定の列を表します。  
  
## 構文  
  
```  
  
PROVIDER_COLUMN_ENTRY_GN (  
name  
, ordinal, flags, colSize, dbtype, precision, scale, guid )  
```  
  
#### パラメーター  
 *name*  
 \[\]項目の名前です。  
  
 `ordinal`  
 \[入力\] 列番号。  列がブックマーク列でない場合は、行数は 0 です。  
  
 `flags`  
 \[\]データを返すかを指定します。  [DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)の `dwFlags` の説明を参照してください。  
  
 *colSize*  
 \[\]列のサイズ。  
  
 `dbtype`  
 \[\]値のデータ型を示します。  [DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)の **wType** の説明を参照してください。  
  
 *precision*  
 \[\] *dbType が*`DBTYPE_NUMERIC` または **DBTYPE\_DECIMAL**の精度がデータを取得するときに使用されます。  [DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)の **bPrecision** の説明を参照してください。  
  
 `scale`  
 \[\] dbType が `DBTYPE_NUMERIC` または **DBTYPE\_DECIMAL**のスケールを使用してデータを取得するためにいつ表示されます。  [DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)の **bScale** の説明を参照してください。  
  
 `guid`  
 スキーマ行セットの GUID。  スキーマ行セットおよび GUID の一覧の *OLE DB Programmer's Reference* の [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) を参照してください。  
  
## 解説  
 割り当てサイズ、列のデータ型、精度、スケール、およびスキーマ行セット GUID を指定できます。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)