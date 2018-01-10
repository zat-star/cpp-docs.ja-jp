---
title: "Module::getactivationfactory メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::GetActivationFactory
dev_langs: C++
helpviewer_keywords: GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d5c5ca4d470f52ff9dde862cc99b10a3459cd0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory メソッド
モジュールのアクティベーション ファクトリを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pActivatibleClassId`  
 ランタイム クラスの IID です。  
  
 `ppIFactory`  
 指定したランタイム クラスの IActivationFactory します。  
  
 `serverName`  
 現在のモジュールでクラス ファクトリのサブセットの名前。 使用されるサーバー名を指定、 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)マクロ、または指定`nullptr`を既定のサーバー名を取得します。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、GetActivationFactory によって返された HRESULT のそれ以外の場合。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
[モジュール クラス](../windows/module-class.md) [ActivatableClass マクロ](../windows/activatableclass-macros.md)