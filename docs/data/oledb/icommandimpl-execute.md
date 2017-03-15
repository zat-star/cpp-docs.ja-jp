---
title: "ICommandImpl::Execute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandImpl::Execute"
  - "ICommandImpl.Execute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Execute メソッド"
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ICommandImpl::Execute
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンドを実行します。  
  
## 構文  
  
```  
  
      HRESULT Execute(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset   
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) を参照してください。  
  
## 解説  
 要求されたアウトゴーイング インターフェイスはこの関数を作成するには、行セット オブジェクトから取得したインターフェイスです。  
  
 **実行** の 呼び出し [CreateRowset](../Topic/ICommandImpl::CreateRowset.md)。  複数の行セットを作成したり、さまざまな行セットを作成するための独自の条件を指定するための既定の実装をオーバーライドします。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [ICommandImpl クラス](../Topic/ICommandImpl%20Class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)