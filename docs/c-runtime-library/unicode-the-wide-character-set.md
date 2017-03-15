---
title: "Unicode: ワイド文字セット | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unicode [C++], ワイド文字セット"
  - "ワイド文字 [C++], Unicode"
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Unicode: ワイド文字セット
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ワイド文字は、2 バイトの多言語文字コードです。  、技術的な記号や特別な発行の文字が使用中の文字で、ワイド文字として Unicode 規格に従って世界中で最新の計算を表すことができます。  Microsoft を含む大きなコンソーシアムでも、保持されて、Unicode 規格は、広く受け入れられます。  
  
 ワイド文字は、型 `wchar_t`です。  ワイド文字列が `wchar_t[]` の配列として表され、`wchar_t*` のポインターを参照できます。  ワイド文字として文字が文字 `L` を付け加えることにより、ASCII 文字を表すことができます。  たとえば、L'\\0 は `NULL` の終端の幅 \(16 ビット\) 文字です。  同様に、ワイド文字列として ASCII リテラル \(L " Hello」\) に文字 L を付け加えることにより、ASCII のリテラル文字列を表すことができます。  
  
 通常、ワイド文字はマルチバイト文字、メモリの領域を占有を操作するよりも高速です。  また、マルチバイト文字を使用した場合、一度に表すことのできるロケールは 1 つだけですが、Unicode を使用した場合、世界中の文字セットをすべて同時に使用できます。  
  
## 参照  
 [国際化](../c-runtime-library/internationalization.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)