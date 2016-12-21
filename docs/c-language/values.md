---
title: "値 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
ms.assetid: 24003f89-220f-4f93-be7a-b650c26157d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 値
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.1.2.5** 浮動小数点数のさまざまな型の表現と値セット  
  
 **float** 型は 32 ビットで、符号が 1 ビット、指数部が 8 ビット、仮数部が 23 ビットです。  その範囲は 7 桁以上の精度で、\+\/–3.4E38 です。  
  
 **double** 型は 64 ビットで、符号が 1 ビット、指数部が 11 ビット、仮数部が 52 ビットです。  その範囲は 15 桁以上の精度で、\+\/–1.7E308 です。  
  
 **long double** 型は 80 ビットで、符号が 1 ビット、指数部が 15 ビット、仮数部が 64 ビットです。  その範囲は 19 桁以上の精度で、\+\/–1.2E4932 です。  Microsoft C コンパイラでは、**long double** 型の表現は **double** 型と同じであることに注意してください。  
  
## 参照  
 [浮動小数点数値演算](../c-language/floating-point-math.md)