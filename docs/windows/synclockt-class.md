---
title: "SyncLockT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3f3a9794f7b00a2029f6706db3a846ba127a4d5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="synclockt-class"></a>SyncLockT クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `SyncTraits`  
 この型は、リソースの所有権を取得できます。  
  
## <a name="remarks"></a>コメント  
 排他的に実行できる型を表すまたはリソースの所有権を共有します。  
  
 SyncLockT クラスが使用されるなどの実装に役立つ、 [SRWLock](../windows/srwlock-class.md)クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockT::SyncLockT コンストラクター](../windows/synclockt-synclockt-constructor.md)|SyncLockT クラスの新しいインスタンスを初期化します。|  
|[SyncLockT::~SyncLockT デストラクター](../windows/synclockt-tilde-synclockt-destructor.md)|SyncLockT クラスのインスタンスの初期化を解除します。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockT::SyncLockT コンストラクター](../windows/synclockt-synclockt-constructor.md)|SyncLockT クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockT::IsLocked メソッド](../windows/synclockt-islocked-method.md)|SyncLockT、現在、リソースを所有しているかどうかを示しますSyncLockT オブジェクトは、つまり、*ロック*です。|  
|[SyncLockT::Unlock メソッド](../windows/synclockt-unlock-method.md)|存在する場合は、現在の SyncLockT オブジェクトによって保持されているリソースの制御を解放します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[SyncLockT::sync_ データ メンバー](../windows/synclockt-sync-data-member.md)|SyncLockT クラスによって表される、基になるリソースを保持します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SyncLockT`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Wrappers::Details Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock クラス](../windows/srwlock-class.md)