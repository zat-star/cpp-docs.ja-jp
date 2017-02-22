---
title: "CDynamicParameterAccessor:GetParamType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor.GetParamType"
  - "CDynamicParameterAccessor:GetParamType"
  - "CDynamicParameterAccessor::GetParamType"
  - "ATL.CDynamicParameterAccessor.GetParamType"
  - "GetParamType"
  - "ATL::CDynamicParameterAccessor::GetParamType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamType メソッド"
ms.assetid: d9c46775-c2a6-4100-8b69-99f13c52958b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor:GetParamType
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定したパラメーターのデータ型を取得します。  
  
## 構文  
  
```  
  
      bool GetParamType(  
   DBORDINAL nParam,  
   DBTYPE* pType   
) const throw( );  
```  
  
#### パラメーター  
 `nParam`  
 \[\]パラメーター数 \(1\) からのオフセット。  パラメーターは 0 戻り値のために予約されています。  パラメーターの数は、SQL またはストアド プロシージャ呼び出しの順序に基づいてパラメーターのインデックスです。  例については、" [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) を参照してください。  
  
 `pType`  
 \[\]を含む変数へのポインター。指定したパラメーターのデータ型。  
  
## 戻り値  
 成功の戻り **true** または失敗の **false**。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)