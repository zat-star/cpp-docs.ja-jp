---
title: "Semaphoretraits::unlock メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
dev_langs: C++
helpviewer_keywords: Unlock method
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 819f7d7e4e4d5b6182da6172bd91a1e799379b52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="semaphoretraitsunlock-method"></a>SemaphoreTraits::Unlock メソッド
共有リソースのリリースのコントロールです。  
  
## <a name="syntax"></a>構文  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 セマフォ オブジェクトへのハンドルします。  
  
## <a name="remarks"></a>コメント  
 ロック解除の操作が成功しなかった場合、Unlock() は、エラーの原因を示すエラーを出力します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>参照  
 [SemaphoreTraits 構造体](../windows/semaphoretraits-structure.md)