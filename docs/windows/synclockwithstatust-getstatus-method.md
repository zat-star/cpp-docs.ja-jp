---
title: "Synclockwithstatust::getstatus メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 181735766e62aa1bf8c306bd425c6e6b03b2066d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="synclockwithstatustgetstatus-method"></a>SyncLockWithStatusT::GetStatus メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>戻り値  
 オブジェクトに基づいている SyncLockWithStatusT クラスなどの待機操作の結果、[ミュー テックス](../windows/mutex-class1.md)または[セマフォ](../windows/semaphore-class.md)です。 ゼロ (0) では、待機操作によって返されたシグナルの状態であることを示しますそれ以外の場合、別の状態が発生しました、タイムアウト値が経過した場合などです。  
  
## <a name="remarks"></a>コメント  
 SyncLockWithStatusT、現在の待機の状態を取得します。  
  
 GetStatus() 関数が、基になる値を取得[status _](../windows/synclockwithstatust-status-data-member.md)データ メンバーです。 SyncLockWithStatusT クラスに基づいてオブジェクトは、ロック操作を実行するときに使用可能になるオブジェクトのオブジェクトが最初に待機します。 待機操作の結果が格納されている、`status_`データ メンバーです。 有効な値、`status_`データ メンバーは、待機操作の戻り値。 詳細については、の戻り値を参照してください、 **WaitForSingleObjectEx()** MSDN ライブラリ内の関数。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>参照  
 [SyncLockWithStatusT クラス](../windows/synclockwithstatust-class.md)