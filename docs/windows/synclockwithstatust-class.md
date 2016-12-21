---
title: "SyncLockWithStatusT クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockWithStatusT クラス"
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockWithStatusT クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 排他が実行できる型またはリソースの所有権を共有します。  
  
## <a name="remarks"></a>コメント  
 排他が実行できる型を表すか、リソースの所有権を共有します。  
  
 SyncLockWithStatusT クラスを実装するため、 [ミュー テックス](../Topic/Mutex%20Class1.md) と [セマフォ](../windows/semaphore-class.md) クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Synclockwithstatust::synclockwithstatust コンス トラクター](../Topic/SyncLockWithStatusT::SyncLockWithStatusT%20Constructor.md)|SyncLockWithStatusT クラスの新しいインスタンスを初期化します。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Synclockwithstatust::synclockwithstatust コンス トラクター](../Topic/SyncLockWithStatusT::SyncLockWithStatusT%20Constructor.md)|SyncLockWithStatusT クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Synclockwithstatust::getstatus メソッド](../windows/synclockwithstatust-getstatus-method.md)|現在の SyncLockWithStatusT オブジェクトの待機の状態を取得します。|  
|[Synclockwithstatust::islocked メソッド](../windows/synclockwithstatust-islocked-method.md)|SyncLockWithStatusT の現在のオブジェクトがリソースを所有しているかどうかを示しますつまり、SyncLockWithStatusT オブジェクトが *ロック*します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[Synclockwithstatust::status _ データ メンバー](../windows/synclockwithstatust-status-data-member.md)|保持しますが、基になる結果にロック操作の後の操作を待機するオブジェクトは、現在の SyncLockWithStatusT オブジェクトに基づいています。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>「  
 [Microsoft::WRL::Wrappers::Details 名前空間](../windows/microsoft-wrl-wrappers-details-namespace.md)