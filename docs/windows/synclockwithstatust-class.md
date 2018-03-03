---
title: "SyncLockWithStatusT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT class
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b4b007acd6e6b9272a4fc7bb256d302cafeb75c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `SyncTraits`  
 排他的に実行できる型またはリソースの所有権を共有します。  
  
## <a name="remarks"></a>コメント  
 排他的に実行できる型を表すまたはリソースの所有権を共有します。  
  
 SyncLockWithStatusT クラスが実装に使用される、[ミュー テックス](../windows/mutex-class1.md)と[セマフォ](../windows/semaphore-class.md)クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT コンストラクター](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|SyncLockWithStatusT クラスの新しいインスタンスを初期化します。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT コンストラクター](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|SyncLockWithStatusT クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::GetStatus メソッド](../windows/synclockwithstatust-getstatus-method.md)|SyncLockWithStatusT、現在の待機の状態を取得します。|  
|[SyncLockWithStatusT::IsLocked メソッド](../windows/synclockwithstatust-islocked-method.md)|SyncLockWithStatusT、現在、リソースを所有しているかどうかを示しますSyncLockWithStatusT オブジェクトは、つまり、*ロック*です。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::status_ データ メンバー](../windows/synclockwithstatust-status-data-member.md)|保持しますが、基になる結果にロック操作の後に操作を待機するオブジェクトは、現在の SyncLockWithStatusT オブジェクトに基づいています。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Wrappers::Details 名前空間](../windows/microsoft-wrl-wrappers-details-namespace.md)