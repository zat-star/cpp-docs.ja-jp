---
title: 終了ハンドラーに関する制約 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 71486b167f4e9939d4913b3660ed3513dc02b8f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="restrictions-on-termination-handlers"></a>終了ハンドラーに関する制約
`goto` ステートメントを使用して、`__try` ステートメント ブロックまたは `__finally` ステートメント ブロックにジャンプすることはできません。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 (ただし、`__try` ステートメント ブロックの外部にジャンプすることもできます)。また、`__finally` ブロック内の例外ハンドラーまたは終了ハンドラーは入れ子にできません。  
  
 また、終端ハンドラーに割り当てられた一部の種類のコードが生成する結果に問題がある場合があります。したがって、これらは慎重に使用する必要があります。 1 つは、`goto` ステートメント ブロックの外部にジャンプする `__finally` ステートメントです。 ブロックが正常終了の一部として実行される場合、特に異常は発生しません。 ただし、システムがスタックをアンワインドしている場合は、そのアンワインドが停止し、異常な終了がなかったかのように現在の関数が制御を得ます。  
  
 `return` ステートメント ブロック内の `__finally` ステートメントが、同じ状況を大まかに示します。 終了ハンドラーを含む関数の直前の呼び出し元に制御が戻ります。 システムがスタックをアンワインドしていた場合、このプロセスは停止し、例外が発生しなかったかのようにプログラムが処理されます。  
  
## <a name="see-also"></a>参照  
 [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)