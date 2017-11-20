---
title: "Csession::gettransactioninfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetTransactionInfo
- CSession.GetTransactionInfo
- ATL.CSession.GetTransactionInfo
- CSession::GetTransactionInfo
- ATL::CSession::GetTransactionInfo
dev_langs: C++
helpviewer_keywords: GetTransactionInfo method
ms.assetid: 9fa62808-3162-4b5a-8610-e1abb8cf9a71
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 105d5f7b63fbd5e38b9363c4bfcc78f5e7dc8f14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="csessiongettransactioninfo"></a>CSession::GetTransactionInfo
トランザクションに関する情報を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT GetTransactionInfo(   
   XACTTRANSINFO* pInfo    
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[ITransaction::GetTransactionInfo](https://msdn.microsoft.com/en-us/library/ms714975.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/en-us/library/ms714975.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CSession クラス](../../data/oledb/csession-class.md)