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
ms.openlocfilehash: 9a0406991fca38b586b27c7f8a0d01cf2e4689af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)