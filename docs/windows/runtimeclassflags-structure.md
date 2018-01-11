---
title: "RuntimeClassFlags 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClassFlags
dev_langs: C++
helpviewer_keywords: RuntimeClassFlags structure
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85eb42c537845d86ce8cf3b1f20db7e9eeffe76f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags 構造体
インスタンスの型が含まれています、 [RuntimeClass](../windows/runtimeclass-class.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `flags`  
 A [RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)値。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constants"></a>パブリック定数  
  
|name|説明|  
|----------|-----------------|  
|[RuntimeClassFlags::value 定数](../windows/runtimeclassflags-value-constant.md)|含まれています、 [RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)値。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `RuntimeClassFlags`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)