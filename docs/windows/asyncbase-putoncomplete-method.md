---
title: "AsyncBase::PutOnComplete メソッド | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::PutOnComplete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PutOnComplete メソッド"
ms.assetid: 1c469ff9-b2df-4637-bf05-01a617043149
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::PutOnComplete メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定された値に完了するイベント ハンドラーのアドレスを設定します。  
  
## 構文  
  
```  
STDMETHOD(  
   PutOnComplete  
)(TComplete* completeHandler);  
```  
  
#### パラメーター  
 `completeHandler`  
 完了のイベント ハンドラーを設定するアドレス。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は E\_ILLEGAL\_METHOD\_CALL。  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)