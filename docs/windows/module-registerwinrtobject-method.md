---
title: "Module::registerwinrtobject メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::RegisterWinRTObject
dev_langs: C++
helpviewer_keywords: RegisterWinRTObject method
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 279a661fae0def63443c9a42d2f290b8d23fa2a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="moduleregisterwinrtobject-method"></a>Module::RegisterWinRTObject メソッド
他のアプリケーションがそれらに接続できるように、1 つまたは複数の Windows ランタイム オブジェクトを登録します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `serverName`  
 この操作によって影響を受けるオブジェクトのサブセットを指定する名前。  
  
 `activatableClassIds`  
 登録のアクティブ化可能な Clsid の配列。  
  
 `cookie`  
 登録済みのクラス オブジェクトを識別する値。 この値は、登録を取り消すを後で使用されます。  
  
 `count`  
 登録するオブジェクトの数。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、エラーの理由を示す CO_E_OBJISREG など hresult 値の操作に失敗しました。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>参照
 [Module クラス](../windows/module-class.md)