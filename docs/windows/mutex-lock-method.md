---
title: "Mutex::lock メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
dev_langs: C++
helpviewer_keywords: Lock method
ms.assetid: 61d95072-b690-441e-a080-0bf94a733141
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e915dee2dbc7f3cc483df2e8135398a12d0fc369
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mutexlock-method"></a>Mutex::Lock メソッド
ミュー テックスを解放するまで、現在のオブジェクト、または、指定したハンドルに関連付けられているミュー テックス オブジェクト待機または指定されたタイムアウト期間が経過しました。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `milliseconds`  
 タイムアウト間隔 (ミリ秒単位)。 既定値は、無限で、無期限に待機します。  
  
 `h`  
 ミュー テックス オブジェクトのハンドル。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>参照
 [Mutex クラス](../windows/mutex-class1.md)