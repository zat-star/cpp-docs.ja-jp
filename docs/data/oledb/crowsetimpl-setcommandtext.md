---
title: "CRowsetImpl::SetCommandText | Microsoft Docs"
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
  - "CRowsetImpl.SetCommandText"
  - "CRowsetImpl::SetCommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetCommandText メソッド"
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::SetCommandText
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2 桁の文字列に **DBID**s を検証し、保存します。[m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) と [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)\)。  
  
## 構文  
  
```  
  
      HRESULT CRowsetBaseImpl::SetCommandText(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### パラメーター  
 `pTableID`  
 \[\]テーブルを表す **DBID** ID へのポインター。  
  
 `pIndexID`  
 \[\]インデックスを表す **DBID** ID へのポインター。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 **SetCommentText** のメソッドは `CreateRowset`のテンプレート化されます `IOpenRowsetImpl`の静的メソッドによって呼び出されます。  
  
 このメソッドは upcasted ポインターを通じて [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) と [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) を呼び出して、タスクに委任します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)