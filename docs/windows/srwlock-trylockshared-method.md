---
title: "Srwlock::trylockshared メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs:
- C++
helpviewer_keywords:
- TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c36657b5c732055260dc77471e109961a66c144
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared メソッド
現在または指定した SRWLock オブジェクトの共有モードで SRWLock オブジェクトを取得しようとしています。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lock`  
 SRWLock オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、共有モードと呼び出し元のスレッドで SRWLock オブジェクトは、ロックの所有権を取得します。 それ以外の場合、SRWLock オブジェクトの状態が無効です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [SRWLock クラス](../windows/srwlock-class.md)