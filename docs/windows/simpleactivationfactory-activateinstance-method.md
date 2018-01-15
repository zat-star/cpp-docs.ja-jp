---
title: "Simpleactivationfactory::activateinstance メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs: C++
helpviewer_keywords: ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bbe9d8c215674f087c6e0fa4ca7f3439fb89b78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactoryactivateinstance-method"></a>SimpleActivationFactory::ActivateInstance メソッド

指定されたインターフェイスのインスタンスを作成します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>パラメーター

*ppvObject*  
この操作の完了時で指定されたオブジェクトのインスタンスへのポインター、`Base`クラス テンプレート パラメーター。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>コメント

場合 &#95; &#95;です。WRL_STRICT &#95; #95定義されている、assert エラーが発生、クラス テンプレート パラメーターに指定された基本クラスから派生していない場合[RuntimeClass](../windows/runtimeclass-class.md)、WinRt または WinRtClassicComMix で構成されていない、または[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。

## <a name="requirements"></a>必要条件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)