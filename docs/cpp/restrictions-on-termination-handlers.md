---
title: "終了ハンドラーに関する制約 | Microsoft Docs"
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
  - "制限事項, 終了ハンドラー"
  - "終了ハンドラー, 制限事項"
  - "try-catch キーワード [C++], 終了ハンドラー"
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 終了ハンドラーに関する制約
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`goto` ステートメントを使用して、`__try` ステートメント ブロックまたは `__finally` ステートメント ブロックにジャンプすることはできません。  代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 \(ただし、`__try` ステートメント ブロックの外部にジャンプすることもできます\)。 また、`__finally` ブロック内の例外ハンドラーまたは終了ハンドラーは入れ子にできません。  
  
 また、終端ハンドラーに割り当てられた一部の種類のコードが生成する結果に問題がある場合があります。したがって、これらは慎重に使用する必要があります。  1 つは、`__finally` ステートメント ブロックの外部にジャンプする `goto` ステートメントです。  ブロックが正常終了の一部として実行される場合、特に異常は発生しません。  ただし、システムがスタックをアンワインドしている場合は、そのアンワインドが停止し、異常な終了がなかったかのように現在の関数が制御を得ます。  
  
 `__finally` ステートメント ブロック内の `return` ステートメントが、同じ状況を大まかに示します。  終了ハンドラーを含む関数の直前の呼び出し元に制御が戻ります。  システムがスタックをアンワインドしていた場合、このプロセスは停止し、例外が発生しなかったかのようにプログラムが処理されます。  
  
## 参照  
 [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)   
 [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)