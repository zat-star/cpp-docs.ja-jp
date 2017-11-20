---
title: "1 バイト文字セットとマルチバイト文字セット | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.character.multibyte
dev_langs: C++
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9f7f9cfe98e243cb9eaa0252889b61e6c6019d89
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="single-byte-and-multibyte-character-sets"></a>1 バイト文字セットとマルチバイト文字セット
ASCII 文字セットでは、0x00 から 0x7F までの範囲の文字を定義しています。 そのほかに、ASCII 文字セットと同じ 0x00 から 0x7F までの範囲の文字に加え、0x80 から 0xFF までの拡張文字セットも定義している、主にヨーロッパ向けのさまざまな文字セットがあります。 多くのヨーロッパ系言語の文字と ASCII 文字セットを表現するには、8 ビットの 1 バイト文字セット (`SBCS`) で十分です。 ただし、日本語の漢字など、ヨーロッパ以外の文字セットでは、1 バイトのコード体系ですべての文字を表現しきれないため、マルチバイト文字セット (`MBCS`) エンコーディングが必要になります。  
  
> [!NOTE]
>  Microsoft ランタイム ライブラリの多くの `SBCS` ルーチンでマルチバイト、文字、文字列が必要に応じて処理されます。 多くのマルチバイト文字セットでは、ASCII 文字セットをサブセットとして定義しています。 多くのマルチバイト文字セットでは、0x00 から 0x7F の範囲内の各文字が、ASCII 文字セットで同じ値を持つ文字と一致します。 たとえば、`ASCII` 文字列でも `MBCS` 文字列でも、1 バイトの `NULL` 文字 ('\0') の値は 0x00 で、終端の null 文字を意味します。  
  
 マルチバイト文字セットは、1 バイト文字と 2 バイト文字の両方で構成されることがあります。 そのため、マルチバイト文字列には、 1 バイト文字と 2 バイト文字が混在することがあります。 2 バイト文字には、先行バイトと後続バイトがあります。 特殊なマルチバイト文字セットでは、先行バイトが後続バイトと同じ範囲の値を持っている場合があります。 先頭バイトと後続バイトの範囲が重複する場合は、コンテキストを確認し、指定したバイトが先頭バイトと後続バイトのどちらであるかを判断する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [国際化](../c-runtime-library/internationalization.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)