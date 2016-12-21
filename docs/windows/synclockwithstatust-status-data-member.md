---
title: "SyncLockWithStatusT::status_ データ メンバー | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "status_ データ メンバー"
ms.assetid: 466fa336-b5ff-4d43-8efd-1e87e5fddf88
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockWithStatusT::status_ データ メンバー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
DWORD status_;  
```  
  
## 解説  
 SyncLockWithStatusT の現在のオブジェクトに基づいてオブジェクトのロック操作の後に、基になる待機操作の結果を格納します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::Details  
  
## 参照  
 [SyncLockWithStatusT クラス](../windows/synclockwithstatust-class.md)