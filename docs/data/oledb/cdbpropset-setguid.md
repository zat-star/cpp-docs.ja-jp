---
title: "CDBPropSet::SetGUID | Microsoft Docs"
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
  - "ATL.CDBPropSet.SetGUID"
  - "CDBPropSet.SetGUID"
  - "ATL::CDBPropSet::SetGUID"
  - "SetGUID"
  - "CDBPropSet::SetGUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddProperty メソッド"
  - "SetGUID メソッド"
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropSet::SetGUID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**DBPROPSET** 構造体の **guidPropertySet** フィールドを設定します。  
  
## 構文  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### パラメーター  
 `guid`  
 \[\] [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の **guidPropertySet** フィールドを設定するために使用される GUID。A  
  
## 解説  
 このフィールドは [コンストラクター](../Topic/CDBPropSet::CDBPropSet.md) でも設定できます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDBPropSet クラス](../Topic/CDBPropSet%20Class.md)