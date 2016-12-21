---
title: "式エバリュエーター エラー CXX0025 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0025"
  - "CXX0025"
ms.assetid: 3e2fb541-63b3-46ac-9f93-3dadb253bcf6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 式エバリュエーター エラー CXX0025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

演算子には構造体\/共用体が必要です  
  
 `struct` 型または **union** 型の式を使用する演算子が、`struct`、または **union** 以外の型の式に適用されました。  
  
 クラス、構造体、共用体の要素を使用するときは修飾子を使って正確に指定する必要があります。  修飾の不十分な要素は使用できません。  
  
 このエラーは CAN0025 と同じものです。