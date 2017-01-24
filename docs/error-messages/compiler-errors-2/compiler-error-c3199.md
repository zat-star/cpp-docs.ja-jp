---
title: "コンパイラ エラー C3199 | Microsoft Docs"
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
  - "C3199"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3199"
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3199
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点プラグマの使い方が無効です: 例外は precise でないモードではサポートされていません  
  
 **\/fp:precise** 以外の [\/fp](../../build/reference/fp-specify-floating-point-behavior.md) が設定されている状況で、浮動小数点例外モデルの指定に、[float\_control](../Topic/float_control.md) プラグマが使用されました。  
  
 次の例では警告 C3199 が生成されます。  
  
```  
// C3199.cpp  
// compile with: /fp:fast  
#pragma float_control(except, on)   // C3199  
```