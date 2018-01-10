---
title: "SRWLockSharedTraits 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
dev_langs: C++
helpviewer_keywords: SRWLockSharedTraits structure
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cadf94f1d336de7bac13572a045e7ac8487013cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 構造体
SRWLock クラス共有ロック モードでの一般的な特徴をについて説明します。  
  
## <a name="syntax"></a>構文  
  
```  
struct SRWLockSharedTraits;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Type`|ポインターのシノニム、 [SRWLOCK](../windows/srwlock-class.md)クラスです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SRWLockSharedTraits::GetInvalidValue メソッド](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|常に有効ではない SRWLockSharedTraits オブジェクトを取得します。|  
|[SRWLockSharedTraits::Unlock メソッド](../windows/srwlocksharedtraits-unlock-method.md)|指定した SRWLock オブジェクトの排他的に制御を解放します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)