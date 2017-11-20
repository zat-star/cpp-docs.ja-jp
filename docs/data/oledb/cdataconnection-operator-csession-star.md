---
title: "Cdataconnection::operator CSession * |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
dev_langs: C++
helpviewer_keywords:
- operator CSession*
- CSession* operator
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8c4ad47ce5163291c45827d94c9e6f8d5904c847
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionoperator-csession"></a>CDataConnection::operator CSession*
格納されているポインターを返します`CSession`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
  
operator const CSession*() throw( );  
  
```  
  
## <a name="remarks"></a>コメント  
 この演算子が格納されているへのポインターを返します`CSession`を渡すことをすることにより、オブジェクト、`CDataConnection`オブジェクトを`CSession`ポインターが必要です。  
  
## <a name="example"></a>例  
 参照してください[演算子 CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md)使用例についてはします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)