---
title: "Crowsetimpl::getcommandfromid |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
dev_langs: C++
helpviewer_keywords: GetCommandFromID method
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e75fbd00b6ee2e4a19cf0fe39d0bcda9f0314f8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetimplgetcommandfromid"></a>CRowsetImpl::GetCommandFromID
いずれかまたは両方のパラメーターには、文字列値が含まれている場合を確認するためのチェックは、データ メンバーに文字列値をコピー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT CRowsetBaseImpl::GetCommandFromID(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pTableID`  
 [in]ポインター、 **DBID**テーブルの ID を表す  
  
 `pIndexID`  
 [in]ポインター、 **DBID**インデックスの ID を表す  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、静的キャスト`CRowsetImpl`データ メンバーを設定する[m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md)です。 既定では、このメソッドは、いずれかまたは両方のパラメーターに文字列値が含まれているかどうかを確認します。 文字列値を含まれている場合、このメソッドは、データ メンバーに文字列値をコピーします。 このシグネチャを持つメソッドを配置することによって、 `CRowsetImpl`-派生クラスでは、基底の実装ではなく、メソッドが呼び出されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)