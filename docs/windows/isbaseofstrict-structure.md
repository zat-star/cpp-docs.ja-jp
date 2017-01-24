---
title: "IsBaseOfStrict 構造体 | Microsoft Docs"
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
  - "internal/Microsoft::WRL::Details::IsBaseOfStrict"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsBaseOfStrict 構造体"
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IsBaseOfStrict 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
#### パラメーター  
 `Base`  
 基本型。  
  
 `Derived`  
 派生型。  
  
## 解説  
 一方の型がもう一方の型の基本クラスであるかどうかをテストします。  
  
 最初のテンプレートは型が **true** または **false**を与えた可能性がある基本型から派生されるかどうかをテストします。  2 番目のテンプレートは型が **false**を常に同じ自体から派生されるかどうかをテストします。  
  
## メンバー  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[IsBaseOfStrict::value 定数](../Topic/IsBaseOfStrict::value%20Constant.md)|1 種類の型の基本クラスであるかどうかを示します。|  
  
## 継承階層  
 `IsBaseOfStrict`  
  
## 必要条件  
 **ヘッダー:** internal.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)