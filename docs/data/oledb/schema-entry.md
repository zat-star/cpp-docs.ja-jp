---
title: "SCHEMA_ENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SCHEMA_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SCHEMA_ENTRY マクロ"
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# SCHEMA_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

クラスと GUID を関連付けます。  
  
## 構文  
  
```  
  
      SCHEMA_ENTRY(  
   guid,  
   rowsetClass   
);   
```  
  
#### パラメーター  
 `guid`  
 スキーマ行セットの GUID。  スキーマ行セットおよび GUID の一覧の *OLE DB Programmer's Reference* の [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) を参照してください。  
  
 *rowsetClass*  
 スキーマ行セットを表すために作成されるクラス。  
  
## 解説  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) は、GUID の一覧のマップを呼び出すことも、GUID が指定された行セットを作成できます。  スキーマ行セット `IDBSchemaRowsetImpl` は標準 `CRowsetImpl`\-次の **実行** のシグネチャを持つメソッドを提供する必要があることを除けば、派生クラスに似ています。作成します:  
  
 `HRESULT Execute (LONG* pcRowsAffected, ULONG cRestrictions,`  
  
 `const VARIANT* rgRestrictions)`  
  
 **実行** のこの関数は行セットのデータを設定します。  ATL プロジェクト ウィザードは 3 個の OLE DB スキーマのプロジェクトに *OLE DB Programmer's Reference*で [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) "に説明されているように、3 番目のスキーマ行セットを作成し、T:  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA\_COLUMNS**  
  
-   **DBSCHEMA\_PROVIDER\_TYPES**  
  
 ウィザードは、スキーマ マップの 3 種類の対応するエントリを追加します。  ウィザードのプロバイダーを作成する方法の詳細については、" [OLE DB テンプレート プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN\_SCHEMA\_MAP](../../data/oledb/begin-schema-map.md)   
 [END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)