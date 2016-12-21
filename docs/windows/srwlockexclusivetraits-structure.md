---
title: "SRWLockExclusiveTraits 構造体 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLockExclusiveTraits 構造体"
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLockExclusiveTraits 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

排他ロック モードで SRWLock クラスのような共通の特性について説明します。  
  
## 構文  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`Type`|[SRWLOCK](../windows/srwlock-class.md) クラスへのポインターのシノニムです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[SRWLockExclusiveTraits::GetInvalidValue メソッド](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|常に無効である SRWLockExclusiveTraits オブジェクトを取得します。|  
|[SRWLockExclusiveTraits::Unlock メソッド](../windows/srwlockexclusivetraits-unlock-method.md)|SRWLock オブジェクトのリリース排他制御。|  
  
## 継承階層  
 `SRWLockExclusiveTraits`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 参照  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)