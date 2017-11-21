---
title: "SRWLockExclusiveTraits 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs: C++
helpviewer_keywords: SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 75a232816e73cf19550ca897660708cdf200784f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 構造体
SRWLock クラス排他ロックのモードでの一般的な特徴をについて説明します。  
  
## <a name="syntax"></a>構文  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Type`|ポインターのシノニム、 [SRWLOCK](../windows/srwlock-class.md)クラスです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SRWLockExclusiveTraits::GetInvalidValue メソッド](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|常に有効ではない SRWLockExclusiveTraits オブジェクトを取得します。|  
|[SRWLockExclusiveTraits::Unlock メソッド](../windows/srwlockexclusivetraits-unlock-method.md)|指定した SRWLock オブジェクトの排他的に制御を解放します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SRWLockExclusiveTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)