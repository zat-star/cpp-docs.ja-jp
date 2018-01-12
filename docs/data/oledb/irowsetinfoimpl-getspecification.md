---
title: "Irowsetinfoimpl::getspecification |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetInfoImpl::GetSpecification
- ATL.IRowsetInfoImpl.GetSpecification
- IRowsetInfoImpl.GetSpecification
- GetSpecification
- ATL::IRowsetInfoImpl::GetSpecification
dev_langs: C++
helpviewer_keywords: GetSpecification method
ms.assetid: 8e14289d-9cca-4df7-a9e0-f4ef03c61e30
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c2c0fd40e5d46b67779da50983b8b8faad13a024
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetinfoimplgetspecification"></a>IRowsetInfoImpl::GetSpecification
この行セットを作成するオブジェクト (コマンドまたはセッション) のインターフェイス ポインターを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD ( GetSpecification )(  
   REFIID riid,  
   IUnknown** ppSpecification   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IRowsetInfo::GetSpecification](https://msdn.microsoft.com/en-us/library/ms716746.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="remarks"></a>コメント  
 このメソッドを使用[IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)データ ソース オブジェクトからプロパティを取得します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetInfoImpl クラス](../../data/oledb/irowsetinfoimpl-class.md)   
 [Irowsetinfoimpl::getreferencedrowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)   
 [IRowsetInfoImpl::GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)