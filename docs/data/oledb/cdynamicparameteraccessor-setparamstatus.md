---
title: "CDynamicParameterAccessor::SetParamStatus | Microsoft Docs"
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
  - "CDynamicParameterAccessor::SetParamStatus"
  - "ATL.CDynamicParameterAccessor.SetParamStatus"
  - "ATL::CDynamicParameterAccessor::SetParamStatus"
  - "CDynamicParameterAccessor.SetParamStatus"
  - "SetParamStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamStatus メソッド"
ms.assetid: 0c2271f6-457d-46ca-88b7-4590aadb20d7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::SetParamStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バッファーに格納され、指定したパラメーターの状態を設定します。  
  
## 構文  
  
```  
  
      bool SetParamStatus(  
   DBORDINAL nParam,  
   DBSTATUS status  
);  
```  
  
#### パラメーター  
 `nParam`  
 \[\]パラメーター数 \(1\) からのオフセット。  パラメーターは 0 戻り値のために予約されています。  パラメーターの数は、SQL またはストアド プロシージャ呼び出しの順序に基づいてパラメーターのインデックスです。  例については、" [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) を参照してください。  
  
 *status*  
 \[\]指定されたパラメーターの `DBSTATUS` の状態。  `DBSTATUS` 値の詳細については、*OLE DB Programmer's Reference*の [状態](https://msdn.microsoft.com/en-us/library/ms722617.aspx) を参照するか、oledb.h の `DBSTATUS` を検索します。  
  
## 解説  
 成功の戻り **true** または失敗の **false**。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)