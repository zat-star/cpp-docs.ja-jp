---
title: "CDynamicParameterAccessor:SetParam | Microsoft Docs"
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
  - "ATL::CDynamicParameterAccessor::SetParam"
  - "ATL::CDynamicParameterAccessor::SetParam<ctype>"
  - "CDynamicParameterAccessor.SetParam"
  - "ATL.CDynamicParameterAccessor.SetParam"
  - "SetParam"
  - "CDynamicParameterAccessor:SetParam"
  - "CDynamicParameterAccessor::SetParam<ctype>"
  - "CDynamicParameterAccessor::SetParam"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParam メソッド"
ms.assetid: e2349220-545c-46ad-90da-9113ac52551a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor:SetParam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

選択した \(文字列以外のデータを使用してパラメーター バッファーを設定します。  
  
## 構文  
  
```  
  
      template < class   
      ctype >  
bool SetParam(  
   DBORDINAL nParam,  
   const ctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK  
) throw( );  
template < class ctype >  
bool SetParam(  
   TCHAR* pParamName,  
   const ctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK  
) throw( );  
```  
  
#### パラメーター  
 `ctype`  
 データ型である template 宣言されたパラメーター。  
  
 `nParam`  
 \[\]パラメーター数 \(1\) からのオフセット。  パラメーターは 0 戻り値のために予約されています。  パラメーターの数は、SQL またはストアド プロシージャ呼び出しの順序に基づいてパラメーターのインデックスです。  たとえば、次のようになります。  
  
 [!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/CPP/cdynamicparameteraccessor-setparam_1.cpp)]  
  
 `pParamName`  
 \[入力\] パラメーター名。  
  
 `pData`  
 \[\]などメモリへのポインター バッファーに書き込むデータ。  
  
 *status*  
 \[\] `DBSTATUS` 列のステータス。  `DBSTATUS` 値の詳細については、*OLE DB Programmer's Reference*の [状態](https://msdn.microsoft.com/en-us/library/ms722617.aspx) を参照するか、oledb.h の `DBSTATUS` を検索します。  
  
## 戻り値  
 成功の戻り **true** または失敗の **false**。  
  
 バッファー パラメーターにもデータを設定するために `SetParam` を使用します。  バッファーの文字列パラメーター データを設定するために [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) を使用します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)