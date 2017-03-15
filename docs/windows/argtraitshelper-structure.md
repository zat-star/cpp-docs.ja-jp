---
title: "ArgTraitsHelper 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::ArgTraitsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ArgTraitsHelper 構造体"
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ArgTraitsHelper 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template<  
   typename TDelegateInterface  
>  
struct ArgTraitsHelper;  
```  
  
#### パラメーター  
 `TDelegateInterface`  
 デリゲート インターフェイス。  
  
## 解説  
 ヘルプにはデリゲートの引数のような共通の特性を定義します。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`methodType`|`decltype(&TDelegateInterface::Invoke)` と同義。|  
|`Traits`|`ArgTraits<methodType>` と同義。|  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[ArgTraitsHelper::args 定数](../windows/argtraitshelper-args-constant.md)|ヘルプ [ArgTraits::args](../windows/argtraits-args-constant.md) インターフェイスはデリゲートの呼び出しメソッドのパラメーターの数を記録します。|  
  
## 継承階層  
 `ArgTraitsHelper`  
  
## 必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)