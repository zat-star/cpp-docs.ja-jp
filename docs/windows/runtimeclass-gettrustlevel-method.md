---
title: "Runtimeclass::gettrustlevel メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 89a00c052ec1191cd57057f52401954397169b88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassgettrustlevel-method"></a>RuntimeClass::GetTrustLevel メソッド

RuntimeClass、現在の信頼レベルを取得します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>パラメーター

*trustLvl*  
この操作の完了時、RuntimeClass、現在の信頼レベル。

## <a name="return-value"></a>戻り値

常に S_OK です。

## <a name="remarks"></a>コメント

Assert エラーが出力された場合 &#95; #95 です。WRL_STRICT &#95; #95または (& m); #95 &#95;です。WRL_FORCE_INSPECTABLE_CLASS_MACRO &#95; #95定義されていません。

## <a name="requirements"></a>必要条件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[RuntimeClass クラス](../windows/runtimeclass-class.md)