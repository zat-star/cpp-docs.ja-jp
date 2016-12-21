---
title: "CRowset::GetRowStatus | Microsoft Docs"
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
  - "CRowset.GetRowStatus"
  - "ATL.CRowset<TAccessor>.GetRowStatus"
  - "ATL::CRowset<TAccessor>::GetRowStatus"
  - "CRowset::GetRowStatus"
  - "ATL::CRowset::GetRowStatus"
  - "CRowset<TAccessor>::GetRowStatus"
  - "ATL.CRowset.GetRowStatus"
  - "CRowset<TAccessor>.GetRowStatus"
  - "GetRowStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowStatus メソッド"
ms.assetid: 7a29a235-cb7e-40c1-92ce-5441751febee
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::GetRowStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

すべての行の状態を返します。  
  
## 構文  
  
```  
  
      HRESULT GetRowStatus(   
   DBPENDINGSTATUS* pStatus    
) const throw( );  
```  
  
#### パラメーター  
 `pStatus`  
 \[\] `GetRowStatus` がステータス値を返す場所へのポインター。  OLE DB Programmer's Reference の DBPENDINGSTATUS を参照してください。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 このメソッドは、すべてのプロバイダーでサポートされない省略可能なインターフェイス `IRowsetUpdate`が必要ですが、; この場合、メソッドの戻り **E\_NOINTERFACE**。  また `VARIANT_TRUE` にテーブルの **開く** を呼び出す前に **DBPROP\_IRowsetUpdate** を設定または命じなければ、行セットが含まれます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)   
 [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/en-us/library/ms724377.aspx)