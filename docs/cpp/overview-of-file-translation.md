---
title: "ファイル変換の概要 | Microsoft Docs"
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
  - "ファイル変換 [C++], ファイル変換の概要"
  - "ファイル [C++], 変換"
  - "トランザクション フェーズのプリプロセス"
  - "プログラム [C++], 構文規則"
  - "変換 [C++]"
  - "変換フェーズ"
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ファイル変換の概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ プログラムは、C プログラムと同様、1 つ以上のファイルで構成されます。  これらの各ファイルは、次の概念的な順序で変換されます \(実際の順序は "as if" 規則に従います。つまり、変換は、これらの手順に従ったかのように行われる必要があります\)。  
  
1.  構文のトークン化。  文字の対応付けとトライグラフ処理、行スプライス、およびトークン化は、この変換フェーズで実行されます。  
  
2.  プリプロセス。  この変換フェーズでは、`#include` ディレクティブで参照される補助ソース ファイルを読み込み、"stringizing" ディレクティブと "charizing" ディレクティブを処理し、トークン連結およびマクロの展開を実行します \(詳細については、『プリプロセッサ リファレンス』の「[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)」を参照してください\)。  プリプロセス フェーズの結果、まとまって「翻訳単位」を定義する一連のトークンができます。  
  
     プリプロセッサ ディレクティブは、常にシャープ記号 \(**\#**\) で始まります \(つまり、行の最初の空白以外の文字はシャープ記号である必要があります\)。  1 行に 1 つのプリプロセッサ ディレクティブだけを指定できます。  次に例を示します。  
  
    ```  
    #include <iostream>  // Include text of iostream in   
                         //  translation unit.  
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty   
                         //  text string).  
    ```  
  
3.  コード生成。  この変換フェーズでは、プリプロセス フェーズで生成されたトークンを使用してオブジェクト コードを生成します。  
  
     このフェーズでは、ソース コードの構文チェックと意味チェックが実行されます。  
  
 詳細については、『プリプロセッサ リファレンス』の「[変換の段階](../preprocessor/phases-of-translation.md)」を参照してください。  
  
 C\+\+ プリプロセッサは ANSI C プリプロセッサの厳密なスーパーセットですが、いくつかの点が異なります。  以下に、ANSI C と C\+\+ のプリプロセッサのいくつかの相違点を挙げます。  
  
-   単一行コメントがサポートされています。  詳細については、「[コメント](../cpp/comments-cpp.md)」を参照してください。  
  
-   C\+\+ の場合のみ、定義済みマクロ、**\_\_cplusplus** が定義されます。  詳細については、『プリプロセッサ リファレンス』の「[定義済みマクロ](../preprocessor/predefined-macros.md)」を参照してください。  
  
-   C プリプロセッサでは、C\+\+ 演算子 **.\***、**–\>\***、および `::` は認識されません。  演算子の詳細については、「[演算子](../cpp/cpp-built-in-operators-precedence-and-associativity.md)」および「[式](../cpp/expressions-cpp.md)」を参照してください。  
  
## 参照  
 [構文規則](../cpp/lexical-conventions.md)