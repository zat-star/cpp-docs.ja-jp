---
title: "Runtimeclass::getweakreference メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::GetWeakReference
dev_langs: C++
helpviewer_keywords: GetWeakReference method
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba87fe5097f9aff52b54770c1d438be2be425259
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassgetweakreference-method"></a>RuntimeClass::GetWeakReference メソッド
RuntimeClass、現在の弱い参照オブジェクトへのポインターを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   GetWeakReference  
)(_Deref_out_ IWeakReference **weakReference);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `weakReference`  
 この操作の完了時、弱い参照オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 常に S_OK です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)