---
title: "IRowsetImpl::RefRows | Microsoft Docs"
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
  - "ATL::IRowsetImpl::RefRows"
  - "ATL.IRowsetImpl.RefRows"
  - "IRowsetImpl.RefRows"
  - "RefRows"
  - "IRowsetImpl::RefRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RefRows メソッド"
ms.assetid: 1c048a2a-65dc-4bba-9c81-a23c0dc249c8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::RefRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インクリメントに [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) と [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) によって呼び出され、または既存の行ハンドルの参照カウントを解放します。  
  
## 構文  
  
```  
  
      HRESULT RefRows(  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[],  
   BOOL bAdd   
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) を参照してください。  
  
## 戻り値  
 標準の `HRESULT` 値。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetImpl クラス](../Topic/IRowsetImpl%20Class.md)   
 [CSimpleRow クラス](../Topic/CSimpleRow%20Class.md)