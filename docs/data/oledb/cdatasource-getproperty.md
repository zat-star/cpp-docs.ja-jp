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
ms.openlocfilehash: 96b7437bd96592044b4eab33df3e4912bd677591
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataSource クラス](../../data/oledb/cdatasource-class.md)