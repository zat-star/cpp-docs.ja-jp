---
title: "MakeAllocator クラス | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::MakeAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MakeAllocator クラス"
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MakeAllocator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,   
   T)> , T)> class MakeAllocator;  
  
template<  
   typename T  
>  
class MakeAllocator<T, false>;  
  
template<  
   typename T  
>  
class MakeAllocator<T, true>;  
```  
  
#### パラメーター  
 `T`  
 型の名前。  
  
 `hasWeakReferenceSupport`  
 弱い参照をサポートするオブジェクトにメモリを割り当てる`true` ; 弱い参照をサポートしないオブジェクトにメモリを割り当てる `false`。  
  
## 解説  
 弱い参照サポートの有無に関係なくアクティブ化可能クラスの、メモリを割り当てます。  
  
 ユーザー定義のメモリ割り当てモデルを実装するに MakeAllocator クラスをオーバーライドします。  
  
 オブジェクトが構築中にスローすれば MakeAllocator は、メモリ リークを防ぐために使用します。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[MakeAllocator::MakeAllocator コンストラクター](../windows/makeallocator-makeallocator-constructor.md)|MakeAllocator クラスの新しいインスタンスを初期化します。|  
|[MakeAllocator::~MakeAllocator デストラクター](../Topic/MakeAllocator::~MakeAllocator%20Destructor.md)|Deinitializes MakeAllocator クラスの現在のインスタンス。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[MakeAllocator::Allocate メソッド](../Topic/MakeAllocator::Allocate%20Method.md)|メモリと関連 MakeAllocator を現在のオブジェクトに割り当てます。|  
|[MakeAllocator::Detach メソッド](../windows/makeallocator-detach-method.md)|MakeAllocator の現在のオブジェクトの [割り当てます。](../Topic/MakeAllocator::Allocate%20Method.md) のメソッドによって割り当てられたメモリの関連付けを解除し。|  
  
## 継承階層  
 `MakeAllocator`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)