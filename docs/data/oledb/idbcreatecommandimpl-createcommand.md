---
title: "IDBCreateCommandImpl::CreateCommand | Microsoft Docs"
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
  - "IDBCreateCommandImpl.CreateCommand"
  - "CreateCommand"
  - "IDBCreateCommandImpl::CreateCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateCommand メソッド"
ms.assetid: 50ffbf8b-2c07-4bcb-96c5-ffce4519c7f7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBCreateCommandImpl::CreateCommand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

新しいコマンドを作成し、要求されたインターフェイスを返します。  
  
## 構文  
  
```  
  
      STDMETHOD(CreateCommand)(   
   IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand    
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [IDBCreateCommand::CreateCommand](https://msdn.microsoft.com/en-us/library/ms709772.aspx) を参照してください。  
  
 一部のパラメーターは **IDBCreateCommand::CreateCommand**で説明されている異なる名前で *OLE DB の Programmer's Reference* パラメーターに対応します:  
  
|OLE DB テンプレート パラメーター|*OLE DB の Programmer's Reference* パラメーター|  
|--------------------------|----------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IDBCreateCommandImpl クラス](../../data/oledb/idbcreatecommandimpl-class.md)