---
title: "Implements::CastToUnknown メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown メソッド"
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Implements::CastToUnknown メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

IUnknown 基のインターフェイスへのポインターを取得します。  
  
## 構文  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## 戻り値  
 このアクションは、IUnknown ポインターが常に成功して返します。  
  
## 解説  
 内部ヘルパー関数です。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Implements 構造体](../Topic/Implements%20Structure.md)