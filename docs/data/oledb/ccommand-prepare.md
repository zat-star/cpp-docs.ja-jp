---
title: "CCommand::Prepare | Microsoft Docs"
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
  - "CCommand.Prepare"
  - "CCommand::Prepare"
  - "Prepare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Prepare メソッド"
ms.assetid: f0e473fc-2f7a-4d29-96c2-1328dc21e702
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::Prepare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のコマンドを検証し、最適化します。  
  
## 構文  
  
```  
  
      HRESULT CCommandBase::Prepare(  
   ULONG cExpectedRuns = 0   
) throw( );  
```  
  
#### パラメーター  
 *cExpectedRuns*  
 \[\]、コマンドを実行すると想定する回数。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 このメソッドは、OLE DB の [ICommandPrepare::Prepare](https://msdn.microsoft.com/en-us/library/ms718370.aspx)メソッドをラップします。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CCommand クラス](../../data/oledb/ccommand-class.md)