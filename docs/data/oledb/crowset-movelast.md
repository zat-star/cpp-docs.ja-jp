---
title: "CRowset::MoveLast | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CRowset<TAccessor>::MoveLast"
  - "CRowset<TAccessor>::MoveLast"
  - "ATL.CRowset.MoveLast"
  - "ATL::CRowset::MoveLast"
  - "CRowset<TAccessor>.MoveLast"
  - "MoveLast"
  - "CRowset::MoveLast"
  - "ATL.CRowset<TAccessor>.MoveLast"
  - "CRowset.MoveLast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveLast メソッド"
ms.assetid: 81063578-ae9d-467b-8c88-81d8fc66e020
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::MoveLast
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

最後の行にカーソルを移動します。  
  
## 構文  
  
```  
  
HRESULT MoveLast( ) throw( );  
  
```  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) を最後の位置に次フェッチ場所の位置を変更するために呼び出す、最後の行を取得します。  
  
 このメソッドは `VARIANT_TRUE` に行セットを含むテーブルまたはコマンドの **開く** を呼び出す前に **DBPROP\_CANSCROLLBACKWARDS** を設定する必要があります。\(パフォーマンス、でも `VARIANT_TRUE`に **DBPROP\_QUICKRESTART** を設定する必要があります\)。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)