---
title: "CDynamicParameterAccessor::GetParamString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor.GetParamString"
  - "GetParamString"
  - "CDynamicParameterAccessor::GetParamString"
  - "ATL.CDynamicParameterAccessor.GetParamString"
  - "ATL::CDynamicParameterAccessor::GetParamString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamString メソッド"
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDynamicParameterAccessor::GetParamString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バッファーに格納され、指定したパラメーターの文字列データを取得します。  
  
## 構文  
  
```  
  
      bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringA& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringW& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   WCHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
```  
  
#### パラメーター  
 `nParam`  
 \[\]パラメーター数 \(1\) からのオフセット。  パラメーターは 0 戻り値のために予約されています。  パラメーターの数は、SQL またはストアド プロシージャ呼び出しの順序に基づいてパラメーターのインデックスです。  例については、" [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) を参照してください。  
  
 `strOutput`  
 \[\]**CSimpleStringA** \(ANSI\) または指定されたパラメーターの Unicode \(**CSimpleStringW**\) 文字列データ。  `CString`型のパラメーターを渡す必要があります \(例:  
  
 [!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/CPP/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
 `pBuffer`  
 \[\]**CHAR** \(ANSI\) または指定されたパラメーターの Unicode \(**WCHAR**\) 文字列データへのポインター。  
  
 `pMaxLen`  
 \[\] `pBuffer` によって指し示されたバッファーのサイズへのポインター \(終端の null 文字を含む\)。  
  
## 解説  
 成功の戻り **true** または失敗の **false**。  
  
 `pBuffer` が NULL の場合、このメソッドはデータをコピーしません `pMaxLen` とサービスの **true** 指されたをメモリに必要なバッファーのサイズを設定します。  
  
 このメソッドは、文字列全体を含めるには、バッファー `pBuffer` が十分な大きさで失敗します。  
  
 バッファーから文字列パラメーター データを取得するために `GetParamString` を使用します。  バッファーから文字列パラメーター データを取得するために [GetParam](../Topic/CDynamicParameterAccessor::GetParam.md) を使用します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)