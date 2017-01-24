---
title: "ChainInterfaces::CastToUnknown メソッド | Microsoft Docs"
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
  - "implements/Microsoft::WRL::ChainInterfaces::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown メソッド"
ms.assetid: a6a58555-e5b0-4773-aba0-959d9d362c6b
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ChainInterfaces::CastToUnknown メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

IUnknown へのポインターに `I0` テンプレート パラメーターによって定義される型のインターフェイス ポインターをキャストします。  
  
## 構文  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## 戻り値  
 IUnknown へのポインター。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)