---
title: "IDBPropertiesImpl::SetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBPropertiesImpl.SetProperties"
  - "SetProperties"
  - "IDBPropertiesImpl::SetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetProperties メソッド"
ms.assetid: 2f9fc1de-7f35-4bca-bab3-7b427bf92c26
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBPropertiesImpl::SetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ソースと初期化プロパティのグループのプロパティ、データ ソース オブジェクトに対して、または列挙子の初期化プロパティのグループを設定します。  
  
## 構文  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [IDBProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms723049.aspx) を参照してください。  
  
## 解説  
 プロバイダーが初期化されれば、このメソッド **DBPROPSET\_DATASOURCE**プロパティの設定は、**DBPROPSET\_DATASOURCEINFO**のデータ ソースに **DBPROPSET\_DBINIT** プロパティ グループの値になります。  プロバイダーが初期化されなければ、**DBPROPSET\_DBINIT** の Group プロパティのみを設定します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IDBPropertiesImpl クラス](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)