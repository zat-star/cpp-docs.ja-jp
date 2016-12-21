---
title: "IRowsetImpl::m_bCanFetchBack | Microsoft Docs"
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
  - "ATL.IRowsetImpl.m_bCanFetchBack"
  - "ATL::IRowsetImpl::m_bCanFetchBack"
  - "IRowsetImpl.m_bCanFetchBack"
  - "IRowsetImpl::m_bCanFetchBack"
  - "m_bCanFetchBack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bCanFetchBack"
ms.assetid: cfa007b0-7ba5-48a3-9d05-9f1916305fb7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::m_bCanFetchBack
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロバイダーが後方フェッチをサポートするかどうかを示します。  
  
## 構文  
  
```  
  
unsigned m_bCanFetchBack:1;  
  
```  
  
## 解説  
 **DBPROPSET\_ROWSET** グループのプロパティを **DBPROP\_CANFETCHBACKWARDS** にリンクされます。  プロバイダーは true と **m\_bCanFetchBackwards** の **DBPROP\_CANFETCHBACKWARDS** をサポートする必要があります。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetImpl クラス](../Topic/IRowsetImpl%20Class.md)   
 [IRowsetImpl::m\_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)