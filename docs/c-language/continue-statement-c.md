---
title: "continue ステートメント (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: continue
dev_langs: C++
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cdf4d877ef1b88826d66e36a7ce24fdcff2cb348
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="continue-statement-c"></a>continue ステートメント (C)
`continue` ステートメントは、それを囲む最も近い `do`、`for`、または `while` ステートメントの次の反復処理に制御を渡し、`do`、`for`、または `while` ステートメント本体の残りのステートメントをバイパスします。  
  
## <a name="syntax"></a>構文  
 `jump-statement`:  
 `continue;`  
  
 `do`、`for`、または `while` ステートメントの次の反復処理は次のように決定されます。  
  
-   `do` または `while` ステートメント内では、次の繰り返しは `do` または `while` ステートメントの式の再評価によって開始されます。  
  
-   `continue` ステートメントの `for` ステートメントは、`for` ステートメントのループ式を評価します。 その後、コンパイラは条件式を再評価し、その結果に応じて、ステートメント本体を終了または反復処理します。 `for` ステートメントおよびその非終端要素の詳細については、「[for ステートメント](../c-language/for-statement-c.md)」を参照してください。  
  
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
  
 この例では、ステートメント本体は、`i` が 0 を超える場合に実行されます。 最初に、`f(i)` は `x` に割り当てられています。次に、`x` が 1 に等しい場合は、`continue` ステートメントが実行されます。 本体のステートメントの残りの部分は無視され、ループ テストの評価がループの先頭から再び実行されます。  
  
## <a name="see-also"></a>参照  
 [continue ステートメント](../cpp/continue-statement-cpp.md)