---
title: "DerefHelper 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::Details::DerefHelper
dev_langs: C++
helpviewer_keywords: DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f71a49f6fb240aa6ed305e966ecac0740ffec665
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="derefhelper-structure"></a>DerefHelper 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename T  
>  
struct DerefHelper;  
  
template <  
   typename T  
>  
struct DerefHelper<T*>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 テンプレート パラメーター。  
  
## <a name="remarks"></a>コメント  
 指すポインターが逆参照を表す、`T*`テンプレート パラメーター。  
  
 DerefHelper がなど、式で使用する:`ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`DerefType`|逆参照のテンプレート パラメーターの識別子の`T*`します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `DerefHelper`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** async.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)