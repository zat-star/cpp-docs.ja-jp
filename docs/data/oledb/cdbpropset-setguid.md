---
title: "Cdbpropset::setguid |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
dev_langs: C++
helpviewer_keywords:
- SetGUID method
- AddProperty method
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ca1d8b4b6ee46f7debb52a6ebd0bbfbeded1fede
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cdbpropsetsetguid"></a>CDBPropSet::SetGUID
セット、**コンス トラクターは**フィールドで、 **DBPROPSET**構造体。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 [in]設定に使用される GUID、**コンス トラクターは**のフィールド、 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)構造体。  
  
## <a name="remarks"></a>コメント  
 このフィールドを設定することができます、[コンス トラクター](../../data/oledb/cdbpropset-cdbpropset.md)もします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDBPropSet クラス](../../data/oledb/cdbpropset-class.md)