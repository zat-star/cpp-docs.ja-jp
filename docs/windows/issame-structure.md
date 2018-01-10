---
title: "IsSame 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::IsSame
dev_langs: C++
helpviewer_keywords: IsSame structure
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bae4ecb6f03b7b1cdb0fae02f211dd613e7c39d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="issame-structure"></a>IsSame 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename T1,  
   typename T2  
>  
struct IsSame;  
template <  
   typename T1  
>  
struct IsSame<T1, T1>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T1`  
 型。  
  
 `T2`  
 別の型。  
  
## <a name="remarks"></a>コメント  
 1 つには、型を指定するかどうかが同じ別のテストには、種類が指定されました。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constants"></a>パブリック定数  
  
|name|説明|  
|----------|-----------------|  
|[IsSame::value 定数](../windows/issame-value-constant.md)|1 つの型が別のと同じかどうかを示します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IsSame`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)