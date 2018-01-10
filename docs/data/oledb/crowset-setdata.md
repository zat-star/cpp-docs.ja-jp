---
title: "Crowset::setdata |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.SetData
- SetData
- ATL::CRowset::SetData
- CRowset<TAccessor>.SetData
- CRowset::SetData
- ATL.CRowset.SetData
- CRowset.SetData
- CRowset<TAccessor>::SetData
- ATL::CRowset<TAccessor>::SetData
dev_langs: C++
helpviewer_keywords: SetData method
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0aafc521e130a7f737083390fe5f825c88aa5844
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetsetdata"></a>CRowset::SetData
行の 1 つまたは複数の列のデータ値を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT SetData( ) const throw( );   
HRESULT SetData(  
   int nAccessor   
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nAccessor`  
 [in]データにアクセスするのに使用するアクセサーの数。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 `SetData`引数を指定せず、すべてのアクセサーを受け入れるフォームには更新に使用します。 通常**SetData**値を設定するデータ行の列を呼び出す[更新](../../data/oledb/crowset-update.md)それらの変更を送信します。  
  
 このメソッドには、省略可能なインターフェイスが必要とする`IRowsetChange`、する可能性がありますすべてのプロバイダーでサポートされていない以外の場合は、そうでは、返されます**E_NOINTERFACE**です。 設定する必要もあります**DBPROP_IRowsetChange**に`VARIANT_TRUE`呼び出す前に**開く**テーブルまたは行セットを含むコマンドをします。  
  
 設定操作は、1 つまたは複数の列が書き込み可能な場合に失敗する可能性があります。 これを修正するにはカーソル マップを変更します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)