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
ms.openlocfilehash: 31555e1f8305a281955902b71fdc71fbcc5405e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetChangeImpl クラス](../../data/oledb/irowsetchangeimpl-class.md)