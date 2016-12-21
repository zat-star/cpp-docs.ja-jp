---
title: "CDataConnection::Copy | Microsoft Docs"
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
  - "CDataConnection.Copy"
  - "ATL.CDataConnection.Copy"
  - "ATL::CDataConnection::Copy"
  - "CDataConnection::Copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Copy メソッド"
ms.assetid: a3dbd70d-36be-49e0-a527-00e3910a7a56
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::Copy
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既存のデータ接続のコピーを作成します。  
  
## 構文  
  
```  
  
      CDataConnection& Copy(   
   const CDataConnection & ds    
) throw( );  
```  
  
#### パラメーター  
 `ds`  
 \[\]コピーへの既存のデータ接続への参照。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)