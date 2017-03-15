---
title: "END_ACCESSOR_MAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "END_ACCESSOR_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "END_ACCESSOR_MAP マクロ"
ms.assetid: ede813c7-46c9-48a6-aa1a-8ebf38e92023
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# END_ACCESSOR_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アクセサーのエントリ マップの終了位置を示します。  
  
## 構文  
  
```  
  
END_ACCESSOR_MAP( )  
  
```  
  
## 解説  
 行セットでの複数アクセサーの場合、`BEGIN_ACCESSOR_MAP` を指定し、個々のアクセサーに対して `BEGIN_ACCESSOR` マクロを使用する必要があります。  `BEGIN_ACCESSOR` マクロは `END_ACCESSOR` マクロについて説明します。  `BEGIN_ACCESSOR_MAP` マクロは `END_ACCESSOR_MAP` マクロについて説明します。  
  
## 使用例  
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)