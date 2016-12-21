---
title: "SRWLockExclusiveTraits::Unlock メソッド | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock メソッド"
ms.assetid: 7fd6b0fb-8b88-4a43-aa74-0d7fe47a0da6
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLockExclusiveTraits::Unlock メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

SRWLock オブジェクトのリリース排他制御。  
  
## 構文  
  
```  
inline static void Unlock(  
   _In_ Type srwlock  
);  
```  
  
#### パラメーター  
 `srwlock`  
 SRWLock オブジェクトへのハンドル。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 参照  
 [SRWLockExclusiveTraits 構造体](../windows/srwlockexclusivetraits-structure.md)