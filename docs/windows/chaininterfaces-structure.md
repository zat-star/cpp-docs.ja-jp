---
title: "ChainInterfaces 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
dev_langs:
- C++
helpviewer_keywords:
- ChainInterfaces structure
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e9417b3950e4df98ed4e13ea1bb40e76c383868e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces 構造体
一連のインターフェイス ID に適用できる検証および初期化関数を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename I0,  
   typename I1,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct ChainInterfaces : I0;  
template <  
   typename DerivedType,  
   typename BaseType,  
   bool hasImplements,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8,  
   typename I9  
>  
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `I0`  
 (必須)インターフェイス ID 0 です。  
  
 `I1`  
 (必須)ID 1 のインターフェイスです。  
  
 `I2`  
 (省略可能)インターフェイス ID は 2 です。  
  
 `I3`  
 (省略可能)ID 3 のインターフェイスです。  
  
 `I4`  
 (省略可能)インターフェイス ID 4 です。  
  
 `I5`  
 (省略可能)ID 5 のインターフェイスです。  
  
 `I6`  
 (省略可能)インターフェイス ID 6 です。  
  
 `I7`  
 (省略可能)インターフェイス ID 7 です。  
  
 `I8`  
 (省略可能)インターフェイス ID 8 です。  
  
 `I9`  
 (省略可能)インターフェイス ID 9 です。  
  
 `DerivedType`  
 派生型です。  
  
 `BaseType`  
 派生型の基本データ型。  
  
 `hasImplements`  
 ブール値を`true`、使用することはできません、 [MixIn](../windows/mixin-structure.md)クラスから派生していないを持つ構造体、[を実装](../windows/implements-structure.md)構造です。  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ChainInterfaces::CanCastTo メソッド](../windows/chaininterfaces-cancastto-method.md)|指定されたインターフェイス ID を ChainInterface テンプレート パラメーターで定義された特殊化の各にキャストできるかどうかを示します。|  
|[ChainInterfaces::CastToUnknown メソッド](../windows/chaininterfaces-casttounknown-method.md)|によって定義された型のインターフェイス ポインターにキャスト、 `I0` IUnknown へのポインターをテンプレート パラメーター。|  
|[ChainInterfaces::FillArrayWithIid メソッド](../windows/chaininterfaces-fillarraywithiid-method.md)|ストアで定義されているインターフェイス ID、`I0`インターフェイス Id の指定した配列内の指定した場所にテンプレート パラメーター。|  
|[ChainInterfaces::Verify メソッド](../windows/chaininterfaces-verify-method.md)|テンプレート パラメーターによって、各インターフェイスが定義されていることを確認`I0`を通じて`I9`IUnknown や、IInspectable から継承`I0`から継承`I1`を通じて`I9`です。|  
  
### <a name="protected-constants"></a>プロテクト コンス トラクター  
  
|name|説明|  
|----------|-----------------|  
|[ChainInterfaces::IidCount 定数](../windows/chaininterfaces-iidcount-constant.md)|インターフェイスのテンプレート パラメーターで指定されたインターフェイスに含まれる Id の合計数`I0`を通じて`I9`です。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `I0`  
  
 `ChainInterfaces`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)