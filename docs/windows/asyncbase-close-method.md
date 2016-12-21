---
title: "AsyncBase::Close メソッド | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close メソッド"
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::Close メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

非同期操作を閉じます。  
  
## 構文  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## 戻り値  
 操作が終了すると、終了、または S\_OK; それ以外の場合は E\_ILLEGAL\_STATE\_CHANGE。  
  
## 解説  
 Close\(\) は IAsyncInfo::Close の既定の実装では、実際の作業を行いません。  実際には、非同期操作を閉じるために、OnClose\(\) の純粋仮想メソッドをオーバーライドします。  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)