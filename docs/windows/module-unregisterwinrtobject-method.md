---
title: "Module::unregisterwinrtobject メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::UnregisterWinRTObject
dev_langs: C++
helpviewer_keywords: UnregisterWinRTObject method
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1c5f1fe4da0d9c0699ab7205ad7823ca8d506dd2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="moduleunregisterwinrtobject-method"></a>Module::UnregisterWinRTObject メソッド
他のアプリケーションがそれらに接続できないように、1 つまたは複数の Windows ランタイム オブジェクトを登録解除します。  
  
## <a name="syntax"></a>構文  
  
```  
virtual HRESULT UnregisterWinRTObject(  
   unsigned int,  
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cookie`  
 登録を取り消すクラス オブジェクトを識別する値へのポインター。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)