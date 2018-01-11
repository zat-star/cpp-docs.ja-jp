---
title: "Simpleactivationfactory::getruntimeclassname メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
dev_langs: C++
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73431c7a0f719579caf3df146b69dd8d7248d0a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactorygetruntimeclassname-method"></a>SimpleActivationFactory::GetRuntimeClassName メソッド

によって指定されたクラスのインスタンスのランタイム クラス名を取得、`Base`クラス テンプレート パラメーター。

## <a name="syntax"></a>構文

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>パラメーター

*runtimeName*  
この操作の完了時、ランタイム クラス名。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>コメント

場合 &#95; &#95;です。WRL_STRICT &#95; #95定義されている、assert エラーが発生して、クラスが指定されている場合、`Base`から派生したクラス テンプレート パラメーターはありません[RuntimeClass](../windows/runtimeclass-class.md)、WinRt または WinRtClassicComMix で構成されていない、または[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。

## <a name="requirements"></a>必要条件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)