---
title: "Asyncbase::continueasyncoperation メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
dev_langs: C++
helpviewer_keywords: ContinueAsyncOperation method
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 976ee601e836bbabbfbf65beca41f6fbd687cebb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasecontinueasyncoperation-method"></a>AsyncBase::ContinueAsyncOperation メソッド
非同期操作が処理を続行する必要がありますまたは中止するかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>戻り値  
 `true`非同期操作の現在の状態がある場合*開始*、つまり、操作を続行する必要があります。 それ以外の場合、 `false`、つまり、操作を停止する必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)