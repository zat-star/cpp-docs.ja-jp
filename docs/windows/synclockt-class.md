---
title: "SyncLockT クラス | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockT クラス"
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockT クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### パラメーター  
 `SyncTraits`  
 リソースの所有権を取得できる型。  
  
## 解説  
 リソースの排他的または共有所有権を取得できる型を表します。  
  
 [SRWLock](../windows/srwlock-class.md) クラスの実装を支援するために SyncLockT クラスは、たとえば、使用されます。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[SyncLockT::SyncLockT コンストラクター](../Topic/SyncLockT::SyncLockT%20Constructor.md)|SyncLockT クラスの新しいインスタンスを初期化します。|  
|[SyncLockT::~SyncLockT デストラクター](../windows/synclockt-tilde-synclockt-destructor.md)|Deinitializes SyncLockT クラスのインスタンス。|  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[SyncLockT::SyncLockT コンストラクター](../Topic/SyncLockT::SyncLockT%20Constructor.md)|SyncLockT クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[SyncLockT::IsLocked メソッド](../windows/synclockt-islocked-method.md)|SyncLockT の現在のオブジェクトがリソースを所有するかどうかを示します; つまり、SyncLockT オブジェクトは *ロックされます*。|  
|[SyncLockT::Unlock メソッド](../windows/synclockt-unlock-method.md)|リソースの制御の解放は SyncLockT の現在のオブジェクトである場合、保持されます。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[SyncLockT::sync\_ データ メンバー](../Topic/SyncLockT::sync_%20Data%20Member.md)|基になるリソースを SyncLockT クラスによって表されるを保持します。|  
  
## 継承階層  
 `SyncLockT`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::Details  
  
## 参照  
 [Microsoft::WRL::Wrappers::Details 名前空間](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock クラス](../windows/srwlock-class.md)