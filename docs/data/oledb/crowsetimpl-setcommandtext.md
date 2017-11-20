---
title: "Crowsetimpl::setcommandtext |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
dev_langs: C++
helpviewer_keywords: SetCommandText method
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a33af61311b9c202e5e0c68579ac4f21afd98f94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetimplsetcommandtext"></a>CRowsetImpl::SetCommandText
検証し、格納、 **DBID**2 つの文字列で $s ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md))。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT CRowsetBaseImpl::SetCommandText(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)