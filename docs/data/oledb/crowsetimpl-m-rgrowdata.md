---
title: "CRowsetImpl::m_rgRowData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl.m_rgRowData"
  - "CRowsetImpl::m_rgRowData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_rgRowData"
ms.assetid: e4e75ca7-12e8-4a0b-94e8-e395c21385b2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowsetImpl::m_rgRowData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CRowsetImpl`にユーザー レコード テンプレート引数で templatizes 既定で、`CAtlArray`。  
  
## 構文  
  
```  
  
ArrayType CRowsetBaseImpl::m_rgRowData;  
  
```  
  
## 解説  
 **ArrayType** は `CRowsetImpl`にテンプレート パラメーターです。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)   
 [CRowsetImpl::m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)