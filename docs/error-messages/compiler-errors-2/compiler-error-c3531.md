---
title: "コンパイラ エラー C3531 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3531"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3531"
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3531
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': 'auto' を含む型のシンボルには初期化子が必要です  
  
 指定した変数には、初期化子式がありません。  
  
### このエラーを解決するには  
  
1.  変数の宣言時に、等号 \(\=\) を使用した構文の単純な代入などの初期化子式を指定します。  
  
## 使用例  
 次の例では、変数 `x1`、`y1, y2, y3`、および `z2` が初期化されていないため、C3531 が発生します。  
  
```  
// C3531.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto x1;                  // C3531  
   auto y1, y2, y3;          // C3531  
   auto z1 = 1, z2, z3 = -1; // C3531  
   return 0;  
}  
```  
  
## 参照  
 [auto キーワード](../../cpp/auto-keyword.md)