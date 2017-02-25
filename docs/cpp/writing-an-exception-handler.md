---
title: "例外ハンドラーの記述 | Microsoft Docs"
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
  - "例外処理, 例外ハンドラー"
  - "構造化例外処理, 例外ハンドラー"
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 例外ハンドラーの記述
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

特定のエラーに応答するために例外ハンドラーがよく使用されます。  例外処理構文を使用して、処理する方法が不明な例外をすべて除外できます。  他の例外は、それらの特定の例外を検索するように記述された他のハンドラー \(ランタイム ライブラリまたはオペレーティング システム内にあると考えられます\) に渡される必要があります。  
  
 例外ハンドラーは try\-except ステートメントを使用します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [try\-except ステートメント](../cpp/try-except-statement.md)  
  
-   [例外フィルターの記述](../cpp/writing-an-exception-filter.md)  
  
-   [ソフトウェア例外の発生](../cpp/raising-software-exceptions.md)  
  
-   [ハードウェア例外](../cpp/hardware-exceptions.md)  
  
-   [例外ハンドラーに対する制限](../cpp/restrictions-on-exception-handlers.md)  
  
## 参照  
 [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)