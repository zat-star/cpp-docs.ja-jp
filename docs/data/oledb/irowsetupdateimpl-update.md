---
title: "Irowsetupdateimpl::update |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
dev_langs:
- C++
helpviewer_keywords:
- Update method
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 98d0fde6c4fddf43cf353018ca7fcafea82a6f6e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetupdateimplupdate"></a>IRowsetUpdateImpl::Update
最後のフェッチまたは更新以降、行に加えられた変更を送信します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (Update )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hReserved`  
 [in]対応する、`hChapter`パラメーター [irowsetupdate::update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)です。  
  
 その他のパラメーターを参照してください。 [irowsetupdate::update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="remarks"></a>コメント  
 呼び出して変更を転送する[irowsetchangeimpl::flushdata](../../data/oledb/irowsetchangeimpl-flushdata.md)です。 コンシューマーは、呼び出す必要があります[crowset::update](../../data/oledb/crowset-update.md)変更を有効にするためにします。 設定*prgRowstatus* 」の説明に従って適切な値に[行状態](https://msdn.microsoft.com/en-us/library/ms722752.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)