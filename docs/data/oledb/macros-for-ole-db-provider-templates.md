---
title: "OLE DB プロバイダー テンプレート用マクロ | Microsoft Docs"
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
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "マクロ, OLE DB プロバイダー テンプレート"
  - "OLE DB プロバイダー テンプレートのマクロ"
  - "OLE DB プロバイダー テンプレート, マクロ"
  - "プロバイダー テンプレートのマクロ (OLE DB)"
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB プロバイダー テンプレート用マクロ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB テンプレートのプロバイダーのマクロには、次の機能を提供し、T:  
  
### プロパティ セット マップ マクロ  
  
|||  
|-|-|  
|[BEGIN\_PROPERTY\_SET](../../data/oledb/begin-property-set.md)|プロパティ セットの開始位置を示します。|  
|[BEGIN\_PROPERTY\_SET\_EX](../../data/oledb/begin-property-set-ex.md)|プロパティ セットの開始位置を示します。|  
|[BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md)|プロバイダーの範囲外の表示\/非表示を定義できるプロパティ セットの開始位置を示します。|  
|[CHAIN\_PROPERTY\_SET](../Topic/CHAIN_PROPERTY_SET.md)|プロパティ グループをまとめてチェインします。|  
|[END\_PROPERTY\_SET](../../data/oledb/end-property-set.md)|プロパティ セットの終了位置を示します。|  
|[END\_PROPSET\_MAP](../../data/oledb/end-propset-map.md)|プロパティ セット マップの終了位置を示します。|  
|[PROPERTY\_INFO\_ENTRY](../../data/oledb/property-info-entry.md)|既定値にプロパティ セットの特定のプロパティを設定します。|  
|[PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md)|指定する値が、プロパティ セットの特定のプロパティを設定します。  有効なフラグとオプションを設定できます。|  
|[PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md)|指定する値が、プロパティ セットの特定のプロパティを設定します。|  
  
### 列マップ マクロ  
  
|||  
|-|-|  
|[BEGIN\_PROVIDER\_COLUMN\_MAP](../../data/oledb/begin-provider-column-map.md)|プロバイダーの列マップ エントリの開始位置を示します。|  
|[END\_PROVIDER\_COLUMN\_MAP](../../data/oledb/end-provider-column-map.md)|プロバイダーの列マップ エントリの終了位置を示します。|  
|[PROVIDER\_COLUMN\_ENTRY](../../data/oledb/provider-column-entry.md)|プロバイダーでサポートされる特定の列を表します。|  
|[PROVIDER\_COLUMN\_ENTRY\_GN](../../data/oledb/provider-column-entry-gn.md)|プロバイダーでサポートされる特定の列を表します。  列のサイズ、データ型、精度、スケール、およびスキーマ行セット GUID を指定できます。|  
|[PROVIDER\_COLUMN\_ENTRY\_FIXED](../Topic/PROVIDER_COLUMN_ENTRY_FIXED.md)|プロバイダーでサポートされる特定の列を表します。  列のデータ型を指定できます。|  
|[PROVIDER\_COLUMN\_ENTRY\_LENGTH](../../data/oledb/provider-column-entry-length.md)|プロバイダーでサポートされる特定の列を表します。  列のサイズを指定できます。|  
|[PROVIDER\_COLUMN\_ENTRY\_STR](../../data/oledb/provider-column-entry-str.md)|プロバイダーでサポートされる特定の列を表します。  これは列型が文字列であることを前提としています。|  
|[PROVIDER\_COLUMN\_ENTRY\_TYPE\_LENGTH](../../data/oledb/provider-column-entry-type-length.md)|プロバイダーでサポートされる特定の列を表します。  PROVIDER\_COLUMN\_ENTRY\_LENGTH が、割り当てのように、列のデータ型やサイズを指定できます。|  
|[PROVIDER\_COLUMN\_ENTRY\_WSTR](../../data/oledb/provider-column-entry-wstr.md)|プロバイダーでサポートされる特定の列を表します。  これは列型が Unicode 文字列であると想定されます。|  
  
### スキーマ行セットのマクロ  
  
|||  
|-|-|  
|[BEGIN\_SCHEMA\_MAP](../../data/oledb/begin-schema-map.md)|スキーマ マップの開始位置を示します。|  
|[SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)|クラスと GUID を関連付けます。|  
|[END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)|スキーマ マップの終了位置を示します。|  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB プロバイダー テンプレート リファレンス](../../data/oledb/ole-db-provider-templates-reference.md)