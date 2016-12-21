---
title: "コンパイラ エラー C2491 | Microsoft Docs"
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
  - "C2491"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2491"
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2491
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'識別子': dllimport 関数の定義は許可されていません。  
  
 データ、静的データ メンバー、および関数は `dllimport` として宣言できますが、`dllimport` として定義することはできません。  
  
 この問題を解決するには、関数の定義から `__declspec(dllimport)` 指定子を削除します。  
  
 次の例では警告 C2491 が生成されます。  
  
```  
// C2491.cpp  
// compile with: /c  
// function definition  
void __declspec(dllimport) funcB() {}   // C2491  
  
// function declaration  
void __declspec(dllimport) funcB();   // OK  
```