---
title: "CAccessorBase::GetHAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetHAccessor"
  - "CAccessorBase::GetHAccessor"
  - "CAccessorBase.GetHAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetHAccessor メソッド"
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessorBase::GetHAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定アクセサーのアクセサー ハンドルを取得します。  
  
## 構文  
  
```  
  
      HACCESSOR GetHAccessor(  
   ULONG nAccessor   
) const;  
```  
  
#### パラメーター  
 `nAccessor`  
 \[\]アクセサーのゼロの数。  
  
## 戻り値  
 アクセサーのハンドル。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CAccessorBase クラス](../../data/oledb/caccessorbase-class.md)