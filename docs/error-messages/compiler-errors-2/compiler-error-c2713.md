---
title: "コンパイラ エラー C2713 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2713"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2713"
ms.assetid: bae9bee3-b4b8-4be5-b6a5-02df587a7278
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C2713
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数ごとに許されている例外ハンドルのフォームは 1 つです。  
  
 1 つの関数内で、構造化例外処理 \(`__try`\/`__except`\) と C\+\+ の例外処理 \(`try`\/`catch`\) を同時に使用することはできません。