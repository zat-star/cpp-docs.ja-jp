---
title: "AsyncBase::OnClose メソッド | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::OnClose"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnClose メソッド"
ms.assetid: 96766450-c262-4611-8534-7d190b799142
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::OnClose メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

派生クラスでオーバーライドされた場合、非同期操作を閉じます。  
  
## 構文  
  
```  
virtual void OnClose(  
   void  
) = 0;  
```  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)   
 [AsyncBase::Close メソッド](../windows/asyncbase-close-method.md)