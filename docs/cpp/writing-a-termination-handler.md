---
title: "終了ハンドラーの記述 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "例外処理, 終了ハンドラー"
  - "例外, 終了"
  - "ハンドラー"
  - "ハンドラー, 終了"
  - "構造化例外処理, 終了ハンドラー"
  - "終了ハンドラー"
  - "終了ハンドラー, 書き込み"
  - "try-catch キーワード [C++], 終了ハンドラー"
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 終了ハンドラーの記述
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

例外ハンドラーとは異なり、終了ハンドラーは、コードの保護されたブロックが正常に終了したかどうかに関係なく、常に実行されます。  終了ハンドラーの唯一の目的は、コードのセクションの実行がどのように終了したかに関係なく、メモリ、ハンドル、ファイルなどのリソースが適切に閉じられるようにすることです。  
  
 終了ハンドラーは、try\-finally ステートメントを使用します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [try\-finally ステートメント](../cpp/try-finally-statement.md)  
  
-   [リソースのクリーンアップ](../cpp/cleaning-up-resources.md)  
  
-   [例外処理でのアクションのタイミング](../cpp/timing-of-exception-handling-a-summary.md)  
  
-   [終了ハンドラーに対する制限](../cpp/restrictions-on-termination-handlers.md)  
  
## 参照  
 [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)