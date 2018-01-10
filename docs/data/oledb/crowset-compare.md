---
title: "Crowset::compare |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset<TAccessor>.Compare
- CRowset<TAccessor>::Compare
- ATL.CRowset<TAccessor>.Compare
- ATL::CRowset<TAccessor>::Compare
- CRowset.Compare
- ATL::CRowset::Compare
- ATL.CRowset.Compare
- CRowset::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: a8117b40-7abd-4867-b0ba-eb9e9808204e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9d7e69c168489fcfe71c14fbbfe2b2aca8e28f62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetcompare"></a>CRowset::Compare
使用してをブックマーク 2 つの比較[IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx)です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT Compare(   
   const CBookmarkBase& bookmark1,   
   const CBookmarkBase& bookmark2,   
   DBCOMPARE* pComparison    
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 *Bookmark1*  
 [in]比較する最初のブックマークです。  
  
 *Bookmark2*  
 [in]比較する 2 番目のブックマークです。  
  
 `pComparison`  
 [out]比較の結果へのポインター。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドには、省略可能なインターフェイスが必要とする`IRowsetLocate`、する可能性がありますすべてのプロバイダーでサポートされていない以外の場合は、そうでは、返されます**E_NOINTERFACE**です。 設定する必要もあります**DBPROP_IRowsetLocate**に`VARIANT_TRUE`呼び出す前に**開く**テーブルまたは行セットを含むコマンドをします。  
  
 コンシューマーでのブックマークの使用方法の詳細については、次を参照してください。[を使用してブックマーク](../../data/oledb/using-bookmarks.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CRowset クラス](../../data/oledb/crowset-class.md)