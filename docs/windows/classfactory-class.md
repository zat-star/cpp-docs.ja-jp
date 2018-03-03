---
title: "ClassFactory クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
dev_langs:
- C++
helpviewer_keywords:
- ClassFactory class
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c37c016809d31fcb072f23768e9f54313331016
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="classfactory-class"></a>ClassFactory クラス
IClassFactory インターフェイスの基本機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ClassFactory : public Details::RuntimeClass<  
   typename Details::InterfaceListHelper<IClassFactory,   
   I0,   
   I1,   
   I2,   
   Details::Nil>::TypeT,   
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,   
      false>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `I0`  
 0 番目のインターフェイスです。  
  
 `I1`  
 最初のインターフェイスです。  
  
 `I2`  
 2 番目のインターフェイスです。  
  
## <a name="remarks"></a>コメント  
 利用`ClassFactory`工場出荷時のユーザー定義の実装を提供します。  
  
 次のプログラミング パターンが使用する方法を示します、 [Implements](../windows/implements-structure.md)構造体をクラス ファクトリで複数の 3 つのインターフェイスを指定します。  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ClassFactory::ClassFactory コンストラクター](../windows/classfactory-classfactory-constructor.md)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ClassFactory::AddRef メソッド](../windows/classfactory-addref-method.md)|ClassFactory、現在の参照カウントをインクリメントします。|  
|[ClassFactory::LockServer メソッド](../windows/classfactory-lockserver-method.md)|現在の ClassFactory オブジェクトによって追跡されているオブジェクトの基になる数ずつインクリメントまたはデクリメントします。|  
|[ClassFactory::QueryInterface メソッド](../windows/classfactory-queryinterface-method.md)|パラメーターで指定されたインターフェイスへのポインターを取得します。|  
|[ClassFactory::Release メソッド](../windows/classfactory-release-method.md)|現在の ClassFactory オブジェクト、参照カウントをデクリメントします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ClassFactory`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Microsoft::wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)