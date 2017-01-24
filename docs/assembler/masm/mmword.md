---
title: "MMWORD | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MMWORD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MMWORD directive"
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MMWORD
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MMX および \(SSE\) XMM 命令を含む 64 ビット マルチメディア オペランドに使用されます。  
  
## 構文  
  
```  
MMWORD  
```  
  
## 解説  
 `MMWORD` は型です。  MASM に追加する前に MMWORD 同等の機能をで実行されている可能性があります :  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 命令が両方とも 64 ビットのオペランドで実行すると`QWORD` は 64 ビット符号なし整数の型です `MMWORD` は 64 ビット マルチメディアの値の型です。  
  
 `MMWORD` は [\_\_m64](../../cpp/m64.md) と同じ型を表すためのものです。  
  
## 使用例  
  
```  
movq     mm0, mmword ptr [ebx]  
```