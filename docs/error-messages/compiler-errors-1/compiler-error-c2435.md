---
title: "コンパイラ エラー C2435 | Microsoft Docs"
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
  - "C2435"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2435"
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2435
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 動的な初期化にはマネージ CRT が必要であり、\/clr:safe と共にコンパイルできません  
  
 アプリケーション ドメインごとにグローバルな変数の初期化には、`/clr:pure` を指定してコンパイルした CRT が必要ですが、これは検証可能なイメージを作成しません。  
  
 詳細については、「[appdomain](../Topic/appdomain.md)」、および「[process](../../cpp/process.md)」を参照してください。  
  
 次の例では警告 C2435 が生成されます。  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```