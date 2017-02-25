---
title: "IRowsetLocateImpl::Hash | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetLocateImpl::Hash"
  - "IRowsetLocateImpl.Hash"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Hash メソッド"
ms.assetid: 7df4386d-80fb-4332-a85f-baae98cdc6e0
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetLocateImpl::Hash
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定したブックマークのハッシュ値を返します。  
  
## 構文  
  
```  
  
      STDMETHOD ( Hash )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmarks,  
   const DBBKMARK* rgcbBookmarks[],  
   const BYTE* rgpBookmarks[],  
   DBHASHVALUE rgHashValues[],  
   DBROWSTATUS rgBookmarkStatus[]   
);  
```  
  
#### パラメーター  
 `hReserved`  
 \[\] [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx)に `hChapter` パラメーターに対応します。  
  
 他のパラメーターには、*OLE DB Programmer's Reference*の [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetLocateImpl クラス](../../data/oledb/irowsetlocateimpl-class.md)