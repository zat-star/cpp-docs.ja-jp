---
title: "コンパイラの制限 | Microsoft Docs"
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
  - "cl.exe コンパイラ, 言語構成要素の制限"
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの制限
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 標準は、さまざまな言語構成体の制限を勧告しています。  以下は、Visual C\+\+ コンパイラが推奨される制限を実装しない場合のリストです。  最初の数字は ISO C\+\+ 11 標準 \(INCITS\/ISO\/IEC 14882\-2011\[2012\], Annex B\) で規定されている制限であり、2 番目の数字は Visual C\+\+ で実装されている制限です。  
  
-   複合ステートメント、イテレーション制御構造、および選択制御構造の入れ子レベル \[C\+\+ 標準: 256\] \(Visual C\+\+ コンパイラ: 入れ子になっているステートメントの組み合わせに依存しますが、一般的には 100 から 110 の間\)。  
  
-   1 つのマクロ定義内のパラメーター \[C\+\+ 標準: 256\] \(Visual C\+\+ コンパイラ: 127\)。  
  
-   1 つのマクロ呼び出しの引数 \[C\+\+ 標準: 256\] \(Visual C\+\+ コンパイラ: 127\)。  
  
-   文字列リテラルまたはワイド文字列リテラル \(連結後\) の文字数 \[C\+\+ 標準: 65536\] \(Visual C\+\+ コンパイラ: `null` 終端文字を含む 1 バイト文字の場合は 65535、 `null` 終端文字を含む 2 バイト文字の場合は 32767\)。  
  
-   単一の `struct-declaration-list` で入れ子になったクラス、構造体、または共用体の定義のレベル \[C\+\+ 標準: 256\] \(Visual C\+\+ コンパイラ: 16\)。  
  
-   コンストラクター定義内のメンバー初期化子 \[C\+\+ 標準: 6144\] \(Visual C\+\+ コンパイラ: 最低 6144\)。  
  
-   1 つの識別子のスコープ修飾 \[C\+\+ 標準: 256\] \(Visual C\+\+ コンパイラ: 127\)。  
  
-   入れ子になった `extern` 指定 \[C\+\+ 標準: 1024\] \(Visual C\+\+ コンパイラ: 9 \(グローバル スコープの暗黙的な `extern` 指定をカウントしません。グローバル スコープの暗黙的な `extern` 指定をカウントする場合は 10\)。  
  
-   テンプレート宣言内のテンプレート引数 \[C\+\+ 標準: 1024\] \(Visual C\+\+ コンパイラ: 2046\)。  
  
## 参照  
 [非標準動作](../Topic/Nonstandard%20Behavior.md)