---
title: "Module::releasenotifier:: メソッドを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
dev_langs:
- C++
helpviewer_keywords:
- Invoke method
ms.assetid: f62686fe-74bf-482b-a46b-6a3c09b80e7e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e2eff342264bf7866a4eb95147bca7ce41acb997
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="modulereleasenotifierinvoke-method"></a>Module::ReleaseNotifier::Invoke メソッド
実装された場合、モジュール内の最後のオブジェクトが離されると、イベント ハンドラーを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
virtual void Invoke() = 0;  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Module::ReleaseNotifier クラス](../windows/module-releasenotifier-class.md)