---
title: "Irowsetupdateimpl::setdata |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SetData
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
dev_langs: C++
helpviewer_keywords: SetData method
ms.assetid: 7288a8d1-a7cf-4957-b832-0f3b18fd0da4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e098db995bad0d99e47d6108436a5324d2920e9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetupdateimplsetdata"></a>IRowsetUpdateImpl::SetData
1 つまたは複数の列のデータ値を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD ( SetData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[irowsetchange::setdata](https://msdn.microsoft.com/en-us/library/ms721232.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、 [irowsetchangeimpl::setdata](../../data/oledb/irowsetchangeimpl-setdata.md)がメソッドにはでは操作の即時または遅延のいずれかの処理を許可するように元のデータのキャッシュが含まれます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)