---
title: "AsyncStatusInternal 列挙型 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::Details::AsyncStatusInternal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncStatusInternal 列挙型"
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# AsyncStatusInternal 列挙型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
enum AsyncStatusInternal;  
```  
  
## 解説  
 非同期操作の状態の内部列挙体と **Windows::Foundation::AsyncStatus** の列挙体間のマッピングを指定します。  
  
## メンバー  
 `_Created`  
 ::Windows::Foundation::AsyncStatus::Created への等価  
  
 `_Started`  
 ::Windows::Foundation::AsyncStatus::Started への等価  
  
 `_Completed`  
 ::Windows::Foundation::AsyncStatus::Completed への等価  
  
 `_Cancelled`  
 ::Windows::Foundation::AsyncStatus::Cancelled への等価  
  
 `_Error`  
 ::Windows::Foundation::AsyncStatus::Error への等価  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)