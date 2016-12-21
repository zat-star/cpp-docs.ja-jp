---
title: "AsyncBase::put_Id メソッド | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::put_Id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "put_Id メソッド"
ms.assetid: aebad85f-4774-42de-b625-a9cf5f65cb4e
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::put_Id メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

非同期操作のハンドルを設定します。  
  
## 構文  
  
```  
STDMETHOD(  
   put_Id  
)(const unsigned int id);  
```  
  
#### パラメーター  
 `id`  
 0 以外のなハンドル。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は E\_ILLEGAL\_METHOD\_CALL E\_INVALIDARG か。  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)