---
title: "CDynamicParameterAccessor::SetParamString | Microsoft Docs"
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
  - "ATL.CDynamicParameterAccessor.SetParamString"
  - "ATL::CDynamicParameterAccessor::SetParamString"
  - "SetParamString"
  - "CDynamicParameterAccessor::SetParamString"
  - "CDynamicParameterAccessor.SetParamString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamString メソッド"
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::SetParamString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バッファーに格納され、指定したパラメーターの文字列データを設定します。  
  
## 構文  
  
```  
  
      bool SetParamString(   
   DBORDINAL nParam,   
   const CHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
bool SetParamString(   
   DBORDINAL nParam,   
   const WCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
```  
  
#### パラメーター  
 `nParam`  
 \[\]パラメーター数 \(1\) からのオフセット。  パラメーターは 0 戻り値のために予約されています。  パラメーターの数は、SQL またはストアド プロシージャ呼び出しの順序に基づいてパラメーターのインデックスです。  例については、" [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) を参照してください。  
  
 `pString`  
 \[\]**CHAR** \(ANSI\) または指定されたパラメーターの Unicode \(**WCHAR**\) 文字列データへのポインター。  oledb.h の `DBSTATUS` を参照してください。  
  
 *status*  
 \[\]指定されたパラメーターの `DBSTATUS` の状態。  `DBSTATUS` 値の詳細については、*OLE DB Programmer's Reference*の [状態](https://msdn.microsoft.com/en-us/library/ms722617.aspx) を参照するか、oledb.h の `DBSTATUS` を検索します。  
  
## 解説  
 成功の戻り **true** または失敗の **false**。  
  
 `SetParamString` は `pString`に指定する最大サイズを超える文字列を設定しようとすると失敗します。  
  
 バッファーの文字列パラメーター データを設定するために `SetParamString` を使用します。  バッファー パラメーターにもデータを設定するために [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) を使用します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)