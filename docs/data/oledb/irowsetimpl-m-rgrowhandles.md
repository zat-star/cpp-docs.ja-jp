---
title: "Irowsetimpl::m_rgrowhandles |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
dev_langs: C++
helpviewer_keywords: m_rgRowHandles
ms.assetid: d3c2578f-58c4-4301-bf59-cf101a523a95
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bdb68e9eac5204da8c293742bcfd6ddcfdba1652
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplmrgrowhandles"></a>IRowsetImpl::m_rgRowHandles
プロバイダーへの応答に含まれる現在の行ハンドルのマップ`GetNextRows`です。  
  
## <a name="syntax"></a>構文  
  
```  
  
MapClass  
 m_rgRowHandles;  
  
```  
  
## <a name="remarks"></a>コメント  
 行ハンドルを呼び出すことによって削除`ReleaseRows`です。 参照してください、 [IRowsetImpl 概要](../../data/oledb/irowsetimpl-class.md)の定義の*MapClass*です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)