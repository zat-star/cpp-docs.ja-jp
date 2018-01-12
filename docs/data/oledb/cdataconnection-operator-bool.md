---
title: "Cdataconnection::operator BOOL |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
dev_langs: C++
helpviewer_keywords:
- BOOL operator
- operator bool
ms.assetid: ad0bea7f-61ff-47f7-8127-32a31e3e9b9d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 342a8074f61a6f05505534ff497010b8a752293c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdataconnectionoperator-bool"></a>CDataConnection::operator BOOL
か、現在のセッションが開いているかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```  
  
operator BOOL( ) throw( );  
  
```  
  
## <a name="remarks"></a>コメント  
 返します**BOOL** (MFC の typedef) 値です。 **TRUE**現在のセッションが開いていることを意味**FALSE**現在のセッションが閉じられたことを意味します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [Cdataconnection::operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)