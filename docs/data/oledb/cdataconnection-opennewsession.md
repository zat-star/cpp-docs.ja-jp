---
title: "CDataConnection::OpenNewSession | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataConnection.OpenNewSession"
  - "ATL.CDataConnection.OpenNewSession"
  - "ATL::CDataConnection::OpenNewSession"
  - "OpenNewSession"
  - "CDataConnection::OpenNewSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenNewSession メソッド"
ms.assetid: 0a70e573-9498-4ca7-b524-45666dc7b0a3
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataConnection::OpenNewSession
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在の接続オブジェクト データ ソースを使用して新しいセッションが開きます。  
  
## 構文  
  
```  
  
      HRESULT OpenNewSession(   
   CSession & session    
) throw( );  
```  
  
#### パラメーター  
 `session`  
 \[\]その新しいセッション オブジェクトへの参照。  
  
 **解説**  
 新しいセッションが親として現在の接続オブジェクトに含まれているデータ ソース オブジェクトを使用してデータ ソースと同じ情報すべてにアクセスできます。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)