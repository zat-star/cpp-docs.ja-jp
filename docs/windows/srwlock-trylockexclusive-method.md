---
title: "SRWLock::TryLockExclusive メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLockExclusive メソッド"
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SRWLock::TryLockExclusive メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

SRWLock の現在のディレクトリまたは指定オブジェクトの排他モードの SRWLock オブジェクトを取得しようとします。  呼び出しが成功した場合、呼び出し元スレッドはロックの所有権を取得します。  
  
## 構文  
  
```  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### パラメーター  
 `lock`  
 SRWLock オブジェクトへのポインター。  
  
## 戻り値  
 成功すると、排他モードの SRWLock オブジェクトと呼び出し元のスレッドは、ロックの所有権を取得します。  それ以外の場合は、状態が無効である SRWLock オブジェクト。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [SRWLock クラス](../windows/srwlock-class.md)