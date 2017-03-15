---
title: "Mutex::Mutex コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Mutex、コンストラクター"
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Mutex::Mutex コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mutex クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
explicit Mutex(  
   HANDLE h  
);  
  
Mutex(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 ハンドル、または、ミュー テックス オブジェクトへのハンドルへの右辺値参照します。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターでは、指定したハンドル、ミュー テックス オブジェクトを初期化します。 2 番目のコンス トラクターでは、指定したハンドル、ミュー テックス オブジェクトを初期化し、現在ミュー テックス オブジェクトに、ミュー テックスの所有権を移動します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>関連項目
 [Mutex クラス](Mutex%20Class1.md)