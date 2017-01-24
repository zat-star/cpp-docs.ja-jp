---
title: "AsyncBase::Start メソッド | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start メソッド"
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::Start メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

非同期操作を開始できます。  
  
## 構文  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## 戻り値  
 操作を開始したり、既に開始している場合は S\_OK; それ以外の場合は E\_ILLEGAL\_STATE\_CHANGE。  
  
## 解説  
 Start\(\) は IAsyncInfo::Start の既定の実装では、実際の作業を行いません。  実際には、非同期操作を開始するには、OnStart\(\) の純粋仮想メソッドをオーバーライドします。  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)