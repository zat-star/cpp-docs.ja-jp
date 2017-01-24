---
title: "continue ステートメント (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "continue"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "continue キーワード [C]"
  - "ループ構造, continue キーワード"
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# continue ステートメント (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`continue` ステートメントは、それを囲む最も近い `do`、`for`、または `while` ステートメントの次の反復処理に制御を渡し、`do`、`for`、または `while` ステートメント本体の残りのステートメントをバイパスします。  
  
## 構文  
 `jump-statement`:  
 `continue;`  
  
 `do`、`for`、または `while` ステートメントの次の反復処理は次のように決定されます。  
  
-   `do` または `while` ステートメント内では、次の繰り返しは `do` または `while` ステートメントの式の再評価によって開始されます。  
  
-   `for` ステートメントの `continue` ステートメントは、`for` ステートメントのループ式を評価します。  その後、コンパイラは条件式を再評価し、その結果に応じて、ステートメント本体を終了または反復処理します。  `for` ステートメントおよびその必須ではない要素の詳細については、「[for ステートメント](../c-language/for-statement-c.md)」を参照してください。  
  
 `continue` ステートメントの例を次に示します。  
  
```  
while ( i-- > 0 )   
{  
    x = f( i );  
    if ( x == 1 )  
        continue;  
    y += x * x;  
}  
```  
  
 この例では、ステートメント本体は、`i` が 0 を超える場合に実行されます。  最初に、`f(i)` は `x` に割り当てられています。次に、`x` が 1 に等しい場合は、`continue` ステートメントが実行されます。  本体のステートメントの残りの部分は無視され、ループ テストの評価がループの先頭から再び実行されます。  
  
## 参照  
 [continue ステートメント](../cpp/continue-statement-cpp.md)