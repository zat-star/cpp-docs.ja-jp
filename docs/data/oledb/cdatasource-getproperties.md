---
title: "CDataSource::GetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource::GetProperties"
  - "ATL.CDataSource.GetProperties"
  - "CDataSource.GetProperties"
  - "ATL::CDataSource::GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties メソッド"
ms.assetid: ffaecc17-9fe7-449e-94d6-43d31ad06cfc
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDataSource::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アタッチされたデータ ソース オブジェクトに要求するプロパティ情報を返します。  
  
## 構文  
  
```  
  
      HRESULT GetProperties(   
   ULONG ulPropIDSets,   
   const DBPROPIDSET* pPropIDSet,   
   ULONG* pulPropertySets,   
   DBPROPSET** ppPropsets    
) const throw( );  
```  
  
#### パラメーター  
 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の *OLE DB Programmer's Reference* の [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) を参照してください。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 一つのプロパティを取得するには、[GetProperty](../Topic/CDataSource::GetProperty.md)を使用します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDataSource クラス](../Topic/CDataSource%20Class.md)