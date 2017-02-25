---
title: "BLOB_NAME_LENGTH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLOB_NAME_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_NAME_LENGTH マクロ"
ms.assetid: 38150260-a127-486d-a7ab-0d01b731b6fd
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# BLOB_NAME_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バイナリ ラージ オブジェクト \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\) をバインドするために `BEGIN_COLUMN_MAP` と `END_COLUMN_MAP` で使用します。  [BLOB\_NAME](../../data/oledb/blob-name.md)、このマクロと同様に、BLOB のデータ列の長さ \(バイト単位\) を取得します。  
  
## 構文  
  
```  
  
BLOB_NAME_LENGTH(  
pszName  
,   
IID  
,   
flags  
,   
data  
,   
length )  
```  
  
#### パラメーター  
 `pszName`  
 \[\]項目の名前へのポインター。  名前は Unicode 文字列である必要があります。  名前の先頭に「L」を追加することにより実現できます \(例: `L"MyColumn"`。  
  
 *IID*  
 \[\] GUID を、BLOB を取得するために使用される **IDD\_ISequentialStream**などのインターフェイスです。  
  
 `flags`  
 \[\] OLE 構造化ストレージ モデル \(たとえば、**STGM\_READ**\) によって定義されたストレージ モード フラグ。  
  
 `data`  
 \[\]ユーザー レコードと対応するデータ メンバー。  
  
 *length*  
 \[\] BLOB 列のバイト \(実際の長さ\)。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_NAME](../../data/oledb/blob-name.md)   
 [BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB\_NAME\_STATUS](../Topic/BLOB_NAME_STATUS.md)