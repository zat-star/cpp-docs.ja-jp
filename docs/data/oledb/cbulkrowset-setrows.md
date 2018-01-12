---
title: "Cbulkrowset::setrows |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
dev_langs: C++
helpviewer_keywords: SetRows method
ms.assetid: 7e92312a-bfd0-4c24-a799-62bef663f28e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87fdb1f634c39062252c2593ae0a5b92d6265660
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cbulkrowsetsetrows"></a>CBulkRowset::SetRows
各呼び出しで取得する行ハンドルの数を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void SetRows(  
   DBROWCOUNT nRows   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nRows`  
 [in]行セット (行の数) の新しいサイズ。  
  
## <a name="remarks"></a>コメント  
 この関数を呼び出す場合は、行セットが開かれる前にあります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CBulkRowset クラス](../../data/oledb/cbulkrowset-class.md)