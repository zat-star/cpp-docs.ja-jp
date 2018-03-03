---
title: "Synclockt::synclockt コンス トラクター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e2aa229b85c0d3e40b5f3736c9e5da451102775
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="synclocktsynclockt-constructor"></a>SyncLockT::SyncLockT コンストラクター
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `other`  
 右辺値参照を別の SyncLockT オブジェクト。  
  
 `sync`  
 SyncLockWithStatusT の別のオブジェクトへの参照。  
  
## <a name="remarks"></a>コメント  
 SyncLockT クラスの新しいインスタンスを初期化します。  
  
 最初のコンス トラクターの初期化パラメーターで指定された別の SyncLockT オブジェクトから現在の SyncLockT オブジェクト`other`、し、その他の SyncLockT オブジェクトを無効にします。 2 番目のコンス トラクターは`protected`、無効な状態を現在の SyncLockT オブジェクトを初期化します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>参照  
 [SyncLockT クラス](../windows/synclockt-class.md)