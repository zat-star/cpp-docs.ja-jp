---
title: "CRowset::MoveFirst | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset<TAccessor>::MoveFirst"
  - "ATL::CRowset::MoveFirst"
  - "CRowset<TAccessor>.MoveFirst"
  - "CRowset::MoveFirst"
  - "CRowset.MoveFirst"
  - "ATL.CRowset.MoveFirst"
  - "ATL.CRowset<TAccessor>.MoveFirst"
  - "ATL::CRowset<TAccessor>::MoveFirst"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveFirst メソッド"
ms.assetid: a17c0799-ead9-4d85-9a1d-8b17188d01e3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::MoveFirst
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

カーソルを初期位置に移動し、最初の行を取得します。  
  
## 構文  
  
```  
  
HRESULT MoveFirst( ) throw( );  
  
```  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) を行セットが作成されたときに、フェッチ場所の初期位置 \(位置\) に次フェッチ場所の位置を変更するために呼び出すと、最初の行を取得します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)