---
title: "RuntimeClassBaseT 構造体 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT"
dev_langs: 
  - "C++"
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClassBaseT 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template <  
   unsigned int RuntimeClassTypeT  
>  
friend struct Details::RuntimeClassBaseT;  
```  
  
#### パラメーター  
 `RuntimeClassTypeT`  
 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) の一つ以上の列挙子を指定するフラグのフィールド。  
  
## 解説  
 `QueryInterface` のアクションおよびインターフェイス ID を取得するためのヘルパー メソッドが用意されています。  
  
## メンバー  
  
## 継承階層  
 `RuntimeClassBaseT`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/ja-jp/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)