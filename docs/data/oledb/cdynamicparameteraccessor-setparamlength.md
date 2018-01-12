---
title: "Cdynamicparameteraccessor::setparamlength |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDynamicParameterAccessor::SetParamLength
- CDynamicParameterAccessor.SetParamLength
- ATL.CDynamicParameterAccessor.SetParamLength
- CDynamicParameterAccessor::SetParamLength
- SetParamLength
dev_langs: C++
helpviewer_keywords: SetParamLength method
ms.assetid: d8e0bbfe-e1ae-4a8f-9567-584fbb0c8385
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9430ac2a250c41cafce7d8efc7b190625510aa62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorsetparamlength"></a>CDynamicParameterAccessor::SetParamLength
バッファーに格納され、指定されたパラメーターの長さを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      bool SetParamLength(  
   DBORDINAL nParam,  
   DBLENGTH length  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nParam`  
 [in]パラメーターの数 (1 からのオフセット)。 に対するパラメーター 0 は、戻り値に予約されています。 パラメーター数は、SQL またはストアド プロシージャの呼び出しでその順序に基づいて、パラメーターのインデックスです。 参照してください[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)例についてはします。  
  
 *length*  
 [in]指定されたパラメーターの長さを (バイト単位)。  
  
## <a name="remarks"></a>コメント  
 返します**true**成功した場合または**false**エラー発生時にします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)