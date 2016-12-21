---
title: "IDBPropertiesImpl クラス | Microsoft Docs"
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
  - "IDBPropertiesImpl"
  - "ATL.IDBPropertiesImpl"
  - "ATL.IDBPropertiesImpl<T>"
  - "ATL::IDBPropertiesImpl<T>"
  - "ATL::IDBPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBPropertiesImpl クラス"
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBPropertiesImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`IDBProperties` インターフェイスの実装を提供します。  
  
## 構文  
  
```  
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### パラメーター  
 `T`  
 クラス、`IDBPropertiesImpl`から派生します。  
  
## メンバー  
  
### インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|初期化プロパティのグループのプロパティのデータ ソース オブジェクトまたは列挙子で設定されている値で現在設定されているデータ ソース、データ ソース情報と初期化プロパティのグループのプロパティの値を返します。|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|プロバイダーによってサポートされているすべてのプロパティに関する情報を返します。|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|データ ソースと初期化プロパティのグループのプロパティ、データ ソース オブジェクトに対して、または列挙子の初期化プロパティのグループを設定します。|  
  
## 解説  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) を列挙子データ ソース オブジェクトと省略可能なインターフェイスの必須インターフェイスです。  ただし、列挙子が [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx)を公開する場合は、`IDBProperties`を公開する必要があります。  `IDBPropertiesImpl` は [BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md)で定義された静的関数を使用して `IDBProperties` を実装します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)