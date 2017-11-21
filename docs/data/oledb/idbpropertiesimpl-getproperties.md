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
ms.openlocfilehash: 6e066e525def0a983d6912774f2e27e2af045a01
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IDBPropertiesImpl クラス](../../data/oledb/idbpropertiesimpl-class.md)   
 [Idbpropertiesimpl::getpropertyinfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)