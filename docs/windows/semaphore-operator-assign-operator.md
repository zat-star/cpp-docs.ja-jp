---
title: "Semaphore::operator= 演算子 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 演算子"
ms.assetid: ea19839f-91f0-4b00-a35b-5728fcba4981
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Semaphore::operator= 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在のセマフォ オブジェクト セマフォ オブジェクトから指定したハンドルを移動します。  
  
## <a name="syntax"></a>構文  
  
```  
Semaphore& operator=(  
   _Inout_ Semaphore&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 セマフォ オブジェクトへの右辺値参照。  
  
## <a name="return-value"></a>戻り値  
 現在のセマフォ オブジェクトへの参照。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>「
 [Semaphore クラス](../windows/semaphore-class.md)