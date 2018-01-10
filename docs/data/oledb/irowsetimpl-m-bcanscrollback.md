---
title: "Irowsetimpl::m_bcanscrollback |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
dev_langs: C++
helpviewer_keywords: m_bCanScrollBack
ms.assetid: 69de3179-bf56-415e-935f-e98bcb34debe
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2f0fd3e481033947ddce11193872085b553d5ff7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplmbcanscrollback"></a>IRowsetImpl::m_bCanScrollBack
プロバイダーがそのカーソルのスクロールを旧バージョンとができるかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```  
  
unsigned  m_bCanScrollBack:1;  
  
```  
  
## <a name="remarks"></a>コメント  
 リンク、 **DBPROP_CANSCROLLBACKWARDS**プロパティに、 **DBPROPSET_ROWSET**グループ。 プロバイダーをサポートする必要があります**DBPROP_CANSCROLLBACKWARDS**の**m_bCanFetchBackwards**を true にします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::m_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)