---
title: "SRWLockSharedTraits 構造体 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLockSharedTraits 構造体"
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLockSharedTraits 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

共有ロック モードで SRWLock クラスのような共通の特性について説明します。  
  
## 構文  
  
```  
struct SRWLockSharedTraits;  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`Type`|[SRWLOCK](../windows/srwlock-class.md) クラスへのポインターのシノニムです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[SRWLockSharedTraits::GetInvalidValue メソッド](../Topic/SRWLockSharedTraits::GetInvalidValue%20Method.md)|常に無効である SRWLockSharedTraits オブジェクトを取得します。|  
|[SRWLockSharedTraits::Unlock メソッド](../Topic/SRWLockSharedTraits::Unlock%20Method.md)|SRWLock オブジェクトのリリース排他制御。|  
  
## 継承階層  
 `SRWLockSharedTraits`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 参照  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)