---
title: "C++ トークン | Microsoft Docs"
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
  - "解析, C++ トークン"
  - "トークン"
  - "変換単位"
  - "空白, C++ トークン"
ms.assetid: aa812fd0-6d47-4f3f-aee0-db002ee4d8b9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ トークン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

トークンは、コンパイラにとって意味がある、C \+\+ プログラムの最小要素です。 C\+\+ パーサーが認識するトークンの種類は、識別子、キーワード、リテラル、演算子、句読記号、およびその他の区切り記号です。 これらのトークンのストリームが、翻訳単位を構成します。  
  
 トークンは通常、*空白*で区切られます。 空白は、次のうちの 1 つ以上です。  
  
-   スペース  
  
-   水平または垂直タブ  
  
-   改行  
  
-   フォームフィード  
  
-   コメント  
  
 このパーサーは、キーワード、識別子、リテラル、演算子、および区切り記号を認識します。 特定のトークンの種類に関する情報については、「[キーワード](../cpp/keywords-cpp.md)」、「[識別子](../cpp/identifiers-cpp.md)」、「[数値、ブール値、およびポインターのリテラル](../cpp/numeric-boolean-and-pointer-literals-cpp.md)」、「[文字列リテラルと文字リテラル](../cpp/string-and-character-literals-cpp.md)」、「[ユーザー定義リテラル](../Topic/User-Defined%20Literals%20%20\(C++\).md)」、「[C\+\+ 組み込み演算子、優先順位、および結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)」、および「[区切り記号](../cpp/punctuators-cpp.md)」を参照してください。 トークンを区切る必要がある場合を除いて、空白は無視されます。  
  
 プリプロセス トークンは、プリプロセス フェーズでコンパイラに渡されるトークン ストリームを生成するために使用されます。 プリプロセス トーン カテゴリは、ヘッダー名、識別子、プリプロセス番号、文字リテラル、文字列リテラル、プリプロセス演算子と区切り文字、および他のカテゴリと一致しない単一の非空白文字です。 文字リテラルと文字列リテラルはユーザー定義リテラルに使用できます。 プリプロセス トークンは空白またはコメントで区切ることができます。  
  
 パーサーが入力ストリームからのトークンを区切るときには、左から右にスキャンした入力文字列を使用して、できるだけ長いトークンを作成します。 次のコード片の場合を考えてみます。  
  
```  
a = i+++j;  
```  
  
 コードを記述したプログラマは、次の 2 つのステートメントのいずれかを意図していた可能性があります。  
  
```  
a = i + (++j) a = (i++) + j  
```  
  
 パーサーは入力ストリームから最長のトークンを作成しようとするため、2 つ目の解釈が選択され、トークンは `i++`、`+`、および `j` になります。  
  
## 参照  
 [構文規則](../cpp/lexical-conventions.md)