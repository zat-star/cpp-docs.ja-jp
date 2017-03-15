---
title: "AsyncBase::get_Id メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::get_Id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_Id メソッド"
ms.assetid: 591d8366-ea76-4deb-9278-9d3bc394a42b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::get_Id メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

非同期操作のハンドルを取得します。  
  
## 構文  
  
```  
STDMETHOD(  
   get_Id  
)(unsigned int *id) override;  
```  
  
#### パラメーター  
 `id`  
 ハンドルが格納される場所。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は E\_ILLEGAL\_METHOD\_CALL。  
  
## 解説  
 このメソッドは IAsyncInfo::get\_Id を実装します。  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)