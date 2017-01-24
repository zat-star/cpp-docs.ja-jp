---
title: "コンパイラ エラー C3198 | Microsoft Docs"
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
  - "C3198"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3198"
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3198
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点プラグマの使い方が無効です: fenv\_access プラグマは precise モードでのみ操作します  
  
 [fenv\_access](../../preprocessor/fenv-access.md) プラグマが、**\/fp:precise** 以外の [\/fp](../../build/reference/fp-specify-floating-point-behavior.md) 設定で使用されています。  
  
 次の例では警告 C3198 が生成されます。  
  
```  
// C3198.cpp  
// compile with: /fp:fast  
#pragma fenv_access(on)   // C3198  
```