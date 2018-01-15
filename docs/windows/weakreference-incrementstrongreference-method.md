---
title: "Weakreference::incrementstrongreference メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
dev_langs: C++
helpviewer_keywords: IncrementStrongReference method
ms.assetid: d0232426-a8cb-48b4-99d4-165de2d66cb9
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 355f1c07d8185c83fd92fa76810ef57547ebd599
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="weakreferenceincrementstrongreference-method"></a>WeakReference::IncrementStrongReference メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
ULONG IncrementStrongReference();  
```  
  
## <a name="return-value"></a>戻り値  
 インクリメントされた強力な参照カウントします。  
  
## <a name="remarks"></a>コメント  
 現在の WeakReference オブジェクトの厳密な参照カウントをインクリメントします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
[WeakReference クラス](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)