---
title: "Irowsetimpl::createrow |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
dev_langs: C++
helpviewer_keywords: CreateRow method
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2f455935a1736eae2c70d95f4528d216a80e782a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplcreaterow"></a>IRowsetImpl::CreateRow
によって呼び出されたヘルパー メソッド[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)に割り当てる新しい**HROW**です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT CreateRow(  
   DBROWOFFSET lRowsOffset,  
   DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows   
);  
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)