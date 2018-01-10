---
title: "Irowsetlocateimpl::hash |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
dev_langs: C++
helpviewer_keywords: Hash method
ms.assetid: 7df4386d-80fb-4332-a85f-baae98cdc6e0
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c3cb64979b8c1ff7a5b9d2e9441a91da0c77f2b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetlocateimplhash"></a>IRowsetLocateImpl::Hash
指定されたブックマークの値のハッシュを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD ( Hash )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmarks,  
   const DBBKMARK* rgcbBookmarks[],  
   const BYTE* rgpBookmarks[],  
   DBHASHVALUE rgHashValues[],  
   DBROWSTATUS rgBookmarkStatus[]   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hReserved`  
 [in]対応する`hChapter`パラメーターを[IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx)です。  
  
 その他のパラメーターを参照してください。 [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetLocateImpl クラス](../../data/oledb/irowsetlocateimpl-class.md)