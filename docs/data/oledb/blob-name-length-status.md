---
title: "BLOB_NAME_LENGTH_STATUS | Microsoft Docs"
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
  - "BLOB_NAME_LENGTH_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_NAME_LENGTH_STATUS マクロ"
ms.assetid: 3cc3ec8d-80a5-4522-848a-123fcaee58cb
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BLOB_NAME_LENGTH_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バイナリ ラージ オブジェクト \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\) をバインドするために `BEGIN_COLUMN_MAP` と `END_COLUMN_MAP` で使用します。  [BLOB\_NAME](../../data/oledb/blob-name.md)、このマクロと同様に、BLOB のデータ列の長さと状態を取得します。  
  
## 構文  
  
```  
  
BLOB_NAME_LENGTH_STATUS(  
pszName  
,   
IID  
,   
flags  
,   
data  
,   
length  
, status )  
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
  
 *status*  
 \[\] BLOB フィールドの状態。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_NAME](../../data/oledb/blob-name.md)   
 [BLOB\_NAME\_LENGTH](../../data/oledb/blob-name-length.md)   
 [BLOB\_NAME\_STATUS](../Topic/BLOB_NAME_STATUS.md)