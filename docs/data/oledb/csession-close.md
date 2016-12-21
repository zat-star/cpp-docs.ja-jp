---
title: "CSession::Close | Microsoft Docs"
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
  - "CSession::Close"
  - "ATL.CSession.Close"
  - "CSession.Close"
  - "ATL::CSession::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close メソッド"
ms.assetid: dc36c4c0-e588-4c0b-91d1-fc7dc5c8e7f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSession::Close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CSession::Open](../../data/oledb/csession-open.md)で開かれたセッションを終了します。  
  
## 構文  
  
```  
  
void Close( ) throw( );  
  
```  
  
## 解説  
 **m\_spOpenRowset** のポインターを解放します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CSession クラス](../../data/oledb/csession-class.md)