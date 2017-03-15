---
title: "Swap 関数 (Windows ランタイム C++ テンプレート ライブラリ) | Microsoft Docs"
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
  - "internal/Microsoft::WRL::Details::Swap"
dev_langs: 
  - "C++"
ms.assetid: ed134a08-ceb7-4279-aa02-a183c3a426ea
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Swap 関数 (Windows ランタイム C++ テンプレート ライブラリ)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
WRL_NOTHROW inline void Swap(  
   _Inout_ T& left,  
   _Inout_ T& right  
);  
```  
  
#### パラメーター  
 `left`  
 第 1 引数。  
  
 `right`  
 第 2 引数。  
  
## 戻り値  
  
## 解説  
 2 種類の指定した引数の値を交換します。  
  
## 必要条件  
 **ヘッダー:** internal.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)