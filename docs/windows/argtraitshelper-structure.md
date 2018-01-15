---
title: "ArgTraitsHelper 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs: C++
helpviewer_keywords: ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31d9072ebf8c36453a74c75ff4a8997805d0973f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template<  
   typename TDelegateInterface  
>  
struct ArgTraitsHelper;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TDelegateInterface`  
 デリゲートのインターフェイスです。  
  
## <a name="remarks"></a>コメント  
 支援は、デリゲート引数の共通の特性を定義します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`methodType`|`decltype(&TDelegateInterface::Invoke)` と同義。|  
|`Traits`|`ArgTraits<methodType>` と同義。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|name|説明|  
|----------|-----------------|  
|[ArgTraitsHelper::args 定数](../windows/argtraitshelper-args-constant.md)|により、 [argtraits::args](../windows/argtraits-args-constant.md)デリゲート インターフェイスの呼び出しメソッドのパラメーターの数のカウントを保持します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ArgTraitsHelper`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)