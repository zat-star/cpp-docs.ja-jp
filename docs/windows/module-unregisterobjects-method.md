---
title: "Module::unregisterobjects メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::UnregisterObjects
dev_langs: C++
helpviewer_keywords: UnregisterObjects method
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d7e55afb96805fba6558cb900d2421a86379791c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="moduleunregisterobjects-method"></a>Module::UnregisterObjects メソッド
指定したモジュール内のオブジェクトの登録を解除して、他のアプリケーションがそれらに接続できないようにします。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT UnregisterObjects(  
   ModuleBase* module,  
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `module`  
 モジュールへのポインター。  
  
 `serverName`  
 この操作によって影響を受けるオブジェクトのサブセットを指定する修飾名。  
  
## <a name="return-value"></a>戻り値  
 この操作が成功した場合は S_OK、それ以外の場合、エラーの理由を示す hresult 値この操作に失敗しました。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>参照
 [Module クラス](../windows/module-class.md)