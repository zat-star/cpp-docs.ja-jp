---
title: "Criticalsectiontraits::getinvalidvalue メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs: C++
helpviewer_keywords: GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55bf0dedc286ed5dac8f48c7e8a2d43aa7741eff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue メソッド
CriticalSection テンプレートを特化できるように、テンプレートは、常に有効です。  
  
## <a name="syntax"></a>構文  
  
```  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>戻り値  
 常に無効な重要なセクションへのポインターを返します。  
  
## <a name="remarks"></a>コメント  
 *型*修飾子とは見なさ`typedef CRITICAL_SECTION* Type;`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>参照  
 [CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)