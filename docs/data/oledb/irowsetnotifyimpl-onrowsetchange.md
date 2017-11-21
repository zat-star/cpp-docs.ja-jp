---
title: "Irowsetnotifyimpl::onrowsetchange |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
dev_langs: C++
helpviewer_keywords: OnRowsetChange method
ms.assetid: 5125b0c8-f175-4ee6-befa-8df2c904d5e0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6073976867099ff683f1afdd3f4e593ffd5a8876
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetnotifyimplonrowsetchange"></a>IRowsetNotifyImpl::OnRowsetChange
行セット全体に影響する変更をコンシューマーに通知します。  
  
## <a name="syntax"></a>構文  
  
```  
  
   STDMETHOD(OnRowsetChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](https://msdn.microsoft.com/en-us/library/ms722669.aspx)パラメーターの説明をします。  
  
## <a name="return-value"></a>戻り値  
 参照してください[は、](https://msdn.microsoft.com/en-us/library/ms722669.aspx)戻り値についてです。  
  
## <a name="remarks"></a>コメント  
 このメソッドをラップ、[は、](https://msdn.microsoft.com/en-us/library/ms722669.aspx)メソッドです。 詳細については、OLE DB プログラマーズ リファレンス内のメソッドの説明を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetNotifyImpl クラス](../../data/oledb/irowsetnotifyimpl-class.md)   
 [は、](https://msdn.microsoft.com/en-us/library/ms722669.aspx)