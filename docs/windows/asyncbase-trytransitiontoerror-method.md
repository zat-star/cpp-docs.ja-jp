---
title: "AsyncBase::TryTransitionToError メソッド | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::TryTransitionToError"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryTransitionToError メソッド"
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::TryTransitionToError メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したエラー コードが内部エラーの状態を変更できるかどうかを示します。  
  
## 構文  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### パラメーター  
 `error`  
 エラー HRESULT。  
  
## 戻り値  
 内部エラーの状態が変更された場合`true` ; それ以外の場合は `false`。  
  
## 解説  
 この操作は、エラー状態が S\_OK に既に設定されている場合にのみ、エラー状態を変更します。  この操作は、エラー状態が既にエラーな場合は、取り消し、完了したか、および終了しません。  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)