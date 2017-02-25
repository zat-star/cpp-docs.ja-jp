---
title: "CAccessorBase::IsAutoAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IsAutoAccessor"
  - "CAccessorBase.IsAutoAccessor"
  - "CAccessorBase::IsAutoAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsAutoAccessor メソッド"
ms.assetid: c330da15-2947-4050-ad00-8f776adc58fb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CAccessorBase::IsAutoAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データの移動操作中にアクセサーを自動的に取得されれば、true を返します。  
  
## 構文  
  
```  
  
      bool IsAutoAccessor(  
   ULONG nAccessor   
) const;  
```  
  
#### パラメーター  
 `nAccessor`  
 \[\]アクセサーのゼロの数。  
  
## 戻り値  
 アクセサー番号の場合 **true** を返します。  それ以外の場合は **false** を返します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CAccessorBase クラス](../../data/oledb/caccessorbase-class.md)