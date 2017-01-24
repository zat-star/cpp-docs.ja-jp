---
title: "CAccessorRowset::Bind | Microsoft Docs"
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
  - "CAccessorRowset.Bind"
  - "CAccessorRowset::Bind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bind メソッド"
ms.assetid: 42a1fc86-f570-4e54-9b82-7f7141564214
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessorRowset::Bind
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CCommand::Open](../../data/oledb/ccommand-open.md)で false として **bBind** を指定した場合は、バインディングを作成します。  
  
## 構文  
  
```  
  
HRESULT Bind( );  
  
```  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CAccessorRowset クラス](../Topic/CAccessorRowset%20Class.md)