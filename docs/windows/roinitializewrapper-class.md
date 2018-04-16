---
title: "RoInitializeWrapper クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5f6330c78a6bbac5f14e94c253f05515e3d29575
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper クラス
Windows ランタイムを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
class RoInitializeWrapper  
```  
  
## <a name="remarks"></a>コメント  
 RoInitializeWrapper は、利便性のための Windows ランタイムを初期化し、操作が成功したかどうかを示す HRESULT を返します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[RoInitializeWrapper::RoInitializeWrapper コンストラクター](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|RoInitializeWrapper クラスの新しいインスタンスを初期化します。|  
|[RoInitializeWrapper::~RoInitializeWrapper デストラクター](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|RoInitializeWrapper クラスの現在のインスタンスを破棄します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[RoInitializeWrapper::HRESULT() 演算子](../windows/roinitializewrapper-hresult-parens-operator.md)|RoInitializeWrapper コンス トラクターが生成された HRESULT を取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `RoInitializeWrapper`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)