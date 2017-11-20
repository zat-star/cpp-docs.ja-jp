---
title: "コメント (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 828d02ddd02c7484e142333bdb87453f8fb922e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comments-c"></a>コメント (C++)
コメントは、コンパイラは無視しますが、プログラマにとって便利なテキストです。 コメントは、通常、後で参照できるようにコードに注釈を付けるために使用されます。 コンパイラは、それらを空白文字として処理します。 特定のコード行を非アクティブな; させるテストでコメントを使用することができます。ただし、 `#if` / `#endif`プリプロセッサ ディレクティブの方が適してこのコメントを含むコードを囲むことができますが、コメントを入れ子にすることはできません。  
  
 C++ のコメントは、次のいずれかの方法で記述されます。  
  
-   `/*` (スラッシュ、アスタリスク) 文字と、それに続く任意の文字シーケンス (改行を含む) と、それに続く `*/`。 この構文は ANSI C と同じです。  
  
-   `//` (2 つのスラッシュ) 文字と、それに続く任意の文字シーケンス。 直前に円記号がない新しい行は、この形式のコメントを終了させます。 そのため、この形式は一般に "単一行コメント" と呼ばれます。  
  
 コメント文字 (`/*`、`*/`、および `//`) は、文字定数、文字列リテラル、またはコメント内で特別な意味を持ちません。 したがって、最初の構文を使用したコメントを入れ子にすることはできません。  
  
## <a name="see-also"></a>関連項目  
 [構文規則](../cpp/lexical-conventions.md)