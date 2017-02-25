---
title: "コンパイラの警告 C4962 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4962"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4962"
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラの警告 C4962
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 最適化によってプロファイル データに矛盾が生じたため、ガイド付き最適化のプロファイルを無効にします。  
  
 関数のカウント \(プロファイル\) データの信頼性が低かったため、この関数は \/LTCG:PGO を指定してコンパイルされませんでした。 その関数の信頼性の低いプロファイル データを格納している .pgc ファイルを再生成するためにプロファイリングを再実行します。  
  
 既定では、この警告はオフに設定されています。 詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。