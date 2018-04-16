---
title: "Cutlprops::isvalidvalue |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
dev_langs:
- C++
helpviewer_keywords:
- IsValidValue method
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bd02ef7c27926b2be99ed900b82d53c77d8d6dd0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cutlpropsisvalidvalue"></a>CUtlProps::IsValidValue
プロパティを設定する前に、値を検証するために使用します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,  
   DBPROP* pDBProp);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `iCurSet`  
 配列のインデックスのプロパティ セットです。1 つのプロパティ セットがある場合は 0 します。  
  
 `pDBProp`  
 プロパティ ID と新しい値、 [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx)構造体。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。 既定の戻り値は`S_OK`します。  
  
## <a name="remarks"></a>コメント  
 使用してプロパティを設定しようとしている値で実行する検証ルーチンがある場合は、この関数をオーバーライドする必要があります。 たとえば、検証するでした**DBPROP_AUTH_PASSWORD**有効な値を決定するパスワード テーブルに対してです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)