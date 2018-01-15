---
title: "Weakreference::setunknown メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference::SetUnknown
dev_langs: C++
helpviewer_keywords: SetUnknown method
ms.assetid: 5dddb9e3-a7c1-4195-8166-97c5ab6e972f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 682a80859c4a65854efbc5886eacefdf82cc5817
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="weakreferencesetunknown-method"></a>WeakReference::SetUnknown メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
void SetUnknown(  
   _In_ IUnknown* unk  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `unk`  
 ポインター、`IUnknown`オブジェクトのインターフェイスです。  
  
## <a name="remarks"></a>コメント  
 現在の強力な参照を設定`WeakReference`オブジェクトを指定されたインターフェイス ポインター。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照
[WeakReference クラス](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)