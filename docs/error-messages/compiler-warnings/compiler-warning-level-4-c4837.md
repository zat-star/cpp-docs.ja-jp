---
title: "コンパイラの警告 (レベル 4) C4837 | Microsoft Docs"
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
  - "C4837"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4837"
ms.assetid: 9a3c7b6b-ffe4-443d-96af-43deb80d85b4
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4837
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

検出されたトライグラフ: 「または"または"「%c "に置き換えられました。  
  
 検出されたトライグラフは表示された文字に置き換えられます。  
  
 コンパイラは、他の処理が完了する前にトライグラフを変換します。  トライグラフに似た文字シーケンスが誤ってトライグラフとして解釈されないようにするには、文字エスケープ シーケンス `\?` を使用します。  トライグラフの詳細については、「[トライグラフ](../Topic/Trigraphs.md)」を参照してください。  エスケープ シーケンスの詳細については、「[エスケープ シーケンス](../../c-language/escape-sequences.md)」を参照してください。  
  
 既定では、C4837 はオフに設定されています。  詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
### このエラーを解決するには  
  
1.  ソース コードのいずれかの '?' 文字の代わりに文字エスケープ シーケンス `\?` を使用します。  
  
## 参照  
 [トライグラフ](../Topic/Trigraphs.md)   
 [エスケープ シーケンス](../../c-language/escape-sequences.md)   
 [既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)