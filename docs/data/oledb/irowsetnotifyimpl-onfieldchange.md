---
title: "Irowsetnotifyimpl::onfieldchange |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
dev_langs:
- C++
helpviewer_keywords:
- OnFieldChange method
ms.assetid: f26b492c-c86e-423b-9374-175e510a2860
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aa4d68c6a634600f7afe3295b41b0939675be4f9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetnotifyimplonfieldchange"></a>IRowsetNotifyImpl::OnFieldChange
列の値の変更をコンシューマーに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(OnFieldChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ HROW /* hRow */,  
/* [in] */ DBORDINAL /* cColumns */,  
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](https://msdn.microsoft.com/en-us/library/ms715961.aspx)パラメーターの説明をします。  
  
## <a name="return-value"></a>戻り値  
 参照してください[は、](https://msdn.microsoft.com/en-us/library/ms715961.aspx)戻り値についてです。  
  
## <a name="remarks"></a>コメント  
 このメソッドをラップ、[は、](https://msdn.microsoft.com/en-us/library/ms715961.aspx)メソッドです。 詳細については、OLE DB プログラマーズ リファレンス内のメソッドの説明を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [IRowsetNotifyImpl クラス](../../data/oledb/irowsetnotifyimpl-class.md)   
 [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx)