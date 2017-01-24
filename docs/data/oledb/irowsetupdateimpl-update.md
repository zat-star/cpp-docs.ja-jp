---
title: "IRowsetUpdateImpl::Update | Microsoft Docs"
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
  - "ATL::IRowsetUpdateImpl::Update"
  - "IRowsetUpdateImpl::Update"
  - "IRowsetUpdateImpl.Update"
  - "ATL.IRowsetUpdateImpl.Update"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Update メソッド"
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl::Update
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

変更された行への変更は、最後のフェッチまたは更新を送信します。  
  
## 構文  
  
```  
  
      STDMETHOD ( Update )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### パラメーター  
 `hReserved`  
 \[\] [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)の `hChapter` パラメーターに対応します。  
  
 他のパラメーターには、*OLE DB Programmer's Reference*の [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx) を参照してください。  
  
## 解説  
 変更は [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)を呼び出して送信されます。  コンシューマーは [CRowset::Update](../Topic/CRowset::Update.md) を変更を有効にするために呼び出す必要があります。  *OLE DB Programmer's Reference*の [行の状態](https://msdn.microsoft.com/en-us/library/ms722752.aspx) "に説明されているように、適切な値に *prgRowstatus を* 設定します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetUpdateImpl クラス](../Topic/IRowsetUpdateImpl%20Class.md)