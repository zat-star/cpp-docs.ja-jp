---
title: "AsyncBase::CheckValidStateForResultsCall メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CheckValidStateForResultsCall メソッド"
ms.assetid: 87ca6805-bff1-4063-b855-6dd26132deff
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::CheckValidStateForResultsCall メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

非同期操作の結果が現在の非同期状態で収集できるかどうかをテストします。  
  
## 構文  
  
```  
inline HRESULT CheckValidStateForResultsCall();  
```  
  
## 戻り値  
 結果を収集できる場合 S\_OK; それ以外の場合は E\_ILLEGAL\_METHOD\_CALLE\_ILLEGAL\_METHOD\_CALL。  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)