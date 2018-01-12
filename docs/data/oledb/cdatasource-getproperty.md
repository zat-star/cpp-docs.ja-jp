---
title: "Cdatasource::getproperty |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
dev_langs: C++
helpviewer_keywords: GetProperty method
ms.assetid: 6531147c-b164-4ab5-a4a7-509634b85b4d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 304a96ef9bb5e918dccaf473577f49b6b8d5d78f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdatasourcegetproperty"></a>CDataSource::GetProperty
接続されているデータ ソース オブジェクトに対して指定されたプロパティの値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT GetProperty(   
   const GUID& guid,   
   DBPROPID propid,   
   VARIANT* pVariant    
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 [in]プロパティを取得する対象のプロパティの設定を識別する GUID。  
  
 `propid`  
 [in]プロパティを返すには、プロパティの ID。  
  
 *pVariant*  
 [out]バリアントを指すポインターを**GetProperty**プロパティの値を返します。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 複数のプロパティを取得する[GetProperties](../../data/oledb/cdatasource-getproperties.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDataSource クラス](../../data/oledb/cdatasource-class.md)