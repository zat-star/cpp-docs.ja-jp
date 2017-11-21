---
title: "Caccessorbase::gethaccessor |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
dev_langs: C++
helpviewer_keywords: GetHAccessor method
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ba60cb6dd108b0ea451baabf5941caeead11a42f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="caccessorbasegethaccessor"></a>CAccessorBase::GetHAccessor
指定されたアクセサーのアクセサー ハンドルを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HACCESSOR GetHAccessor(  
   ULONG nAccessor   
) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nAccessor`  
 [in]アクセサーのゼロ オフセットの数です。  
  
## <a name="return-value"></a>戻り値  
 アクセサーのハンドルです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CAccessorBase クラス](../../data/oledb/caccessorbase-class.md)