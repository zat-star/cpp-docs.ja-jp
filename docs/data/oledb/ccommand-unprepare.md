---
title: "CCommand::Unprepare | Microsoft Docs"
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
  - "Unprepare"
  - "CCommand.Unprepare"
  - "CCommand::Unprepare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unprepare メソッド"
ms.assetid: 4fe59988-fe51-4c7c-a156-72b68e3d642b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::Unprepare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のコマンド実行の計画を破棄します。  
  
## 構文  
  
```  
  
HRESULT CCommandBase::Unprepare( ) throw( );  
  
```  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 このメソッドは、OLE DB の [ICommandPrepare::Unprepare](https://msdn.microsoft.com/en-us/library/ms719635.aspx)メソッドをラップします。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CCommand クラス](../../data/oledb/ccommand-class.md)