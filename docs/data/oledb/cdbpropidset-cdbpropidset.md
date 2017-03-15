---
title: "CDBPropIDSet::CDBPropIDSet | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDBPropIDSet::CDBPropIDSet"
  - "CDBPropIDSet"
  - "CDBPropIDSet.CDBPropIDSet"
  - "CDBPropIDSet::CDBPropIDSet"
  - "ATL.CDBPropIDSet.CDBPropIDSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropIDSet クラス, コンストラクター"
ms.assetid: e68cc20e-fce2-4cc1-9e9d-05c542334cc8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDBPropIDSet::CDBPropIDSet
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンストラクターです。  [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) 構造体の **rgProperties**、**cProperties**と \(オプション\) **guidPropertySet** フィールドを初期化します。  
  
## 構文  
  
```  
  
      CDBPropIDSet(  
   const GUID& guid   
);  
CDBPropIDSet(   
   const CDBPropIDSet& propidset    
);  
CDBPropIDSet( );  
```  
  
#### パラメーター  
 `guid`  
 \[\] **guidPropertySet** フィールドを初期化するために使用される GUID。A  
  
 *propidset*  
 \[\]コピーの構築の `CDBPropIDSet` の別のオブジェクト。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDBPropIDSet クラス](../../data/oledb/cdbpropidset-class.md)   
 [CDBPropIDSet::SetGUID](../Topic/CDBPropIDSet::SetGUID.md)