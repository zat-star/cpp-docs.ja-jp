---
title: "SyncLockT::~SyncLockT デストラクター | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~ SyncLockT、デストラクター"
ms.assetid: 9e14870d-017d-45fe-a3dc-cd86b6fa1c3a
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockT::~SyncLockT デストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
~SyncLockT();  
```  
  
## 解説  
 Deinitializes SyncLockT クラスのインスタンス。  
  
 このデストラクターは、SyncLockT の現在のインスタンスのロックを解除します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::Details  
  
## 参照  
 [SyncLockT クラス](../windows/synclockt-class.md)