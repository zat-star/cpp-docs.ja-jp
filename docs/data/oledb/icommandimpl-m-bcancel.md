---
title: "ICommandImpl::m_bCancel | Microsoft Docs"
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
  - "ICommandImpl::m_bCancel"
  - "ICommandImpl.m_bCancel"
  - "m_bCancel"
  - "ATL::ICommandImpl::m_bCancel"
  - "ATL.ICommandImpl.m_bCancel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bCancel"
ms.assetid: f3b6fb60-4de4-4d81-a5d2-4052c41be0de
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandImpl::m_bCancel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンドが取り消されたかどうかを示します。  
  
## 構文  
  
```  
  
unsigned m_bCancel:1;  
  
```  
  
## 解説  
 コマンド クラスの **実行** のメソッドでこの変数を取得し、必要に応じてキャンセルできます。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [ICommandImpl クラス](../Topic/ICommandImpl%20Class.md)   
 [ICommandImpl::m\_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)