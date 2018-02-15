---
title: "Carrayrowset: |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CArrayRowset::operator[]
- CArrayRowset.operator[]
dev_langs:
- C++
helpviewer_keywords:
- operator [], arrays
- '[] operator'
- operator[], arrays
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0921ad4c574c496656ec616d1d569158c596c5ad
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="carrayrowsetoperator"></a>CArrayRowset::operator
行セット内の行にアクセスするためには、配列に似た構文を提供します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      TAccessor  
      & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TAccessor`  
 行セットに格納されているアクセサーの種類を指定するテンプレート パラメーター。  
  
 `nRow`  
 [in](配列) にアクセスする、行の数です。  
  
## <a name="return-value"></a>戻り値  
 要求された行の内容。  
  
## <a name="remarks"></a>コメント  
 場合`nRow`行セット内の行の数を超えると、例外がスローされます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CArrayRowset クラス](../../data/oledb/carrayrowset-class.md)