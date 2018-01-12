---
title: "Cdynamicparameteraccessor::getparamlength |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDynamicParameterAccessor::GetParamLength
- ATL.CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor::GetParamLength
- GetParamLength
dev_langs: C++
helpviewer_keywords: GetParamLength method
ms.assetid: 04d76931-911a-4915-9c2c-ad585a9f3854
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1fe89c4734102cbd9f5928642092f2bca41db0dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorgetparamlength"></a>CDynamicParameterAccessor::GetParamLength
バッファーに格納され、指定されたパラメーターの長さを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      bool GetParamLength(  
   DBORDINAL nParam,  
   DBLENGTH* pLength  
);  
DBLENGTH* GetParamLength(   
   DBORDINAL nParam    
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nParam`  
 [in]パラメーターの数 (1 からのオフセット)。 に対するパラメーター 0 は、戻り値に予約されています。 パラメーター数は、SQL またはストアド プロシージャの呼び出しでその順序に基づいて、パラメーターのインデックスです。 参照してください[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)例についてはします。  
  
 `pLength`  
 [out]指定されたパラメーターの長さ (バイト単位) を含む変数へのポインター。  
  
## <a name="remarks"></a>コメント  
 最初の形式**true**成功した場合または**false**エラー発生時にします。 2 つ目は、パラメーターの長さを表すメモリへのポインターをオーバーライドします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)