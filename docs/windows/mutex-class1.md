---
title: "ミュー テックス Class1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Mutex
dev_langs: C++
helpviewer_keywords: Mutex class
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c0e849d1fee7eca67f3b5765d31b54e0660eaa25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mutex-class1"></a>ミュー テックス Class1
共有リソースを排他的に制御する同期オブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class Mutex : public HandleT<HandleTraits::MutexTraits>  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|**SyncLock**|同期ロックをサポートするクラスのシノニムです。|  
  
### <a name="public-constructor"></a>パブリック コンス トラクター  
  
|name|説明|  
|----------|-----------------|  
|[Mutex::Mutex コンストラクター](../windows/mutex-mutex-constructor.md)|Mutex クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-members"></a>パブリック メンバー  
  
|name|説明|  
|----------|-----------------|  
|[Mutex::Lock メソッド](../windows/mutex-lock-method.md)|ミュー テックスを解放するまで、現在のオブジェクト、または、指定したハンドルに関連付けられているミュー テックス オブジェクト待機または指定されたタイムアウト期間が経過しました。|  
  
### <a name="public-operator"></a>パブリック演算子  
  
|name|説明|  
|----------|-----------------|  
|[Mutex::operator= 演算子](../windows/mutex-operator-assign-operator.md)|割り当て (移動)、指定されたミュー テックスは、現在のミュー テックス オブジェクトをオブジェクトです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Mutex`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)