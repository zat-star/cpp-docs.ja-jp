---
title: "Mutex::Lock メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock メソッド"
ms.assetid: 61d95072-b690-441e-a080-0bf94a733141
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Mutex::Lock メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ミュー テックスを解放するまで、現在のオブジェクトまたは指定したハンドルに関連付けられているミュー テックス オブジェクト待機または指定されたタイムアウト期間が経過します。  
  
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
 ミュー テックス オブジェクトのハンドル。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>「
 [Mutex クラス](Mutex%20Class1.md)