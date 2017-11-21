---
title: "Irowsetupdateimpl::isupdateallowed |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
dev_langs: C++
helpviewer_keywords: IsUpdateAllowed method
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: feaa5b397989667da62bbf979603391c08eada2c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
セキュリティ、更新後に、整合性を確認するには、このメソッドをオーバーライドします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT IsUpdateAllowed(  
   DBPENDINGSTATUS /* [in] *//* status */,  
   HROW /* [in] *//* hRowUpdate */,  
   DBROWSTATUS* /* [out] *//* pRowStatus */  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *status*  
 [in]保留中の行の操作の状態。  
  
 *hRowUpdate*  
 [in]ユーザーが更新する行のハンドルです。  
  
 *pRowStatus*  
 [out]ユーザーに、状態が返されます。  
  
## <a name="remarks"></a>コメント  
 更新プログラムを許可する必要があると判断した場合を返します`S_OK`以外を返しますそれ以外の場合**E_FAIL**です。 設定する必要がある更新を許可する場合、 **DBROWSTATUS**で[irowsetupdateimpl::update](../../data/oledb/irowsetupdateimpl-update.md)に適切な[状態の行](https://msdn.microsoft.com/en-us/library/ms722752.aspx)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)