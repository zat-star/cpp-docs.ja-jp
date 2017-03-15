---
title: "BLOB_ENTRY_LENGTH_STATUS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLOB_ENTRY_LENGTH_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_ENTRY_LENGTH_STATUS マクロ"
ms.assetid: 09da67de-421b-4853-9a26-760e38324502
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# BLOB_ENTRY_LENGTH_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バイナリ ラージ オブジェクト \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\) をバインドするために `BEGIN_COLUMN_MAP` と `END_COLUMN_MAP` で使用します。  [BLOB\_ENTRY](../Topic/BLOB_ENTRY.md)、このマクロと同様に、BLOB の列の長さと状態を取得します。  
  
## 構文  
  
```  
  
BLOB_ENTRY_LENGTH_STATUS(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
, length, status )  
```  
  
#### パラメーター  
 `nOrdinal`  
 \[入力\] 列番号。  
  
 *IID*  
 \[\] GUID を、BLOB を取得するために使用される **IDD\_ISequentialStream**などのインターフェイスです。  
  
 `flags`  
 \[\] OLE 構造化ストレージ モデル \(たとえば、**STGM\_READ**\) によって定義されたストレージ モード フラグ。  
  
 `data`  
 \[\]ユーザー レコードと対応するデータ メンバー。  
  
 *length*  
 \[\] BLOB 列のバイト \(実際の長さ\)。  
  
 *status*  
 \[\] BLOB のデータ列の状態。  
  
## 使用例  
 [以前に BLOB を取得してよいか。](../../data/oledb/retrieving-a-blob.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_ENTRY](../Topic/BLOB_ENTRY.md)   
 [BLOB\_ENTRY\_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB\_ENTRY\_STATUS](../Topic/BLOB_ENTRY_STATUS.md)