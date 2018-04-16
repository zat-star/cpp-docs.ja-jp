---
title: "C 文字列リテラル | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b0be3ee70ef708441d20fdbbc14f25f5102d734a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-string-literals"></a>C 文字列リテラル
"文字列リテラル" は、二重引用符 (**" "**) で囲まれたソース文字セットの文字のシーケンスです。 文字列リテラルは、まとめて扱われる、null で終わる文字列を形成する文字のシーケンスを表すために使用されます。 ワイド文字列リテラルの前には、常に文字 **L** を付ける必要があります。  
  
## <a name="syntax"></a>構文  
 *string-literal*:  
 **"** *s-char-sequence* opt**"**  
  
 **L"** *s-char-sequence* opt**"**  
  
 *s-char-sequence*:  
 *s-char*  
  
 *s-char-sequence s-char*  
  
 *s-char*:  
 二重引用符 (")、円記号 (\\)、または改行文字を除く、ソース文字セットの任意のメンバー  
  
 *escape-sequence*  
  
 次の例は、単純な文字列リテラルです。  
  
```  
char *amessage = "This is a string literal.";  
```  
  
 「[エスケープ シーケンス](../c-language/escape-sequences.md)」テーブルに示されたすべてのエスケープ コードは、文字列リテラルで有効です。 文字列リテラル内で二重引用符を表すには、エスケープ シーケンス **\\"** を使用します。 単一引用符 (**'**) は、エスケープ シーケンスを使用せずに表すことができます。 円記号 (**\\**) を文字列内で使用する場合は、直後に 2 つ目の円記号を付ける (**\\\\**) 必要があります。 行の末尾にあるバックスラッシュは、常に行連結文字として解釈されます。  
  
## <a name="see-also"></a>参照  
 [C の要素](../c-language/elements-of-c.md)