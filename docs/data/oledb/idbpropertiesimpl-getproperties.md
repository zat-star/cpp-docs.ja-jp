---
title: "Idbpropertiesimpl::getproperties |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- GetProperties
dev_langs: C++
helpviewer_keywords: GetProperties method
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ac54b08dba170dd33d2e5e19cae50715aeab4fb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="idbpropertiesimplgetproperties"></a>IDBPropertiesImpl::GetProperties
データ ソース オブジェクトで現在設定されている初期化プロパティ グループ内のプロパティの値に設定されているデータ ソース、データ ソース情報、および初期化プロパティ グループのプロパティの値を返す、列挙子。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD(GetProperties)(   
   ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties    
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 いくつかのパラメーターに対応*OLE DB プログラマーズ リファレンス*で説明される、別の名前のパラメーター **IDBProperties::GetProperties**:  
  
|OLE DB テンプレート パラメーター|*OLE DB プログラマーズ リファレンス*パラメーター|  
|--------------------------------|------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*その*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## <a name="remarks"></a>コメント  
 このメソッドがプロパティの値を返します、プロバイダーが初期化されている場合、**された DBPROPSET_DATASOURCE**、 **DBPROPSET_DATASOURCEINFO**、 **DBPROPSET_DBINIT**データ ソース オブジェクトに現在設定されているプロパティ グループです。 プロバイダーが初期化されていないかどうかそれを返します**DBPROPSET_DBINIT**プロパティのみをグループ化します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IDBPropertiesImpl クラス](../../data/oledb/idbpropertiesimpl-class.md)   
 [Idbpropertiesimpl::getpropertyinfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)