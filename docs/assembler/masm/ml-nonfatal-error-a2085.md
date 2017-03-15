---
title: "ML Nonfatal Error A2085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2085"
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**現在の CPU モードで使用されていない命令または登録**  
  
 まず現在のプロセッサのモードに無効だった命令登録またはキーワードを使用しました。  
  
 たとえば32 ビットのレジスタは [.386](../Topic/.386.md) をそれ以上に必要です。  CR0 などの制御レジスタが特権モード [.386P](../../assembler/masm/dot-386p.md) をそれ以上に必要です。  このエラーは**NEAR32FAR32**必要な  **フラット**  のキーワードに対して生成されます。**386** それ以上で。  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)