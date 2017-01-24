---
title: "IRowsetImpl::AddRefRows | Microsoft Docs"
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
  - "IRowsetImpl::AddRefRows"
  - "AddRefRows"
  - "IRowsetImpl.AddRefRows"
  - "ATL::IRowsetImpl::AddRefRows"
  - "ATL.IRowsetImpl.AddRefRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRefRows メソッド"
ms.assetid: adc0989b-7592-432e-82d9-df4445431531
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::AddRefRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既存の行ハンドルの参照カウントをインクリメントします。  
  
## 構文  
  
```  
  
      STDMETHOD( AddRefRows )(  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[]   
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetImpl クラス](../Topic/IRowsetImpl%20Class.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)   
 [IRowsetImpl::GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)   
 [IRowsetImpl::ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)