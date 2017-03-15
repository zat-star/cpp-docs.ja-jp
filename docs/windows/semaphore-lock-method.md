---
title: "Semaphore::Lock メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock メソッド"
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Semaphore::Lock メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定されたタイムアウト期間が経過か、現在のオブジェクトまたは指定したハンドルに関連付けられているセマフォ オブジェクトまでの待機がシグナル状態になっています。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `milliseconds`  
 タイムアウト間隔 (ミリ秒単位)。 既定値は、無限には、無期限に待機します。  
  
 `h`  
 セマフォ オブジェクトへのハンドル。  
  
## <a name="return-value"></a>戻り値  
 Details::SyncLockWithStatusT \< HandleTraits::SemaphoreTraits >  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
[Semaphore クラス](../windows/semaphore-class.md)
 