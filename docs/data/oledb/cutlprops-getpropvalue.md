---
title: "Cutlprops::getpropvalue |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
dev_langs:
- C++
helpviewer_keywords:
- GetPropValue method
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 819ce368f636f0470da17d5f3701601c8882f26f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cutlpropsgetpropvalue"></a>CUtlProps::GetPropValue
プロパティのセットからプロパティを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pguidPropSet`  
 [in]PropSet の GUID です。  
  
 `dwPropId`  
 [in]プロパティのインデックス。  
  
 `pvValue`  
 [out]新しいプロパティ値を含んでいるバリアントへのポインター。  
  
## <a name="return-value"></a>戻り値  
 `Failure` エラー発生時に、`S_OK`正常終了した場合。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)