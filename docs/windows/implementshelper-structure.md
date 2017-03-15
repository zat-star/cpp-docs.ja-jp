---
title: "ImplementsHelper 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::ImplementsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ImplementsHelper 構造体"
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ImplementsHelper 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### パラメーター  
 `RuntimeClassFlagsT`  
 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) の一つ以上の列挙子を指定するフラグのフィールド。  
  
 `ILst`  
 インターフェイス ID のリスト。  
  
 `IsDelegateToClass`  
 実装の現在のインスタンスが `ILst`の最初の三つの基本クラス `true` ;を指定します。それ以外の場合は `false`。  
  
## 解説  
 ヘルプが [実装](../Topic/Implements%20Structure.md) 構造を実装します。  
  
 このテンプレートは、インターフェイスのリストを走査し、基本クラスと QueryInterface を有効にするために必要な情報として追加します。  
  
## メンバー  
  
## 継承階層  
 `ImplementsHelper`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/ja-jp/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)