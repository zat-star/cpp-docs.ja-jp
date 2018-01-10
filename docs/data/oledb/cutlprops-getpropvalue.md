---
title: "Cutlprops::getpropvalue |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
dev_langs: C++
helpviewer_keywords: GetPropValue method
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f6af9c8d909039927a7b4ad1f4840adac4353c97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cutlpropsgetpropvalue"></a>CUtlProps::GetPropValue
プロパティのセットからプロパティを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      OUT_OF_LINE HRESULT GetPropValue(  
   const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pguidPropSet`  
 [in]PropSet の GUID です。  
  
 `dwPropId`  
 [in]プロパティのインデックス。  
  
 `pvValue`  
 [out]新しいプロパティ値を含んでいるバリアントへのポインター。  
  
## <a name="return-value"></a>戻り値  
 `Failure`エラー発生時に、`S_OK`正常終了した場合。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)