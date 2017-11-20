---
title: "Cdynamicparameteraccessor::getparamstatus |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor::GetParamStatus
- CDynamicParameterAccessor.GetParamStatus
- ATL.CDynamicParameterAccessor.GetParamStatus
- ATL::CDynamicParameterAccessor::GetParamStatus
- GetParamStatus
dev_langs: C++
helpviewer_keywords: GetParamStatus method
ms.assetid: 9300225a-616c-4a7d-82d0-8c2ecd4d8185
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 483a6b8aea87d552d1397f70222323fbe8514747
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicparameteraccessorgetparamstatus"></a>CDynamicParameterAccessor::GetParamStatus
バッファーに格納され、指定されたパラメーターのステータスを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      bool GetParamStatus(  
   DBORDINAL nParam,  
   DBSTATUS* pStatus  
);  
DBSTATUS* GetParamStatus(   
   DBORDINAL nParam    
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nParam`  
 [in]パラメーターの数 (1 からのオフセット)。 に対するパラメーター 0 は、戻り値に予約されています。 パラメーター数は、SQL またはストアド プロシージャの呼び出しでその順序に基づいて、パラメーターのインデックスです。 参照してください[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)例についてはします。  
  
 `pStatus`  
 [out]変数を含むへのポインター、`DBSTATUS`指定されたパラメーターの状態。 詳細について`DBSTATUS`値を参照してください[ステータス](https://msdn.microsoft.com/en-us/library/ms722617.aspx)で、 *OLE DB プログラマーズ リファレンス*、または検索`DBSTATUS`oledb.h でします。  
  
## <a name="remarks"></a>コメント  
 最初の形式**true**成功した場合または**false**エラー発生時にします。 2 つ目は、指定されたパラメーターの状態を表すメモリへのポインターをオーバーライドします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)