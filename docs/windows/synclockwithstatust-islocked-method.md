---
title: "SyncLockWithStatusT::IsLocked メソッド | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsLocked メソッド"
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockWithStatusT::IsLocked メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
bool IsLocked() const;  
```  
  
## 解説  
 SyncLockWithStatusT の現在のオブジェクトがリソースを所有するかどうかを示します; つまり、SyncLockWithStatusT オブジェクトは *ロックされます*。  
  
## 戻り値  
 SyncLockWithStatusT オブジェクトがロックされて**true** ; それ以外の場合は **false**。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::Details  
  
## 参照  
 [SyncLockWithStatusT クラス](../windows/synclockwithstatust-class.md)