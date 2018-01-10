---
title: "Idbpropertiesimpl::setproperties |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl.SetProperties
- SetProperties
- IDBPropertiesImpl::SetProperties
dev_langs: C++
helpviewer_keywords: SetProperties method
ms.assetid: 2f9fc1de-7f35-4bca-bab3-7b427bf92c26
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d835810a2ca14c8e0631ed7dda8fcaddeb859d71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="idbpropertiesimplsetproperties"></a>IDBPropertiesImpl::SetProperties
列挙子のデータ ソースと初期化プロパティ グループのデータ ソース オブジェクトまたは Initialization プロパティ グループのプロパティを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[idbproperties::setproperties](https://msdn.microsoft.com/en-us/library/ms723049.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="remarks"></a>コメント  
 このメソッドがプロパティの値を設定する場合は、プロバイダーを初期化、**された DBPROPSET_DATASOURCE**、 **DBPROPSET_DATASOURCEINFO**、 **DBPROPSET_DBINIT**プロパティデータ ソース オブジェクトのグループ。 プロバイダーが初期化されていない場合は設定**DBPROPSET_DBINIT**プロパティのみをグループ化します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IDBPropertiesImpl クラス](../../data/oledb/idbpropertiesimpl-class.md)   
 [Idbpropertiesimpl::getproperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)