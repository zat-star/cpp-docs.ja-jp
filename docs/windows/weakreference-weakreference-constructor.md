---
title: "WeakReference::WeakReference コンストラクター | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::WeakReference::WeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakReference、コンストラクター"
ms.assetid: 4959a9d7-78ea-423d-a46b-50d010d29fff
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakReference::WeakReference コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
WeakReference();  
```  
  
## <a name="remarks"></a>コメント  
 新しいインスタンスを初期化、 [WeakReference クラス](../windows/weakreference-class1.md)します。  
  
 WeakReference オブジェクトに対する強い参照ポインターを初期化 `nullptr`, 、し、厳密な参照カウントが 1 に初期化します。  
  
## <a name="requirements"></a>要件  
 **Header:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
    
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)