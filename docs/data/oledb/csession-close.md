---
title: "Csession::close |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: dc36c4c0-e588-4c0b-91d1-fc7dc5c8e7f4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ceefd83603962f97050f8a2c494c7acdf7c383ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="csessionclose"></a>CSession::Close
によって開かれたセッションを閉じます[csession::open](../../data/oledb/csession-open.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
  
void Close( ) throw( );  
  
```  
  
## <a name="remarks"></a>コメント  
 リリース、 **m_spOpenRowset**ポインター。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CSession クラス](../../data/oledb/csession-class.md)