---
title: "Csimplerow::compare |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSimpleRow.Compare
- CSimpleRow::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8e49dcc0356c563312c0d73041ab412716694c1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="csimplerowcompare"></a>CSimpleRow::Compare
同じ行インスタンスを参照しているかを参照してください。 2 つの行を比較します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT Compare(   
   CSimpleRow* pRow    
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRow`  
 ポインター、`CSimpleRow`オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`値、通常`S_OK`を示す 2 つの行が同じ行インスタンスまたは**S_FALSE**、2 つの行を示すことが異なります。 参照してください[IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx)で、 *OLE DB プログラマーズ リファレンス*の考えられる他の戻り値。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [CSimpleRow クラス](../../data/oledb/csimplerow-class.md)   
 [Csimplerow::releaserow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)