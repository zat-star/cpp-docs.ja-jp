---
title: "COLUMN_ENTRY | Microsoft Docs"
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
  - "COLUMN_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY マクロ"
ms.assetid: a10aef29-6d70-49ec-b572-5b5c4abe1b46
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行セット内の特定の列に行セットのバインディングを表します。  
  
## 構文  
  
```  
  
COLUMN_ENTRY(  
nOrdinal  
,   
data  
 )  
  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) を参照してください。  
  
 `nOrdinal`  
 \[入力\] 列番号。  
  
 `data`  
 \[\]ユーザー レコードと対応するデータ メンバー。  
  
## 解説  
 `COLUMN_ENTRY` マクロは次の場所で使用されています:  
  
-   [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md) の [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md) とマクロ中。  
  
-   [END\_ACCESSOR](../Topic/END_ACCESSOR.md) の [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) とマクロ中。  
  
-   [END\_PARAM\_MAP](../../data/oledb/end-param-map.md) の [BEGIN\_PARAM\_MAP](../Topic/BEGIN_PARAM_MAP.md) とマクロ中。  
  
## 使用例  
 マクロ [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md) トピック、および [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)の例を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../Topic/COLUMN_ENTRY_PS_LENGTH_STATUS.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../Topic/COLUMN_ENTRY_PS_STATUS.md)   
 [COLUMN\_ENTRY\_TYPE](../Topic/COLUMN_ENTRY_TYPE.md)   
 [COLUMN\_ENTRY\_TYPE\_SIZE](../Topic/COLUMN_ENTRY_TYPE_SIZE.md)   
 [END\_ACCESSOR](../Topic/END_ACCESSOR.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)