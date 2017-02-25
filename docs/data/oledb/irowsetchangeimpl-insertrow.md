---
title: "IRowsetChangeImpl::InsertRow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetChangeImpl.InsertRow"
  - "InsertRow"
  - "IRowsetChangeImpl.InsertRow"
  - "ATL::IRowsetChangeImpl::InsertRow"
  - "IRowsetChangeImpl::InsertRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InsertRow メソッド"
ms.assetid: 93027be3-921e-438e-a19a-6e5aadb813eb
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# IRowsetChangeImpl::InsertRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行セットの新しい行を作成し、初期化します。  
  
## 構文  
  
```  
  
      STDMETHOD ( InsertRow )(  
   HCHAPTER /* hReserved */,  
   HACCESSOR hAccessor,  
   void* pData,  
   HROW* phRow   
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [IRowsetChange::InsertRow](https://msdn.microsoft.com/en-us/library/ms716921.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetChangeImpl クラス](../../data/oledb/irowsetchangeimpl-class.md)