---
title: "繰り返しステートメント (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "繰り返しステートメント"
  - "ループ構造, 繰り返しステートメント"
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 繰り返しステートメント (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

繰り返しステートメントにより、ループ終了条件に応じて、ステートメント \(または複合ステートメント\) が複数回実行されます。  これらのステートメントが複合ステートメントの場合、[break](../cpp/break-statement-cpp.md) ステートメントまたは [continue](../cpp/continue-statement-cpp.md) ステートメントに達した場合を除き、順序どおりに実行されます。  
  
 C\+\+ 言語には、4 つの繰り返しステートメント \([while](../cpp/while-statement-cpp.md)、[do](../cpp/do-while-statement-cpp.md)、[for](../cpp/for-statement-cpp.md)、[範囲ベースの for](../Topic/Range-based%20for%20Statement%20\(C++\).md)\) があります。  これらのステートメントは、終了式が 0 \(false\) と評価されるか、**break** ステートメントによってループが強制的に終了されるまで繰り返されます。  次の表は、これらのステートメントと操作をまとめたものです。それぞれについては以降のセクションで詳しく説明します。  
  
### 繰り返しステートメント  
  
|ステートメント|評価のタイミング|初期化|インクリメント|  
|-------------|--------------|---------|-------------|  
|`while`|ループの先頭|Ｘ|Ｘ|  
|**do**|ループの最後|Ｘ|Ｘ|  
|**for**|ループの先頭|○|○|  
|**範囲ベースの for**|ループの先頭|○|○|  
  
 繰り返しステートメントのステートメント部分は宣言にできません。  ただし、宣言を含む複合ステートメントにすることができます。  
  
## 参照  
 [C\+\+ ステートメントの概要](../cpp/overview-of-cpp-statements.md)