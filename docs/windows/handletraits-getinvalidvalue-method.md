---
title: "Handletraits::getinvalidvalue メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: e95d2cc1-e70f-463f-8ff0-183cdeac1138
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ae903934d3f4002a416d382537185e9927405ea8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="handletraitsgetinvalidvalue-method"></a>HANDLETraits::GetInvalidValue メソッド
無効なハンドルを表します。  
  
## <a name="syntax"></a>構文  
  
```  
inline static HANDLE GetInvalidValue();  
```  
  
## <a name="return-value"></a>戻り値  
 INVALID_HANDLE_VALUE を常に返します。 (INVALID_HANDLE_VALUE は Windows によって定義されます)。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>参照  
 [HANDLETraits 構造体](../windows/handletraits-structure.md)