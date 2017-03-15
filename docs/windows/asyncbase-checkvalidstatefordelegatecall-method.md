---
title: "AsyncBase::CheckValidStateForDelegateCall メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CheckValidStateForDelegateCall メソッド"
ms.assetid: d997ebe7-2378-4e74-a379-f0f85e6922f0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::CheckValidStateForDelegateCall メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

デリゲートのプロパティが現在の非同期状態で変更できるかどうかをテストします。  
  
## 構文  
  
```  
inline HRESULT CheckValidStateForDelegateCall();  
```  
  
## 戻り値  
 デリゲートのプロパティを変更する場合は、S\_OK; それ以外の場合は E\_ILLEGAL\_METHOD\_CALL。  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)