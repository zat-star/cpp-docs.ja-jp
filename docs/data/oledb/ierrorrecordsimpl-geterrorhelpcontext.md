---
title: "IErrorRecordsImpl::GetErrorHelpContext | Microsoft Docs"
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
  - "GetErrorHelpContext"
  - "IErrorRecordsImpl::GetErrorHelpContext"
  - "IErrorRecordsImpl.GetErrorHelpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorHelpContext メソッド"
ms.assetid: 53d70239-0d64-482e-9ad4-4e1f4f02d5a3
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IErrorRecordsImpl::GetErrorHelpContext
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エラー レコードからヘルプ コンテキスト ID を取得します。  
  
## 構文  
  
```  
  
      DWORD GetErrorHelpContext(  
   ERRORINFO& rCurError   
);  
```  
  
#### パラメーター  
 `rCurError`  
 **IErrorInfo** インターフェイスの `ERRORINFO` レコード。  
  
## 戻り値  
 エラーのヘルプ コンテキスト ID。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IErrorRecordsImpl クラス](../../data/oledb/ierrorrecordsimpl-class.md)