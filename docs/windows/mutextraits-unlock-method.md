---
title: "Mutextraits::unlock メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
dev_langs: C++
helpviewer_keywords: Unlock method
ms.assetid: 7c4e5664-6d95-498a-95bb-d30b5e866c2c
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55c1252dfa1464d68b28f2da520b5ac8319ae096
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mutextraitsunlock-method"></a>MutexTraits::Unlock メソッド
共有リソースの排他的に制御を解放します。  
  
## <a name="syntax"></a>構文  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 ミュー テックス オブジェクトへのハンドルします。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>参照  
 [MutexTraits 構造体](../windows/mutextraits-structure.md)