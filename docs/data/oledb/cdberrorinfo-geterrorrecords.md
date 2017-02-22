---
title: "CDBErrorInfo::GetErrorRecords | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBErrorInfo.GetErrorRecords"
  - "ATL.CDBErrorInfo.GetErrorRecords"
  - "ATL::CDBErrorInfo::GetErrorRecords"
  - "GetErrorRecords"
  - "CDBErrorInfo::GetErrorRecords"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorRecords メソッド"
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDBErrorInfo::GetErrorRecords
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定されたオブジェクトのエラー レコードを取得します。  
  
## 構文  
  
```  
  
      HRESULT GetErrorRecords(   
   IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords    
) throw( );  
HRESULT GetErrorRecords(   
   ULONG* pcRecords    
) throw( );  
```  
  
#### パラメーター  
 *pUnk*  
 \[\]エラー レコードを取得するオブジェクトにインターフェイスです。  
  
 `iid`  
 \[\]エラーに関連付けられたインターフェイスの IID。  
  
 *pcRecords*  
 \[\]エラー レコード \(インデックス番号が 1 から始まるな\) 数へのポインター。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 から、エラー情報を取得するインターフェイスの確認する場合は、関数の最初のフォームを使用します。  それ以外の場合は、2 番目のフォームを使用します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDBErrorInfo クラス](../../data/oledb/cdberrorinfo-class.md)