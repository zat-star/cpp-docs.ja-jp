---
title: "Cdataconnection::operator BOOL |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- operator bool
ms.assetid: ad0bea7f-61ff-47f7-8127-32a31e3e9b9d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a29d4a3878750f2ca7e70eff032ac9d2cb6b986c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectionoperator-bool"></a>CDataConnection::operator BOOL
か、現在のセッションが開いているかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp
operator BOOL() throw();  
  
```  
  
## <a name="remarks"></a>コメント  
 返します**BOOL** (MFC の typedef) 値です。 **TRUE**現在のセッションが開いていることを意味**FALSE**現在のセッションが閉じられたことを意味します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [Cdataconnection::operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)