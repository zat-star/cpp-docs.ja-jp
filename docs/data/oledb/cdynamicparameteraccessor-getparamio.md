---
title: "Cdynamicparameteraccessor::getparamio |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetParamIO
- CDynamicParameterAccessor::GetParamIO
- ATL.CDynamicParameterAccessor.GetParamIO
- CDynamicParameterAccessor.GetParamIO
- ATL::CDynamicParameterAccessor::GetParamIO
dev_langs: C++
helpviewer_keywords: GetParamIO method
ms.assetid: 9c485e39-c67e-4df7-a707-c773019c4d1e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d09eee048e737b19b21f6d71518d2b70702df8a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicparameteraccessorgetparamio"></a>CDynamicParameterAccessor::GetParamIO
指定されたパラメーターが入力または出力パラメーターであるかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      bool GetParamIO(   
   DBORDINAL nParam,   
   DBPARAMIO * pParamIO    
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nParam`  
 [in]パラメーターの数 (1 からのオフセット)。 に対するパラメーター 0 は、戻り値に予約されています。 パラメーター数は、SQL またはストアド プロシージャの呼び出しでその順序に基づいて、パラメーターのインデックスです。 参照してください[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)例についてはします。  
  
 *pParamIO*  
 変数を含むへのポインター、 **DBPARAMIO**指定されたパラメーターの型 (入力または出力) します。 次のように定義されます。  
  
```  
typedef DWORD DBPARAMIO;  
  
enum DBPARAMIOENUM {  
    DBPARAMIO_NOTPARAM   = 0,  
    DBPARAMIO_INPUT      = 0x1,  
    DBPARAMIO_OUTPUT     = 0x2  
};  
```  
  
## <a name="return-value"></a>戻り値  
 返します**true**成功した場合または**false**エラー発生時にします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)