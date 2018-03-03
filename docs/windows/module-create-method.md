---
title: "Module::create メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1f025c446dd6a7dab9b37d126d65e640a02b939b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="modulecreate-method"></a>Module::Create メソッド
モジュールのインスタンスを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW static Module& Create();  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   _In_ T* object,  
   _In_ void (T::* method)()  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 モジュールの種類。  
  
 `callback`  
 モジュールの最後のインスタンスのオブジェクトがリリースされたときに呼び出されます。  
  
 `object`  
 `object`と`method`パラメーターの組み合わせで使用されます。 場合に、ポイント最後のインスタンス オブジェクト、モジュール内の最後のインスタンス オブジェクトを解放します。  
  
 `method`  
 `object`と`method`パラメーターの組み合わせで使用されます。 モジュールの最後のインスタンス オブジェクトが離されると、最後のインスタンス オブジェクトのメソッドを指します。  
  
## <a name="return-value"></a>戻り値  
 モジュールへの参照。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
[Module クラス](../windows/module-class.md)

 