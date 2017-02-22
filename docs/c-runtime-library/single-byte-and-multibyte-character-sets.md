---
title: "1 バイト文字セットとマルチバイト文字セット | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.character.multibyte"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "文字セット [C++], マルチバイト"
  - "文字セット [C++], 1 バイト"
  - "MBCS [C++], 概要 (MBCS の)"
  - "SBCS (1 バイト文字セット)"
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 1 バイト文字セットとマルチバイト文字セット
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ASCII 文字セットでは、0x00 ~ 0x7F –範囲の文字を定義します。  ヨーロッパ範囲 0x00 – 0x7F までの文字を ASCII 文字セットと同様に定義され、0x80 –ルーチンから拡張文字セットを定義するそのほかの文字セットは、主にあります。  したがって、8 ビット 1 バイト文字セット \(`SBCS`\) は多くのヨーロッパ言語の ASCII 文字セット、文字セットを表す十分です。  ただし、ある、ユーロ文字セットは、日本語の漢字など、1 バイトのコード体系で表現できるおよびマルチバイト文字の定数 \(`MBCS`\) エンコーディングを必要とするよりも多くの文字です。  
  
> [!NOTE]
>  Microsoft ランタイム ライブラリの `SBCS` 多くのルーチンを適切にマルチバイトのバイト、文字や文字列を処理します。  多くのマルチバイト文字セットはサブセットと ASCII 文字セットを定義します。  多くのマルチバイト文字セットでは、0x00 ～ 0x7F の範囲内の各文字が、ASCII 文字セットで同じ値を持つ文字と一致します。  たとえば、`ASCII` と `MBCS` の文字列の両方でも、1 バイトの `NULL` の文字 \(「\\0」\) の値は 0x00 で、終端の NULL 文字を示します。  
  
 マルチバイト文字セットは、1 バイト、2 バイト文字の両方から構成される可能性がある。  したがって、マルチバイト文字は前のバイト文字の組み合わせが含まれる場合があります。  2 バイトのマルチバイト文字に先頭バイトと後続バイトがあります。  特殊なマルチバイト文字セットでは、先行バイトが後続バイトと同じ範囲の値を持っている場合があります。  これらの範囲が重複する場合、特定のバイトが先行バイトと後続バイトとして機能しているかどうかを判断するために特定のコンテキストを評価する必要がある場合があります。  
  
## 参照  
 [国際化](../c-runtime-library/internationalization.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)