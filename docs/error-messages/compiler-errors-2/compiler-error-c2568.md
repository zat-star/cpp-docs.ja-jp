---
title: "コンパイラ エラー C2568 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2568"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2568"
ms.assetid: 140b4dc9-5a88-4032-9aef-a224bb796f72
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C2568
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier1' : オーバーロード関数のうち、どれを呼び出すのか決定できません。  
  
 コンパイラは、どのオーバーロードされた関数を呼び出すかを決定できません。  関数に渡された実パラメーターは、オーバーロードされたいずれかの関数の仮パラメーター リストと一致するようにキャストする必要があります。ただし、ある 1 つのパラメーター リストだけが、ほかの可能性のあるパラメーター リストよりもうまく一致するようにする必要があります。