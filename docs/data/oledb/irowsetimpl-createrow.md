---
title: "Irowsetimpl::createrow |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
dev_langs:
- C++
helpviewer_keywords:
- CreateRow method
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4403388146b79eec4435374793b2517dd46ff188
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetimplcreaterow"></a>IRowsetImpl::CreateRow
によって呼び出されたヘルパー メソッド[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)に割り当てる新しい**HROW**です。  
  
## <a name="syntax"></a>構文  
  
```
HRESULT CreateRow(DBROWOFFSET lRowsOffset,  
  DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *lRowsOffset*  
 作成されている行のカーソル位置。  
  
 *cRowsObtained*  
 作成される行の数を示すユーザーに、参照が渡されます。  
  
 *rgRows*  
 配列**HROW**新しく作成された行のハンドルが呼び出し元に返されます。  
  
## <a name="remarks"></a>コメント  
 このメソッドを呼び出す行存在する場合、 [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)を返します。 それ以外の場合、RowClass テンプレート変数の新しいインスタンスを割り当てしする追加[m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)