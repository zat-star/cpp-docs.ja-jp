---
title: "CriticalSection::Lock メソッド | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock メソッド"
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSection::Lock メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定クリティカル セクション オブジェクトの所有権のを待ちます。  呼び出し元スレッドが所有権を付与されたときに、関数の戻り値。  
  
## 構文  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### パラメーター  
 `cs`  
 ユーザー指定のクリティカル セクション オブジェクト。  
  
## 戻り値  
 現在のクリティカル セクションのロックを解除するために使用できるロック オブジェクト。  
  
## 解説  
 **Lock** の最初の関数は、現在のクリティカル セクション オブジェクトに影響します。  **Lock** の 2 番目の関数は、ユーザーが指定したクリティカル セクションに影響します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [CriticalSection クラス](../Topic/CriticalSection%20Class.md)