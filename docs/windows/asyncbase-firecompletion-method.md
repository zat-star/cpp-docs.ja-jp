---
title: "AsyncBase::FireCompletion メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::FireCompletion"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FireCompletion メソッド"
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::FireCompletion メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

完了したイベント ハンドラーを呼び出すか、内部進行状況のデリゲートをリセットします。  
  
## 構文  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## 解説  
 FireCompletion\(\) の最初のバージョンは、進行状況のデリゲートの変数をリセットします。  2 番目のバージョンは、非同期操作が完了すると完了のイベント ハンドラーが呼び出されます。  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)