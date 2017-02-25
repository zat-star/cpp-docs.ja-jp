---
title: "BEGIN_ACCESSOR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_ACCESSOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_ACCESSOR マクロ"
  - "BEGIN_ACCESSOR マクロ, 構文"
ms.assetid: 59d0ff3e-7cfd-4ce8-9a1c-d664c0892a52
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# BEGIN_ACCESSOR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アクセサー エントリの開始位置を示します。  
  
## 構文  
  
```  
  
BEGIN_ACCESSOR(  
num  
,   
bAuto  
 )  
  
```  
  
#### パラメーター  
 *num*  
 \[\]このアクセサーのマップのアクセサーのゼロの数。  
  
 *bAuto*  
 \[\]このアクセサーを自動アクセサーまたは手動アクセサーで指定します。  **true**、アクセサーが自動の場合; **false**が、手動アクセサーです。  自動アクセサーにするデータが移動操作の、フェッチされます。  
  
## 解説  
 行セットでの複数アクセサーの場合、`BEGIN_ACCESSOR_MAP` を指定し、個々のアクセサーに対して `BEGIN_ACCESSOR` マクロを使用する必要があります。  `BEGIN_ACCESSOR` マクロは `END_ACCESSOR` マクロについて説明します。  `BEGIN_ACCESSOR_MAP` マクロは `END_ACCESSOR_MAP` マクロについて説明します。  
  
## 使用例  
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [END\_ACCESSOR](../Topic/END_ACCESSOR.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)