---
title: "SRWLock::TryLockShared メソッド | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLockShared メソッド"
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLock::TryLockShared メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

SRWLock の現在のディレクトリまたは指定オブジェクトの共有モードの SRWLock オブジェクトを取得しようとします。  
  
## 構文  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### パラメーター  
 `lock`  
 SRWLock オブジェクトへのポインター。  
  
## 戻り値  
 成功すると、共有モードの SRWLock オブジェクトと呼び出し元のスレッドは、ロックの所有権を取得します。  それ以外の場合は、状態が無効である SRWLock オブジェクト。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [SRWLock クラス](../windows/srwlock-class.md)