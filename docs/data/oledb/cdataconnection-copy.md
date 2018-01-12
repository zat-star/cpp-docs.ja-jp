---
title: "Cdataconnection::copy |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
dev_langs: C++
helpviewer_keywords: Copy method
ms.assetid: a3dbd70d-36be-49e0-a527-00e3910a7a56
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eb2a5aa351afec2d5a379b6c8c0543e69db2f045
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdataconnectioncopy"></a>CDataConnection::Copy
既存のデータ接続のコピーを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      CDataConnection& Copy(   
   const CDataConnection & ds    
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ds`  
 [in]コピーする既存のデータ接続への参照。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)