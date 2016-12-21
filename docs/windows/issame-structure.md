---
title: "IsSame 構造体 | Microsoft Docs"
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
  - "internal/Microsoft::WRL::Details::IsSame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsSame 構造体"
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IsSame 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template <  
   typename T1,  
   typename T2  
>  
struct IsSame;  
template <  
   typename T1  
>  
struct IsSame<T1, T1>;  
```  
  
#### パラメーター  
 `T1`  
 型。  
  
 `T2`  
 他のスレッドが入力されます。  
  
## 解説  
 1 種類の型が別の型と同じであるかどうかをテストします。  
  
## メンバー  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[IsSame::value 定数](../windows/issame-value-constant.md)|1 種類の別のと同じであるかどうかを示します。|  
  
## 継承階層  
 `IsSame`  
  
## 必要条件  
 **ヘッダー:** internal.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)