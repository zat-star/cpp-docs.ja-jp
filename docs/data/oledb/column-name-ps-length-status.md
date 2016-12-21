---
title: "COLUMN_NAME_PS_LENGTH_STATUS | Microsoft Docs"
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
  - "COLUMN_NAME_PS_LENGTH_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_NAME_PS_LENGTH_STATUS マクロ"
ms.assetid: a1a2e2ca-f0ae-4896-8aa3-67a96c270b05
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_NAME_PS_LENGTH_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行セット内の特定の列に行セットのバインディングを表します。  [COLUMN\_NAME](../Topic/COLUMN_NAME.md)、このマクロと同様に、精度、スケール、列の長さと列のステータスを取得します。  
  
## 構文  
  
```  
  
COLUMN_NAME_PS_LENGTH_STATUS(  
pszName  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length  
,   
status )  
```  
  
#### パラメーター  
 `pszName`  
 \[\]項目の名前へのポインター。  名前は Unicode 文字列である必要があります。  名前の先頭に「L」を追加することにより実現できます \(例: `L"MyColumn"`。  
  
 `nPrecision`  
 \[\]、バインドし列の最大の精度。  
  
 `nScale`  
 \[\]、バインドしたい列の小数点以下桁数。  
  
 `data`  
 \[\]ユーザー レコードと対応するデータ メンバー。  
  
 *length*  
 \[\]列の長さにバインドされるようにします。  
  
 *status*  
 \[\]列のステータスにバインドされるようにします。  
  
## 解説  
 **COLUMN\_NAME\_\*** のマクロで使用される情報の [COLUMN\_NAME](../Topic/COLUMN_NAME.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [COLUMN\_NAME](../Topic/COLUMN_NAME.md)   
 [COLUMN\_NAME\_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN\_NAME\_LENGTH](../Topic/COLUMN_NAME_LENGTH.md)   
 [COLUMN\_NAME\_LENGTH\_STATUS](../Topic/COLUMN_NAME_LENGTH_STATUS.md)   
 [COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN\_NAME\_PS\_LENGTH](../Topic/COLUMN_NAME_PS_LENGTH.md)   
 [COLUMN\_NAME\_PS\_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN\_NAME\_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN\_NAME\_TYPE\_STATUS](../Topic/COLUMN_NAME_TYPE_STATUS.md)