---
title: "Irowsetnotifycp::fire_onrowchange |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetNotifyCP.Fire_OnRowChange
- ATL.IRowsetNotifyCP.Fire_OnRowChange
- Fire_OnRowChange
- ATL::IRowsetNotifyCP::Fire_OnRowChange
- IRowsetNotifyCP::Fire_OnRowChange
dev_langs: C++
helpviewer_keywords: Fire_OnRowChange method
ms.assetid: 6f9beed6-7a69-4c92-936f-422e98f3de5c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8a2530aa2496dca64f238c003ac6e25c9f80d6c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetnotifycpfireonrowchange"></a>IRowsetNotifyCP::Fire_OnRowChange
ブロードキャスト、 [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx)イベント接続ポイントに対するすべてのリスナーを**IID_IRowsetNotify**行に影響する変更のコンシューマーに通知します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT Fire_OnRowChange(  
   IRowset* pRowset,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](https://msdn.microsoft.com/en-us/library/ms722694.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetNotifyCP クラス](../../data/oledb/irowsetnotifycp-class.md)