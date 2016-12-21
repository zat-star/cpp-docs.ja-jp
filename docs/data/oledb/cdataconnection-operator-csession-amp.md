---
title: "CDataConnection::operator CSession&amp; | Microsoft Docs"
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
  - "CSession&"
  - "CDataConnection::operatorCSession&"
  - "CDataConnection.operatorCSession&"
  - "operatorCSession&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession& 演算子"
  - "演算子 CSession&"
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CSession&amp;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CSession` に含まれるオブジェクトへの参照を返します。  
  
## 構文  
  
```  
  
operator const CSession&();  
  
```  
  
## 解説  
 この演算子は `CSession` に含まれるオブジェクトへの参照を取得し、`CSession` の参照を取得する `CDataConnection` オブジェクトを渡すことができます。  
  
## 使用例  
 関数がある場合 `CSession` の参照を取得する \(次 `func` など\)、`CDataConnection` オブジェクトを渡すために **CSession&** を使用できます。  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/CPP/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/CPP/cdataconnection-operator-csession-amp_2.cpp)]  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession\*](../../data/oledb/cdataconnection-operator-csession-star.md)