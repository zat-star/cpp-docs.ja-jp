---
title: "Ierrorrecordsimpl::geterrorsource |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IErrorRecordsImpl.GetErrorSource
- GetErrorSource
- IErrorRecordsImpl::GetErrorSource
dev_langs: C++
helpviewer_keywords: GetErrorSource method
ms.assetid: 5436f1ce-c5a4-403b-a62b-c58e70e5c925
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 312b8e28201447def0f09da9bcefc4a78e15d8ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ierrorrecordsimplgeterrorsource"></a>IErrorRecordsImpl::GetErrorSource
エラー レコードからエラーが発生したソース コードを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      LPOLESTR GetErrorSource(  
   ERRORINFO& rCurError   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rCurError`  
 `ERRORINFO`レコードで、 **IErrorInfo**インターフェイスです。  
  
## <a name="return-value"></a>戻り値  
 エラーのソース コードを含む文字列へのポインター。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IErrorRecordsImpl クラス](../../data/oledb/ierrorrecordsimpl-class.md)