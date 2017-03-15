---
title: "AsyncBase::OnCancel メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::OnCancel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnCancel メソッド"
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::OnCancel メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

派生クラスでオーバーライドされた場合、キャンセル非同期操作。  
  
## 構文  
  
```  
virtual void OnCancel(  
   void  
) = 0;  
```  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)   
 [AsyncBase::Cancel メソッド](../Topic/AsyncBase::Cancel%20Method.md)