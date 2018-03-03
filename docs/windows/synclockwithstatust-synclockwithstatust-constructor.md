---
title: "Synclockwithstatust::synclockwithstatust コンス トラクター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT, constructor
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc5be4a37182cb23b47a2511d2e7d5eb0ffa558a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="synclockwithstatustsynclockwithstatust-constructor"></a>SyncLockWithStatusT::SyncLockWithStatusT コンストラクター
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLockWithStatusT(  
   _Inout_ SyncLockWithStatusT&& other  
);  
  
explicit SyncLockWithStatusT(  
   typename SyncTraits::Type sync,  
   DWORD status  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `other`  
 右辺値参照を別の SyncLockWithStatusT オブジェクト。  
  
 `sync`  
 SyncLockWithStatusT の別のオブジェクトへの参照。  
  
 `status`  
 値、 [status _](../windows/synclockwithstatust-status-data-member.md)のデータ メンバー、`other`パラメーターまたは`sync`パラメーター。  
  
## <a name="remarks"></a>コメント  
 SyncLockWithStatusT クラスの新しいインスタンスを初期化します。  
  
 最初のコンス トラクターの初期化パラメーターで指定された別の SyncLockWithStatusT から現在の SyncLockWithStatusT オブジェクト`other`、し、その他の SyncLockWithStatusT オブジェクトを無効にします。 2 番目のコンス トラクターは`protected`、無効な状態を現在の SyncLockWithStatusT オブジェクトを初期化します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>参照  
 [SyncLockWithStatusT クラス](../windows/synclockwithstatust-class.md)   
 [SyncLockWithStatusT::GetStatus メソッド](../windows/synclockwithstatust-getstatus-method.md)