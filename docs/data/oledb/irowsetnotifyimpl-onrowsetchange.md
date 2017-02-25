---
title: "IRowsetNotifyImpl::OnRowsetChange | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnRowsetChange"
  - "IRowsetNotifyImpl::OnRowsetChange"
  - "IRowsetNotifyImpl.OnRowsetChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnRowsetChange メソッド"
ms.assetid: 5125b0c8-f175-4ee6-befa-8df2c904d5e0
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# IRowsetNotifyImpl::OnRowsetChange
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行セット全体に影響のある変更をコンシューマーに通知します。  
  
## 構文  
  
```  
  
   STDMETHOD(OnRowsetChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### パラメーター  
 パラメーターの説明 [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) を参照してください。  
  
## 戻り値  
 戻り値の説明の [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) を参照してください。  
  
## 解説  
 このメソッドは [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) のメソッドをラップします。  詳細については、OLE DB Programmer's Reference のそのメソッドの説明を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [IRowsetNotifyImpl クラス](../Topic/IRowsetNotifyImpl%20Class.md)   
 [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx)