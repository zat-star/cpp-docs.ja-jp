---
title: "ICommandImpl::GetDBSession | Microsoft Docs"
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
  - "ICommandImpl::GetDBSession"
  - "GetDBSession"
  - "ICommandImpl.GetDBSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDBSession メソッド"
ms.assetid: e5b1cb13-453f-4698-90bf-f6bfe6814a54
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandImpl::GetDBSession
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンドを作成するセッションへのインターフェイス ポインターを返します。  
  
## 構文  
  
```  
  
      STDMETHOD (GetDBSession) (  
   REFIID riid,  
   IUnknown** ppSession   
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [ICommand::GetDBSession](https://msdn.microsoft.com/en-us/library/ms719622.aspx) を参照してください。  
  
## 解説  
 セッションからプロパティを取得する場合に有効です。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [ICommandImpl クラス](../Topic/ICommandImpl%20Class.md)