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
ms.openlocfilehash: b6940c69e61f25abf3880190f58d83a995e2c84e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>関連項目
 [Mutex クラス](../windows/mutex-class1.md)