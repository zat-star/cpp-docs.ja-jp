---
title: "Mutex::mutex コンス トラクター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
dev_langs: C++
helpviewer_keywords: Mutex, constructor
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a07aeac0f8d139f71bdbe2473dc8eabf7e14ec2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mutexmutex-constructor"></a>Mutex::Mutex コンストラクター
Mutex クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
explicit Mutex(  
   HANDLE h  
);  
  
Mutex(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 ハンドル、またはハンドル、ミュー テックス オブジェクトへの右辺値参照。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターは、指定されたハンドルからミュー テックス オブジェクトを初期化します。 2 番目のコンス トラクターは指定のハンドルからミュー テックス オブジェクトを初期化し、現在ミュー テックス オブジェクトにミュー テックスの所有権を移動します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>参照
 [Mutex クラス](../windows/mutex-class1.md)