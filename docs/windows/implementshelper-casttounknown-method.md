---
title: "Implementshelper::casttounknown メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
dev_langs: C++
helpviewer_keywords: CastToUnknown method
ms.assetid: 5bcfcbaf-c75f-4d43-87b3-0d6838c838d9
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d07e716e085b7f10220f3ed3db4956ae7b1b3cf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="implementshelpercasttounknown-method"></a>ImplementsHelper::CastToUnknown メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>戻り値  
 基になる IUnknown インターフェイスへのポインター。  
  
## <a name="remarks"></a>コメント  
 現在の Implements 構造体の基になる IUnknown インターフェイスへのポインターを取得します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [ImplementsHelper 構造体](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)