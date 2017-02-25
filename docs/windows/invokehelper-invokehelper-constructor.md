---
title: "InvokeHelper::InvokeHelper コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InvokeHelper、コンストラクター"
ms.assetid: 0223c574-abc3-4fc0-99e6-38626ba79243
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InvokeHelper::InvokeHelper コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
explicit InvokeHelper(  
   TCallback callback  
);  
```  
  
#### パラメーター  
 `callback`  
 イベント ハンドラー。  
  
## 解説  
 InvokeHelper クラスの新しいインスタンスを初期化します。  
  
 `TCallback` テンプレート パラメーターはイベント ハンドラーの型を指定します。  
  
## 必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [InvokeHelper 構造体](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)