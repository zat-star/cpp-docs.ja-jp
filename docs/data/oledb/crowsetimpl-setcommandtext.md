---
title: "Crowsetimpl::setcommandtext |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
dev_langs:
- C++
helpviewer_keywords:
- SetCommandText method
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18508fed21bb459f4b4c6a653437b1546c8d1a2b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetimplsetcommandtext"></a>CRowsetImpl::SetCommandText
検証し、格納、 **DBID**2 つの文字列で $s ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md))。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pTableID`  
 [in]ポインター、 **DBID**テーブル ID を表す  
  
 `pIndexID`  
 [in]ポインター、 **DBID**インデックス ID を表す  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 **SetCommentText**メソッドによって呼び出されます`CreateRowset`、テンプレート化のメソッドを静的な`IOpenRowsetImpl`します。  
  
 このメソッドは、呼び出すことによって作業を委任[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)と[GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) upcasted ポインターを使用します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)