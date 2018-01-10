---
title: "Crowset::getrowstatus |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset.GetRowStatus
- ATL.CRowset<TAccessor>.GetRowStatus
- ATL::CRowset<TAccessor>::GetRowStatus
- CRowset::GetRowStatus
- ATL::CRowset::GetRowStatus
- CRowset<TAccessor>::GetRowStatus
- ATL.CRowset.GetRowStatus
- CRowset<TAccessor>.GetRowStatus
- GetRowStatus
dev_langs: C++
helpviewer_keywords: GetRowStatus method
ms.assetid: 7a29a235-cb7e-40c1-92ce-5441751febee
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: af94964b3aa68348ad976353845d4647f20d1ef9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetgetrowstatus"></a>CRowset::GetRowStatus
すべての行の状態を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT GetRowStatus(   
   DBPENDINGSTATUS* pStatus    
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pStatus`  
 [out]場所へのポインターを`GetRowStatus`ステータス値を返します。 OLE DB プログラマーズ リファレンス DBPENDINGSTATUS を参照してください。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドには、省略可能なインターフェイスが必要とする`IRowsetUpdate`、する可能性がありますすべてのプロバイダーでサポートされていない以外の場合は、そうでは、返されます**E_NOINTERFACE**です。 設定する必要もあります**DBPROP_IRowsetUpdate**に`VARIANT_TRUE`呼び出す前に**開く**テーブルまたは行セットを含むコマンドをします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/en-us/library/ms724377.aspx)