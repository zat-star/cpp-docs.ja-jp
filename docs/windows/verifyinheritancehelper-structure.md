---
title: "VerifyInheritanceHelper 構造体 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::VerifyInheritanceHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VerifyInheritanceHelper 構造体"
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# VerifyInheritanceHelper 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template <  
   typename I,  
   typename Base  
>  
struct VerifyInheritanceHelper;  
template <  
   typename I  
>  
struct VerifyInheritanceHelper<I, Nil>;  
```  
  
#### パラメーター  
 `I`  
 型。  
  
 `Base`  
 他のスレッドが入力されます。  
  
## 解説  
 1 個のインターフェイスが別のインターフェイスから派生されるかどうかをテストします。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[VerifyInheritanceHelper::Verify メソッド](../windows/verifyinheritancehelper-verify-method.md)|現在のテンプレート パラメーターで指定される 2 種類のインターフェイスをテストし、1 種類のインターフェイスが他から派生されるかどうかを判定します。|  
  
## 継承階層  
 `VerifyInheritanceHelper`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)