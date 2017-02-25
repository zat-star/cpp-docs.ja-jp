---
title: "IErrorRecordsImpl::GetErrorHelpFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorRecordsImpl::GetErrorHelpFile"
  - "GetErrorHelpFile"
  - "IErrorRecordsImpl.GetErrorHelpFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorHelpFile メソッド"
ms.assetid: ad198f76-5bdf-4b8d-9f1a-3d38f72f31ad
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IErrorRecordsImpl::GetErrorHelpFile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エラー レコードからヘルプ ファイルのパス名を取得します。  
  
## 構文  
  
```  
  
      LPOLESTR GetErrorHelpFile(  
   ERRORINFO& rCurError   
);  
```  
  
#### パラメーター  
 `rCurError`  
 **IErrorInfo** インターフェイスの `ERRORINFO` レコード。  
  
## 戻り値  
 エラーのヘルプ ファイルのパス名を含む文字列へのポインター。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IErrorRecordsImpl クラス](../../data/oledb/ierrorrecordsimpl-class.md)