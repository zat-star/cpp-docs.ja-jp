---
title: "コンパイラの警告 (レベル 1) C4027 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4027"
ms.assetid: f30d57b9-20c4-4284-8686-566d9f0ca7fc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数はパラメーター リストなしで宣言されています。  
  
 関数の宣言に仮引数がありませんが、関数の定義に仮引数があるか、呼び出しに実引数があります。 この関数への後続の呼び出しでは、関数が関数の定義内または呼び出し内で検出された型の実引数を取ることが前提になります。