---
title: "Criticalsection::lock メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: af996faeebd0fcddb85993badd71ceecd32d494e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock メソッド
指定されたクリティカル セクション オブジェクトの所有権を待機します。 この関数は、呼び出し元のスレッドには、所有権が付与されるを返します。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cs`  
 クリティカル セクションのユーザーが指定したオブジェクトです。  
  
## <a name="return-value"></a>戻り値  
 現在の重要なセクションのロック解除に使用できるロック オブジェクト。  
  
## <a name="remarks"></a>コメント  
 最初の**ロック**関数が現在のクリティカル セクション オブジェクトに影響します。 2 番目**ロック**関数、ユーザー指定のクリティカル セクションに影響します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [CriticalSection クラス](../windows/criticalsection-class.md)