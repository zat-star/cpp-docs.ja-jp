---
title: "Criticalsectiontraits::unlock メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs: C++
helpviewer_keywords: Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 078ec4a1fa1af6c4660ff1171ab1b671ee9872f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock メソッド
指定されたクリティカル セクション オブジェクトの解放の所有権をサポートするように CriticalSection テンプレートを専門としています。  
  
## <a name="syntax"></a>構文  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cs`  
 クリティカル セクション オブジェクトへのポインター。  
  
## <a name="remarks"></a>コメント  
 *型*修飾子とは見なさ`typedef CRITICAL_SECTION* Type;`です。  
  
 詳細については、次を参照してください。 Windows API のマニュアルの「同期関数」セクションで"LeaveCriticalSection function"です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)