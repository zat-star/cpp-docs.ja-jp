---
title: "CRowset::UpdateAll | Microsoft Docs"
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
  - "CRowset::UpdateAll"
  - "ATL.CRowset.UpdateAll"
  - "CRowset<TAccessor>.UpdateAll"
  - "ATL.CRowset<TAccessor>.UpdateAll"
  - "UpdateAll"
  - "CRowset.UpdateAll"
  - "ATL::CRowset<TAccessor>::UpdateAll"
  - "CRowset<TAccessor>::UpdateAll"
  - "ATL::CRowset::UpdateAll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UpdateAll メソッド"
ms.assetid: e5b26c0a-40fc-4c91-a293-5084951788e6
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::UpdateAll
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

そのため **更新** の最後のフェッチまたは呼び出し以降に行われたすべての行に対する保留中の変更を転送します。  
  
## 構文  
  
```  
  
      HRESULT UpdateAll(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW** pphRow = NULL,   
   DBROWSTATUS** ppStatus = NULL    
) throw( );  
```  
  
#### パラメーター  
 `pcRows`  
 \[\] `UpdateAll` を更新するようにとした行数を返す場所へのポインターが必要な場合。  
  
 `pphRow`  
 \[\] `UpdateAll` が行ハンドルを返す、メモリへのポインターを更新するようにしようとしました。  ハンドルは `pphRow` が NULL の場合は返されません。  
  
 `ppStatus`  
 \[\] **更新** が行の値を返す場所へのポインター。  状態は `ppStatus` が NULL の場合は返されません。  
  
## 解説  
 これらの行が [更新](../Topic/CRowset::Update.md) または `UpdateAll`を使用して、最後にフェッチされるか、更新されたため、すべての行に対する保留中の変更を転送します。  `UpdateAll` は まだの \(`pphRow`を参照してください\)、ハンドルがあるかどうかを変更した行に関係なく更新します。  
  
 たとえば、行セットの 5 行を挿入するために **挿入** を使用して 5 回 **更新** を呼び出し、またはすべてを更新するに `UpdateAll` を一度呼び出すことができます。  
  
 このメソッドは、すべてのプロバイダーでサポートされない省略可能なインターフェイス `IRowsetUpdate`が必要ですが、; この場合、メソッドの戻り **E\_NOINTERFACE**。  また `VARIANT_TRUE` にテーブルの **開く** を呼び出す前に **DBPROP\_IRowsetUpdate** を設定または命じなければ、行セットが含まれます。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)   
 [CRowset::Update](../Topic/CRowset::Update.md)