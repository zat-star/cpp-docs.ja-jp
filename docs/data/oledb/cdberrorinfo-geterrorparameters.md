---
title: "Cdberrorinfo::geterrorparameters |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDBErrorInfo.GetErrorParameters
- CDBErrorInfo::GetErrorParameters
- ATL::CDBErrorInfo::GetErrorParameters
- CDBErrorInfo.GetErrorParameters
- GetErrorParameters
dev_langs: C++
helpviewer_keywords: GetErrorParameters method
ms.assetid: 3a2dd8e2-fecc-4315-9f2b-ce3138cdd187
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 16b4cdfe26eb7e5f9d22803f80090c4e7cc6f5c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdberrorinfogeterrorparameters"></a>CDBErrorInfo::GetErrorParameters
呼び出し[IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx)エラー パラメーターを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT GetErrorParameters(   
   ULONG ulRecordNum,   
   DISPPARAMS* pdispparams    
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDBErrorInfo クラス](../../data/oledb/cdberrorinfo-class.md)