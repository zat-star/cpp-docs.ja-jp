---
title: "IRowsetCreatorImpl::SetSite | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetCreatorImpl.SetSite"
  - "IRowsetCreatorImpl<T>::SetSite"
  - "IRowsetCreatorImpl::SetSite"
  - "SetSite"
  - "ATL.IRowsetCreatorImpl.SetSite"
  - "ATL::IRowsetCreatorImpl<T>::SetSite"
  - "ATL::IRowsetCreatorImpl::SetSite"
  - "ATL.IRowsetCreatorImpl<T>.SetSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetSite メソッド"
ms.assetid: e92e63d5-93e4-4ee0-9ef7-bb6583cc8091
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetCreatorImpl::SetSite
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行セット オブジェクトを含むサイトを設定します。  詳細については、「[IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869)」を参照してください。  
  
## 構文  
  
```  
  
      STDMETHOD( SetSite )(  
   IUnknown* pCreator   
);  
```  
  
#### パラメーター  
 `pCreator`  
 \[\]行セット オブジェクトを管理するサイトの **IUnknown** インターフェイス ポインターへのポインター。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 また、`IRowsetCreatorImpl::SetSite` は OLE DB の **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS** のプロパティを有効にします。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetCreatorImpl クラス](../Topic/IRowsetCreatorImpl%20Class.md)