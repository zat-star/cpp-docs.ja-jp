---
title: "WeakRef::WeakRef コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef::WeakRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakRef、コンストラクター"
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# WeakRef::WeakRef コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WeakRef クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```  
WeakRef();  
WeakRef(  
   decltype(__nullptr)  
);  
  
WeakRef(  
   _In_opt_ IWeakReference* ptr  
);  
  
WeakRef(  
   const ComPtr<IWeakReference>& ptr  
);  
  
WeakRef(  
   const WeakRef& ptr  
);  
  
WeakRef(  
   _Inout_ WeakRef&& ptr  
);  
```  
  
#### パラメーター  
 `ptr`  
 WeakRef の現在のオブジェクトを初期化する既存のオブジェクトへのポインター、参照、rvalue 参照。  
  
## 解説  
 最初のコンストラクターは、空の WeakRef オブジェクトを初期化します。  2 番目のコンストラクターは、ポインターの IWeakReference インターフェイスへの WeakRef オブジェクトを初期化します。  3 番目のコンストラクターは、参照の IWeakReference ComPtr\< オブジェクトへの WeakRef オブジェクトを\> 初期化します。  4 つ目と 5 つ目のコンストラクターは WeakRef の別のオブジェクトの WeakRef オブジェクトを初期化します。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [WeakRef クラス](../windows/weakref-class.md)