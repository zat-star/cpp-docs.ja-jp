---
title: "CBulkRowset::AddRefRows | Microsoft Docs"
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
  - "CBulkRowset::AddRefRows"
  - "AddRefRows"
  - "CBulkRowset.AddRefRows"
  - "ATL.CBulkRowset<TAccessor>.AddRefRows"
  - "ATL::CBulkRowset::AddRefRows"
  - "CBulkRowset<TAccessor>::AddRefRows"
  - "ATL.CBulkRowset.AddRefRows"
  - "ATL::CBulkRowset<TAccessor>::AddRefRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRefRows メソッド"
ms.assetid: 014be991-50f8-4377-ba16-fec80b54b406
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset::AddRefRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) を現在行セットから取得されるすべての行の参照カウントをインクリメントする場合に呼び出します。  
  
## 構文  
  
```  
  
HRESULT AddRefRows( ) throw( );  
  
```  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CBulkRowset クラス](../Topic/CBulkRowset%20Class.md)   
 [CBulkRowset::ReleaseRows](../Topic/CBulkRowset::ReleaseRows.md)