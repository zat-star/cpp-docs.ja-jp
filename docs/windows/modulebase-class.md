---
title: "ModuleBase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ModuleBase
dev_langs: C++
helpviewer_keywords: ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b02efe3ee61234b2439c1cbbae07827d6a879b2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="modulebase-class"></a>ModuleBase クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
class ModuleBase;  
```  
  
## <a name="remarks"></a>コメント  
 基本クラスを表す、[モジュール](../windows/module-class.md)クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ModuleBase::ModuleBase コンストラクター](../windows/modulebase-modulebase-constructor.md)|モジュール クラスのインスタンスを初期化します。|  
|[ModuleBase::~ModuleBase デストラクター](../windows/modulebase-tilde-modulebase-destructor.md)|モジュール クラスの現在のインスタンスの初期化を解除します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ModuleBase::DecrementObjectCount メソッド](../windows/modulebase-decrementobjectcount-method.md)|実装された場合、デクリメント オブジェクトの数によって追跡モジュール。|  
|[ModuleBase::IncrementObjectCount メソッド](../windows/modulebase-incrementobjectcount-method.md)|実装された場合、モジュールによって追跡されるオブジェクトの数をインクリメントします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ModuleBase`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)