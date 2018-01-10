---
title: "Crowsetimpl::validatecommandid |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl.ValidateCommandID
- CRowsetImpl::ValidateCommandID
dev_langs: C++
helpviewer_keywords: ValidateCommandID method
ms.assetid: cdde6088-41bc-4b8f-a32b-f36f7d9b5ec0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1e59ca9d64ea71edcf52d151a592848434a109f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetimplvalidatecommandid"></a>CRowsetImpl::ValidateCommandID
いずれかを参照またはその両方をチェック**DBID**s が、文字列値を含めるし、場合は、そのデータ メンバーにコピー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT CRowsetBaseImpl::ValidateCommandID(  
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
 このメソッドは、静的キャスト`CRowsetImpl`をそのデータ メンバーを設定する[m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md)です。 既定では、このメソッドは参照のいずれかまたは両方をチェック**DBID**s が、文字列値を含めるし、場合は、そのデータ メンバーにコピーします。 このシグネチャを持つメソッドを配置することによって、 `CRowsetImpl`-派生クラスでは、基底の実装ではなく、メソッドが呼び出されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)