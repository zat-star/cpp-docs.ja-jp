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
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87ee21022aa379820ced0463892be12ee0676d88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [CSimpleRow クラス](../../data/oledb/csimplerow-class.md)   
 [Csimplerow::releaserow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)