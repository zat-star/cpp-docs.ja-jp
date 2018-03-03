---
title: "GetModuleBase 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
dev_langs:
- C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19f575705b1f8680a68e9100f20be66ca22ec87a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="getmodulebase-function"></a>GetModuleBase 関数
取得、 [ModuleBase](../windows/modulebase-class.md)の参照カウントをインクリメントおよびデクリメントするため、ポインター、 [RuntimeClass](../windows/runtimeclass-class.md)オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline Details::ModuleBase* GetModuleBase() throw()  
```  
  
## <a name="return-value"></a>戻り値  
 ポインター、`ModuleBase`オブジェクト。  
  
## <a name="remarks"></a>コメント  
 この関数は、内部的に使用をインクリメントおよびデクリメント オブジェクト参照をカウントします。  
  
 この関数を使用するには呼び出すことによって参照カウントを制御する[modulebase::incrementobjectcount](../windows/modulebase-incrementobjectcount-method.md)と[modulebase::decrementobjectcount](../windows/modulebase-decrementobjectcount-method.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)