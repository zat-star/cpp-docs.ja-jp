---
title: "CRowset::Undo | Microsoft Docs"
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
  - "CRowset.Undo"
  - "ATL::CRowset<TAccessor>::Undo"
  - "CRowset<TAccessor>::Undo"
  - "ATL.CRowset.Undo"
  - "ATL.CRowset<TAccessor>.Undo"
  - "CRowset<TAccessor>.Undo"
  - "ATL::CRowset::Undo"
  - "CRowset::Undo"
  - "Undo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Undo メソッド"
ms.assetid: 1ccd70e2-3931-41c4-893e-a05d0e295410
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::Undo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

変更された行への変更は、最後のフェッチまたは [更新](../Topic/CRowset::Update.md)元に戻します。  
  
## 構文  
  
```  
  
      HRESULT Undo(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### パラメーター  
 `pcRows`  
 \[\] **元に戻す** が列番号が返す場所へのポインターを必要に応じて元しようとしました。  
  
 `phRow`  
 \[\] **元に戻す** がすべての行ハンドルの配列が返す場所へのポインターを必要に応じて元しようとしました。  
  
 `pStatus`  
 \[\] **元に戻す** が行の値を返す場所へのポインター。  状態は `pStatus` が NULL の場合は返されません。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 このメソッドは、すべてのプロバイダーでサポートされない省略可能なインターフェイス `IRowsetUpdate`が必要ですが、; この場合、メソッドの戻り **E\_NOINTERFACE**。  また `VARIANT_TRUE` にテーブルの **開く** を呼び出す前に **DBPROP\_IRowsetUpdate** を設定または命じなければ、行セットが含まれます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)   
 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)