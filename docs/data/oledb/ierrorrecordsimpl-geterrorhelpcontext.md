---
title: "Ierrorrecordsimpl::geterrorhelpcontext |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpContext
- IErrorRecordsImpl.GetErrorHelpContext
dev_langs: C++
helpviewer_keywords: GetErrorHelpContext method
ms.assetid: 53d70239-0d64-482e-9ad4-4e1f4f02d5a3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7487895fc79a9d7fba1ed7b49fb7bce934d2b724
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ierrorrecordsimplgeterrorhelpcontext"></a>IErrorRecordsImpl::GetErrorHelpContext
エラー レコードからのヘルプ コンテキスト ID を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      DWORD GetErrorHelpContext(  
   ERRORINFO& rCurError   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rCurError`  
 `ERRORINFO`レコードで、 **IErrorInfo**インターフェイスです。  
  
## <a name="return-value"></a>戻り値  
 エラーのヘルプ コンテキスト ID です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IErrorRecordsImpl クラス](../../data/oledb/ierrorrecordsimpl-class.md)