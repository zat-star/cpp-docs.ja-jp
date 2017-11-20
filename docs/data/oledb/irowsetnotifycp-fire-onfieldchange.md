---
title: "Irowsetnotifycp::fire_onfieldchange |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Fire_OnFieldChange
- ATL::IRowsetNotifyCP::Fire_OnFieldChange
- ATL.IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP::Fire_OnFieldChange
dev_langs: C++
helpviewer_keywords: Fire_OnFieldChange method
ms.assetid: 03dad058-8d4f-4113-aea4-ef7764eab9ec
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fe8c43c04576e416718e5897dfffe07686210f77
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetnotifycpfireonfieldchange"></a>IRowsetNotifyCP::Fire_OnFieldChange
ブロードキャスト、 [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx)列の値に対する変更をコンシューマーに通知するイベントです。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT Fire_OnFieldChange(  
   IRowset* pRowset,  
   HROW hRow,  
   DBORDINAL cColumns,  
   DBORDINAL* rgColumns,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](https://msdn.microsoft.com/en-us/library/ms715961.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetNotifyCP クラス](../../data/oledb/irowsetnotifycp-class.md)