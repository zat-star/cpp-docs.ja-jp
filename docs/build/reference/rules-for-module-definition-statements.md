---
title: "モジュール定義ステートメントに関する規則 | Microsoft Docs"
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
  - ".def"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "モジュール定義ファイル"
  - "モジュール定義ファイル, ステートメント構文"
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# モジュール定義ステートメントに関する規則
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

以下の構文規則は、.def ファイル内のすべてのステートメントに適用されます。  特定のステートメントに対してだけ適用される規則については、それぞれのステートメントの説明を参照してください。  
  
-   ステートメント、属性キーワード、およびユーザー指定の識別子では、大文字と小文字が区別されます。  
  
-   スペースやセミコロン \(;\) を含む長いファイル名は、引用符 \("\) で囲みます。  
  
-   ステートメントのキーワードと引数の間、およびステートメントとステートメントの間は、1 つ以上のスペース、タブ、改行文字のいずれかで区切ります。  引数を示すコロン \(:\) や等号 \(\=\) の両側には、スペース、タブ、改行文字のいずれかを挿入します。  
  
-   **NAME** ステートメントまたは **LIBRARY** ステートメントを使用する場合は、ほかのどのステートメントよりも先に記述します。  
  
-   **SECTIONS** ステートメントと **EXPORTS** ステートメントは、同じ .def ファイル内で複数回使用できます。  各ステートメントでは、複数の引数を指定できます。この場合、それぞれの指定を 1 つ以上のスペース、タブ、改行文字のいずれかで区切ります。  ステートメント キーワードは、最初の指定の前に 1 回記述します。ただし、以降のそれぞれの指定の前で、繰り返し使用してもかまいません。  
  
-   大半のステートメントは、LINK のコマンド ライン オプションでも指定できます。  詳細については、該当する LINK オプションの説明を参照してください。  
  
-   .def ファイル内のコメントには、セミコロン \(;\) をコメント行の先頭に付けます。  コメントはステートメントと同じ行には記述できませんが、複数行にわたるステートメントでは指定と指定の間に挿入できます。たとえば、**SECTIONS** ステートメントや **EXPORTS** ステートメントは複数行にわたるステートメントです。  
  
-   数値引数は、10 進表記か 16 進表記で指定します。  
  
-   文字列の引数が[予約語](../../build/reference/reserved-words.md)と一致する場合は、二重引用符 \("\) で囲みます。  
  
## 参照  
 [モジュール定義 \(.def\) ファイル](../Topic/Module-Definition%20\(.Def\)%20Files.md)   
 [Frequently Asked Questions on Building](http://msdn.microsoft.com/ja-jp/56a3bb8f-0181-4989-bab4-a07ba950ab08)