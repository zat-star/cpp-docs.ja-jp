---
title: "HStringReference クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
dev_langs:
- C++
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97900bd44dfdcede187b20b181c64d235eac60fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreference-class"></a>HStringReference クラス
既存の文字列から作成された HSTRING を表します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
class HStringReference;  
```  
  
## <a name="remarks"></a>コメント  
 新しい HSTRING のバッキング バッファーの有効期間は、Windows ランタイムによって管理されていません。 呼び出し元はソース文字列をスタック フレームに割り当てることで、ヒープ割り当てを回避し、メモリ リークのリスクを排除します。 また、呼び出し元はアタッチ済みの HSTRING の有効期間中にソース文字列が変更されないことを確認する必要があります。 詳細については、次を参照してください。 [WindowsCreateStringReference 関数](http://msdn.microsoft.com/en-us/0361bb7e-da49-4289-a93e-de7aab8712ac)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[HStringReference::HStringReference コンストラクター](../windows/hstringreference-hstringreference-constructor.md)|HStringReference クラスの新しいインスタンスを初期化します。|  
  
### <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|[HStringReference::CopyTo メソッド](../windows/hstringreference-copyto-method.md)|現在の HStringReference オブジェクトを HSTRING オブジェクトにコピーします。|  
|[HStringReference::Get メソッド](../windows/hstringreference-get-method.md)|基になる HSTRING ハンドルの値を取得します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[HStringReference::Operator= 演算子](../windows/hstringreference-operator-assign-operator.md)|別の HStringReference オブジェクトの値を現在の HStringReference オブジェクトに移動します。|  
|[HStringReference::Operator== 演算子](../windows/hstringreference-operator-equality-operator.md)|2 つのパラメーターが等しいかどうかを示します。|  
|[HStringReference::Operator!= 演算子](../windows/hstringreference-operator-inequality-operator.md)|2 つのパラメーターが異なるかどうかを示します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `HStringReference`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)