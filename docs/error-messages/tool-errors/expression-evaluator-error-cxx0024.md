---
title: "式エバリュエーター エラー CXX0024 | Microsoft Docs"
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
  - "CXX0024"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0024"
  - "CXX0024"
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 式エバリュエーター エラー CXX0024
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

演算には左辺値が必要です  
  
 左辺値として評価できない式が、左辺値の必要な演算で使われています。  
  
 左辺値 \(代入文の左辺に記述する式\) は、メモリ位置を参照する式になります。  
  
 たとえば、`buffer[count]` は特定のメモリ位置を示すので左辺値として有効です。  これに対して、論理比較演算 `zed != 0` は TRUE または FALSE として評価され、メモリ アドレスを示さないので左辺値として無効です。  
  
 このエラーは CAN0024 と同じものです。