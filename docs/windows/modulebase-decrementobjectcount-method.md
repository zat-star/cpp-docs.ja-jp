---
title: "Modulebase::decrementobjectcount メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
dev_langs: C++
helpviewer_keywords: DecrementObjectCount method
ms.assetid: a016fb07-a36e-40cd-bc7b-8f6e85e256e7
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 041638c582381be2c7d8b6c64063bd225df357fd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="modulebasedecrementobjectcount-method"></a>ModuleBase::DecrementObjectCount メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
virtual long DecrementObjectCount() = 0;  
```  
  
## <a name="return-value"></a>戻り値  
 デクリメント操作の前にカウントします。  
  
## <a name="remarks"></a>コメント  
 実装された場合、デクリメント オブジェクトの数によって追跡モジュール。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [ModuleBase クラス](../windows/modulebase-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)