---
title: "HANDLENullTraits 構造体 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HANDLENullTraits 構造体"
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HANDLENullTraits 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

初期化されていないハンドルのような共通の特性を定義します。  
  
## 構文  
  
```  
struct HANDLENullTraits;  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`Type`|ハンドルのシノニムです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[HANDLENullTraits::Close メソッド](../windows/handlenulltraits-close-method.md)|指定したハンドルを閉じます。|  
|[HANDLENullTraits::GetInvalidValue メソッド](../windows/handlenulltraits-getinvalidvalue-method.md)|無効なハンドルを表します。|  
  
## 継承階層  
 `HANDLENullTraits`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 参照  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)