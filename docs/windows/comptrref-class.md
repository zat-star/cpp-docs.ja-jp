---
title: "ComPtrRef クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b1bbe134f15fdba6863f1725cbcc7effcb6d94f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptrref-class"></a>ComPtrRef クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 A [ComPtr\<T >](../windows/comptr-class.md)型または型が、ComPtr によって表されるだけではなく、インターフェイスから派生します。  
  
## <a name="remarks"></a>コメント  
 ComPtr の型のオブジェクトへの参照を表す\<T > です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtrRef::ComPtrRef コンストラクター](../windows/comptrref-comptrref-constructor.md)|別の ComPtrRef オブジェクトを指定したポインターから ComPtrRef クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtrRef::GetAddressOf メソッド](../windows/comptrref-getaddressof-method.md)|現在の ComPtrRef オブジェクトによって表されるインターフェイスへのポインターのアドレスを取得します。|  
|[ComPtrRef::ReleaseAndGetAddressOf メソッド](../windows/comptrref-releaseandgetaddressof-method.md)|現在 ComPtrRef オブジェクトを削除ポインターを返しますのポインター-に-を - ComPtrRef オブジェクトによって表されるインターフェイスにします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtrRef::operator InterfaceType** 演算子](../windows/comptrref-operator-interfacetype-star-star-operator.md)|現在 ComPtrRef オブジェクトを削除ポインターを返しますのポインター-に-を - ComPtrRef オブジェクトによって表されるインターフェイスにします。|  
|[ComPtrRef::operator T* 演算子](../windows/comptrref-operator-t-star-operator.md)|値を返します、 [ptr _](../windows/comptrrefbase-ptr-data-member.md)現在 ComPtrRef オブジェクトのデータ メンバーです。|  
|[ComPtrRef::operator void** 演算子](../windows/comptrref-operator-void-star-star-operator.md)|現在の ComPtrRef オブジェクトを削除するには、ポインター-へのポインター - ComPtrRef オブジェクトによって表されるインターフェイスへのポインターをキャスト`void`、キャスト ポインターを返します。|  
|[ComPtrRef::operator* 演算子](../windows/comptrref-operator-star-operator.md)|現在の ComPtrRef オブジェクトによって表されるインターフェイスへのポインターを取得します。|  
|[ComPtrRef::operator== 演算子](../windows/comptrref-operator-equality-operator.md)|2 つの ComPtrRef オブジェクトが等しいかどうかを示します。|  
|[ComPtrRef::operator!= 演算子](../windows/comptrref-operator-inequality-operator.md)|2 つの ComPtrRef オブジェクトが等しくないかどうかを示します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)