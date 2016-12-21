---
title: "C++ コメント | Microsoft Docs"
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
  - "コードのコメント, C++"
  - "コメント, C++ コード"
  - "コメント, ドキュメントの作成 (コードの)"
  - "空白, C++ のコメント"
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ コメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コメントは、コンパイラは無視しますが、プログラマにとって便利なテキストです。  コメントは、通常、後で参照できるようにコードに注釈を付けるために使用されます。  コンパイラは、それらを空白文字として処理します。  テストでコメントを使用して、特定のコード行を非アクティブにすることができます。ただし、このためには、`#if`\/`#endif` の各プリプロセッサ ディレクティブの方が適しています。これは、コメントを含むコードを囲むことができますが、コメントは入れ子にできないためです。  
  
 C\+\+ のコメントは、次のいずれかの方法で記述されます。  
  
-   `/*` \(スラッシュ、アスタリスク\) 文字と、それに続く任意の文字シーケンス \(改行を含む\) と、それに続く `*/`。  この構文は ANSI C と同じです。  
  
-   `//` \(2 つのスラッシュ\) 文字と、それに続く任意の文字シーケンス。  直前に円記号がない新しい行は、この形式のコメントを終了させます。  そのため、この形式は一般に "単一行コメント" と呼ばれます。  
  
 コメント文字 \(`/*`、`*/`、および `//`\) は、文字定数、文字列リテラル、またはコメント内で特別な意味を持ちません。  したがって、最初の構文を使用したコメントを入れ子にすることはできません。  
  
## 参照  
 [構文規則](../cpp/lexical-conventions.md)