---
title: "CDBErrorInfo::GetCustomErrorObject | Microsoft Docs"
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
  - "CDBErrorInfo::GetCustomErrorObject"
  - "ATL.CDBErrorInfo.GetCustomErrorObject"
  - "CDBErrorInfo.GetCustomErrorObject"
  - "ATL::CDBErrorInfo::GetCustomErrorObject"
  - "GetCustomErrorObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCustomErrorObject メソッド"
ms.assetid: 295c053c-b76c-47a5-adfb-333e65d2df0d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBErrorInfo::GetCustomErrorObject
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) をカスタム エラー オブジェクトのインターフェイスへのポインターを取得します。  
  
## 構文  
  
```  
  
      HRESULT GetCustomErrorObject(   
   ULONG ulRecordNum,   
   REFIID riid,   
   IUnknown** ppObject    
) const throw( );  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) を参照してください。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDBErrorInfo クラス](../../data/oledb/cdberrorinfo-class.md)