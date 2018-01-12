---
title: "Cdataconnection::operator CDataSource * |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
dev_langs: C++
helpviewer_keywords:
- CDataSource* operator
- operator * (CDataSource)
ms.assetid: 9118e324-e68d-45c5-a791-03f041d420ed
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2519e036aab6df464ad3e25bc48447ced5af352a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdataconnectionoperator-cdatasource"></a>CDataConnection::operator CDataSource*
格納されているポインターを返します`CDataSource`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
  
operator const CDataSource*() throw( );  
  
```  
  
## <a name="remarks"></a>コメント  
 この演算子が格納されているへのポインターを返します`CDataSource`を渡すことをすることにより、オブジェクト、`CDataConnection`オブジェクトを`CDataSource`ポインターが必要です。  
  
 参照してください[演算子 CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)使用例についてはします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)