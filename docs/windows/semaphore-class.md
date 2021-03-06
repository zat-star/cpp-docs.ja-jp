---
title: "クラスのセマフォ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore class
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60373c12220fce57672389b98455a123990f3c93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="semaphore-class"></a>Semaphore クラス
ユーザー数に制限をサポートできる共有リソースを制御する同期オブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```  
  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`SyncLock`|同期ロックをサポートするクラスのシノニムです。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Semaphore::Semaphore コンストラクター](../windows/semaphore-semaphore-constructor.md)|Semaphore クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[InvokeHelper::Invoke メソッド](../windows/invokehelper-invoke-method.md)|指定した数の引数を含むシグネチャを持つイベント ハンドラーを呼び出します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[Semaphore::Lock メソッド](../windows/semaphore-lock-method.md)|指定されたタイムアウト期間が経過したか、現在のオブジェクトか、指定したハンドルに関連付けられているオブジェクトになるまで待機がシグナル状態になっています。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[Semaphore::operator= 演算子](../windows/semaphore-operator-assign-operator.md)|セマフォ オブジェクトから指定したハンドルを現在のセマフォ オブジェクトに移動します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Semaphore`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)