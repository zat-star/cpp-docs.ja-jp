---
title: "CAccessorBase::ReleaseAccessors | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAccessorBase::ReleaseAccessors"
  - "CAccessorBase.ReleaseAccessors"
  - "ReleaseAccessors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAccessors メソッド"
ms.assetid: f08bc88e-0552-4a9c-9c65-b4061094649a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CAccessorBase::ReleaseAccessors
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

クラスによって作成されたアクセサーを解放します。  
  
## 構文  
  
```  
  
      HRESULT ReleaseAccessors(  
   IUnknown* pUnk   
);  
```  
  
#### パラメーター  
 *pUnk*  
 \[\]アクセサーが作成された COM オブジェクトの **IUnknown** インターフェイスへのポインター。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 [CAccessorRowset::Close](../Topic/CAccessorRowset::Close.md)から呼び出されます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CAccessorBase クラス](../../data/oledb/caccessorbase-class.md)