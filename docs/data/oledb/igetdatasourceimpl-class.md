---
title: "IGetDataSourceImpl クラス | Microsoft Docs"
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
  - "IGetDataSourceImpl"
  - "ATL.IGetDataSourceImpl<T>"
  - "ATL.IGetDataSourceImpl"
  - "ATL::IGetDataSourceImpl"
  - "ATL::IGetDataSourceImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IGetDataSourceImpl クラス"
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IGetDataSourceImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx) オブジェクトの実装を提供します。  
  
## 構文  
  
```  
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
#### パラメーター  
 `T`  
 クラス、`IGetDataSourceImpl`から派生します。  
  
## メンバー  
  
### インターフェイス メソッド  
  
|||  
|-|-|  
|[GetDataSource](../Topic/IGetDataSourceImpl::GetDataSource.md)|セッションを作成するデータ ソース オブジェクトのインターフェイス ポインターを返します。|  
  
## 解説  
 これは、データ ソース オブジェクトへのインターフェイス ポインターを取得するためのセッションの必須インターフェイスです。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)