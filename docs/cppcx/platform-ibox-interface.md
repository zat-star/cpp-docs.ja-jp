---
title: "Platform::ibox インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs: C++
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a86eca75bb5470585ba68fe3b7fcdb55c861434
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="platformibox-interface"></a>Platform::IBox インターフェイス
[Platform::IBox](../cppcx/platform-ibox-interface.md) のインターフェイスは `Windows::Foundation::IReference` のインターフェイスの C++ の名前です。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ボックス化された値の型。  
  
### <a name="remarks"></a>コメント  
 `IBox<T>` インターフェイスは、「 [値クラスと構造体 (C++/CX)](../cppcx/value-classes-and-structs-c-cx.md)」で説明されているように、主に内部的に使用され、null 許容値型を表します。 インターフェイスは、 `Object^`型のパラメーターを受け取る C++ のメソッドに渡される値の型をボックス化するためにも使用されます。 入力パラメーターは `IBox<SomeValueType>`として明示的に宣言できます。 例については、次を参照してください。[ボックス化](../cppcx/boxing-c-cx.md)です。  
  
### <a name="requirements"></a>必要条件  
  
### <a name="members"></a>メンバー  
 `Platform::IBox` インターフェイスは [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md) インターフェイスから継承されます。 `IBox` には、次に示すメンバーがあります。  
  
 **プロパティ**  
  
|メソッド|説明|  
|------------|-----------------|  
|[値](#value)|以前にこの `IBox` インスタンスに格納されていたことがあり、ボックス化が解除されている値を返します。|  

## <a name="value"></a>Ibox::value プロパティ
このオブジェクトに元から格納されていた値を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 ボックス化された値の型。  
  
### <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 このオブジェクトに元から格納されていた値を返します。  
  
### <a name="remarks"></a>コメント  
 例については、次を参照してください。[ボックス化](../cppcx/boxing-c-cx.md)です。  
  
  
## <a name="see-also"></a>参照  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)