---
title: "Cdataconnection::operator CDataSource&amp; |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
dev_langs:
- C++
helpviewer_keywords:
- CDataSource& operator
- operator & (CDataSource)
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c52610d947d60fa7ea1be9b764fd09ae0e777a3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cdataconnectionoperator-cdatasourceamp"></a>Cdataconnection::operator CDataSource&amp;
格納されている参照を返します`CDataSource`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
operator const CDataSource&() throw();  
  
```  
  
## <a name="remarks"></a>コメント  
 この演算子は、包含への参照を返します`CDataSource`オブジェクトを渡して、`CDataConnection`オブジェクトを`CDataSource`参照を必要とします。  
  
## <a name="example"></a>例  
 関数がある場合 (など`func`下) を受け取る、`CDataSource`参照を行うこともできます**CDataSource &**に渡す、`CDataConnection`オブジェクトの代わりにします。  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)