---
title: "ICommandTextImpl::GetCommandText | Microsoft Docs"
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
  - "GetCommandText"
  - "ICommandTextImpl.GetCommandText"
  - "ICommandTextImpl::GetCommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCommandText メソッド"
ms.assetid: 0f8da470-b1c3-4573-974f-1acc111e3984
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandTextImpl::GetCommandText
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

最後のオーダーによって設定された [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)にテキスト コマンドを返します。  
  
## 構文  
  
```  
  
      STDMETHOD(GetCommandText)(   
   GUID * pguidDialect,   
   LPOLESTR * ppwszCommand    
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) を参照してください。  *pguidDialect* パラメーターは既定では無視されます。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [ICommandTextImpl クラス](../../data/oledb/icommandtextimpl-class.md)