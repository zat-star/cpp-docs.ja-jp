---
title: "Semaphore クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Semaphore クラス"
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Semaphore クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

同期オブジェクトとユーザー コントロールの限られた数をサポートできる共有リソースを表します。  
  
## 構文  
  
```  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`SyncLock`|同期ロックをサポートするクラスのシノニムです。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[Semaphore::Semaphore コンストラクター](../windows/semaphore-semaphore-constructor.md)|semaphore クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[InvokeHelper::Invoke メソッド](../windows/invokehelper-invoke-method.md)|シグネチャが引数に指定された回数を含むイベント ハンドラーが呼び出されます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[Semaphore::Lock メソッド](../windows/semaphore-lock-method.md)|現在のオブジェクトまで待機、または指定されたハンドルに関連付けられたオブジェクトがシグナル状態にあるか、指定されたタイムアウト期間が経過する。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[Semaphore::operator\= 演算子](../windows/semaphore-operator-assign-operator.md)|セマフォ オブジェクトから現在のセマフォ オブジェクトに指定されたハンドルを移動します。|  
  
## 継承階層  
 `Semaphore`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [Microsoft::WRL::Wrappers 名前空間](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)