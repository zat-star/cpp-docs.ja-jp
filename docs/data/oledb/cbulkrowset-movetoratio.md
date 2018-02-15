---
title: "Cbulkrowset::movetoratio |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
dev_langs:
- C++
helpviewer_keywords:
- MoveToRatio method
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e680a7e562aaf3e0b1fcb1ee33ea0eb558f62069
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cbulkrowsetmovetoratio"></a>CBulkRowset::MoveToRatio
行セット内の小数部の位置から始まる行がフェッチされます。  
  
## <a name="syntax"></a>構文  
  
```
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator)throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nNumerator`  
 [in]データをフェッチするための小数部の位置を決定するための分子です。  
  
 `nDenominator`  
 [in]分母では、元のデータをフェッチする小数部の位置を決定するために使用します。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 `MoveToRatio` 次の数式に従ってほぼ行がフェッチされます。  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 ここで`RowsetSize`行数で指定された、行セットのサイズです。 この式の精度は、特定のプロバイダーによって異なります。 詳細については、「 [::getrowsatratio](https://msdn.microsoft.com/en-us/library/ms709602.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CBulkRowset クラス](../../data/oledb/cbulkrowset-class.md)