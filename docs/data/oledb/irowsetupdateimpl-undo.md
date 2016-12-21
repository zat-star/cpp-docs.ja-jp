---
title: "IRowsetUpdateImpl::Undo | Microsoft Docs"
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
  - "ATL.IRowsetUpdateImpl.Undo"
  - "ATL::IRowsetUpdateImpl::Undo"
  - "IRowsetUpdateImpl::Undo"
  - "IRowsetUpdateImpl.Undo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Undo メソッド"
ms.assetid: f3dc7764-050c-4322-9b2f-9ca772a0fb88
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl::Undo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行への変更は、最後のフェッチまたは Update 元に戻します。  
  
## 構文  
  
```  
  
      STDMETHOD ( Undo )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### パラメーター  
 `hReserved`  
 \[\] [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)の `hChapter` パラメーターに対応します。  
  
 *pcRowsUndone*  
 \[\] [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)の `pcRows` パラメーターに対応します。  
  
 *prgRowsUndone*  
 \[\] [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)の *prgRows* パラメーターに対応します。  
  
 他のパラメーターには、*OLE DB Programmer's Reference*の [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetUpdateImpl クラス](../Topic/IRowsetUpdateImpl%20Class.md)