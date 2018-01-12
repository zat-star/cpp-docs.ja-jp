---
title: "Cdataconnection::cdataconnection |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
dev_langs: C++
helpviewer_keywords: CDataConnection class, constructor
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fd2deb3978ef3c01d5d70297599be54aabb90cb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdataconnectioncdataconnection"></a>CDataConnection::CDataConnection
インスタンスを作成し、初期化、`CDataConnection`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
  
      CDataConnection();   
CDataConnection(  
   const CDataConnection &ds  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ds`  
 [in]既存のデータ接続への参照。  
  
## <a name="remarks"></a>コメント  
 最初のオーバーライドが新たに作成`CDataConnection`既定の設定を持つオブジェクト。  
  
 2 番目のオーバーライドが新たに作成`CDataConnection`設定を指定するデータ接続オブジェクトと等価のオブジェクト。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)