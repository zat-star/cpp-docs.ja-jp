---
title: "Cutlprops::setpropvalue |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
dev_langs: C++
helpviewer_keywords: SetPropValue method
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 389aa22addcc293131c5b4a1c60aa2601b354f3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cutlpropssetpropvalue"></a>CUtlProps::SetPropValue
プロパティ セットのプロパティを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT SetPropValue(  
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
 [in]新しいプロパティ値を含んでいるバリアントへのポインター。  
  
## <a name="return-value"></a>戻り値  
 `Failure`エラー発生時に、`S_OK`正常終了した場合。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)