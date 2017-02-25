---
title: "CManualAccessor::AddBindEntry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CManualAccessor::AddBindEntry"
  - "ATL.CManualAccessor.AddBindEntry"
  - "CManualAccessor::AddBindEntry"
  - "AddBindEntry"
  - "CManualAccessor.AddBindEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddBindEntry メソッド"
ms.assetid: 8556dda9-dda1-4f67-96bc-6031e6c6a271
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CManualAccessor::AddBindEntry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

出力列にバインド エントリを追加します。  
  
## 構文  
  
```  
  
      void AddBindEntry(  
   DBORDINAL nOrdinal,  
   DBTYPE wType,  
   DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL   
) throw ( );  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) を参照してください。  
  
 `nOrdinal`  
 \[\]列番号。  
  
 `wType`  
 \[\]データ型。  
  
 `nColumnSize`  
 \[\]バイト列のサイズ。  
  
 `pData`  
 \[\]バッファーに格納された列のデータへのポインター。  
  
 `pLength`  
 \[\]フィールドの長さへのポインター \(必要な場合\)。  
  
 `pStatus`  
 \[\]列のステータスにバインドされるする変数へのポインターに必要な場合。  
  
## 解説  
 この関数を使用するには、まず、[CreateAccessor](../Topic/CManualAccessor::CreateAccessor.md)です。  `CreateAccessor`で指定される列数よりも多くのエントリを追加することはできません。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CManualAccessor クラス](../Topic/CManualAccessor%20Class.md)   
 [DBViewer のサンプル](../../top/visual-cpp-samples.md)