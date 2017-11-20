---
title: "Cdataconnection::operator CDataSource&amp; |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
dev_langs: C++
helpviewer_keywords:
- CDataSource& operator
- operator & (CDataSource)
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc2309b7b97a97d19ff9a68895fef3ed3bda8b7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionoperator-cdatasourceamp"></a>Cdataconnection::operator CDataSource&amp;
格納されている参照を返します`CDataSource`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
  
operator const CDataSource&() throw( );  
  
```  
  
## <a name="remarks"></a>コメント  
 この演算子は、包含への参照を返します`CDataSource`オブジェクトを渡して、`CDataConnection`オブジェクトを`CDataSource`参照を必要とします。  
  
## <a name="example"></a>例  
 関数がある場合 (など`func`下) を受け取る、`CDataSource`参照を行うこともできます**CDataSource &**に渡す、`CDataConnection`オブジェクトの代わりにします。  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)