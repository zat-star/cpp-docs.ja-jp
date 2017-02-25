---
title: "CDataConnection::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataConnection.Open"
  - "ATL.CDataConnection.Open"
  - "CDataConnection::Open"
  - "ATL::CDataConnection::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open メソッド"
ms.assetid: 2c6f0c01-4954-43ba-973e-861ac8e82892
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataConnection::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

初期化文字列を使用してデータ ソースへの接続を開きます。  
  
## 構文  
  
```  
  
      HRESULT Open(   
   LPCOLESTR szInitString    
) throw( );  
```  
  
#### パラメーター  
 *szInitString*  
 \[\]データ ソースの初期化文字列。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)