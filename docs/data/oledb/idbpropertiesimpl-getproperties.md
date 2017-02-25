---
title: "IDBPropertiesImpl::GetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBPropertiesImpl::GetProperties"
  - "IDBPropertiesImpl.GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties メソッド"
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBPropertiesImpl::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

初期化プロパティのグループのプロパティのデータ ソース オブジェクトまたは列挙子で設定されている値で現在設定されているデータ ソース、データ ソース情報と初期化プロパティのグループのプロパティの値を返します。  
  
## 構文  
  
```  
  
      STDMETHOD(GetProperties)(   
   ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties    
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) を参照してください。  
  
 一部のパラメーターは **IDBProperties::GetProperties**で説明されている異なる名前で *OLE DB の Programmer's Reference* パラメーターに対応します:  
  
|OLE DB テンプレート パラメーター|*OLE DB の Programmer's Reference* パラメーター|  
|--------------------------|----------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## 解説  
 プロバイダーが初期化されれば、メソッドの戻り **DBPROPSET\_DATASOURCE**のプロパティ、**DBPROPSET\_DATASOURCEINFO**のデータ ソース オブジェクトで現在設定されている **DBPROPSET\_DBINIT** プロパティ グループの値を返します。  プロバイダーが初期化されなければ、**DBPROPSET\_DBINIT** の Group プロパティのみを返します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IDBPropertiesImpl クラス](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)