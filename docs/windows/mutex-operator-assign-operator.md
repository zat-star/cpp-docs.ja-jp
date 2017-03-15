---
title: "Mutex::operator= 演算子 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 演算子"
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mutex::operator= 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

割り当て (移動)、指定されたミュー テックスは、現在のミュー テックス オブジェクトをオブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 ミュー テックス オブジェクトに右辺値の参照。  
  
## <a name="return-value"></a>戻り値  
 現在のミュー テックス オブジェクトへの参照。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。、 **移動セマンティクス** の [右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>「
 [Mutex クラス](Mutex%20Class1.md)