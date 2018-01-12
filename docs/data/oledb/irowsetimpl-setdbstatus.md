---
title: "Irowsetimpl::setdbstatus |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
dev_langs: C++
helpviewer_keywords: SetDBStatus method
ms.assetid: b73f526a-4fc6-4adb-9611-c3cca2cddb23
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 285f9004c9971d18646626b7410dcb52485227c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplsetdbstatus"></a>IRowsetImpl::SetDBStatus
セット、`DBSTATUS`指定したフィールドの状態フラグ。  
  
## <a name="syntax"></a>構文  
  
```  
  
      virtual HRESULT SetDBStatus(  
   DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `statusFlags`  
 [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx)列に対して設定するフラグ。  
  
 `currentRow`  
 現在の行。  
  
 *columnInfo*  
 状態が設定されている列です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
## <a name="remarks"></a>コメント  
 プロバイダーに対する特別な処理を提供するには、この関数をオーバーライドする**DBSTATUS_S_ISNULL**と**DBSTATUS_S_DEFAULT**です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)