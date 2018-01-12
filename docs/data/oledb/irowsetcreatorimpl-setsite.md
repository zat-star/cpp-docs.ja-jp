---
title: "Irowsetcreatorimpl::setsite |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
dev_langs: C++
helpviewer_keywords: SetSite method
ms.assetid: e92e63d5-93e4-4ee0-9ef7-bb6583cc8091
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ed3f5f0bce2408cd2a4439aac6728f0e00760b1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetcreatorimplsetsite"></a>IRowsetCreatorImpl::SetSite
行セット オブジェクトを含むサイトを設定します。 詳細については、次を参照してください。 [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869)です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD( SetSite )(  
   IUnknown* pCreator   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pCreator`  
 [in]ポインター、 **IUnknown**行セット オブジェクトを管理するサイトのインターフェイス ポインター。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 さらに、`IRowsetCreatorImpl::SetSite`により、OLE DB **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**プロパティです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetCreatorImpl クラス](../../data/oledb/irowsetcreatorimpl-class.md)