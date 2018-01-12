---
title: "Irowsetchangeimpl::flushdata |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
dev_langs: C++
helpviewer_keywords: FlushData method
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 565b971b53ddb0a50b276d76aaaf62e9f7fa39f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetchangeimplflushdata"></a>IRowsetChangeImpl::FlushData
データをそのストアにコミットするためのプロバイダーによってオーバーライドされします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT FlushData(  
   HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hRowToFlush*  
 [in]データの行へのハンドルします。 この行の型を特定、 *RowClass*のテンプレート引数、`IRowsetImpl`クラス (`CSimpleRow`既定)。  
  
 *hAccessorToFlush*  
 [in]バインディング情報およびで型情報が含まれて、アクセサーへのハンドル、 **PROVIDER_MAP** (を参照してください[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md))。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetChangeImpl クラス](../../data/oledb/irowsetchangeimpl-class.md)