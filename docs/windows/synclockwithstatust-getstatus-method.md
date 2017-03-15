---
title: "SyncLockWithStatusT::GetStatus メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetStatus メソッド"
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# SyncLockWithStatusT::GetStatus メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>戻り値  
 オブジェクトに基づいている SyncLockWithStatusT クラスなどの待機操作の結果、 [ミュー テックス](Mutex%20Class1.md) または [セマフォ](../windows/semaphore-class.md)します。 ゼロ (0) では、待機操作によって返されたシグナルの状態であることを示しますそれ以外の場合、別の状態が発生しました、タイムアウト値が経過した場合など。  
  
## <a name="remarks"></a>コメント  
 現在の SyncLockWithStatusT オブジェクトの待機の状態を取得します。  
  
 GetStatus() 関数は、基になる値を取得 [status _](../windows/synclockwithstatust-status-data-member.md) データ メンバーです。 SyncLockWithStatusT クラスに基づいてオブジェクトがロック操作を実行すると、オブジェクトは、最初に使用可能になるオブジェクトの待機します。 待機操作の結果は、 `status_` データ メンバーです。 有効な値、 `status_` データ メンバーは、待機操作の戻り値。 詳細については、の戻り値を参照してください、 **WaitForSingleObjectEx()** MSDN ライブラリ内の関数です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [SyncLockWithStatusT クラス](../windows/synclockwithstatust-class.md)