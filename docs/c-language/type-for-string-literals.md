---
title: "文字列リテラルの型 | Microsoft Docs"
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
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 8e8d285bf85c711bd6adcbdb45c6384ea2309dc0
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="type-for-string-literals"></a>文字列リテラルの型
文字列リテラルは、`char` の型配列 (つまり、**char[ ]**) を持ちます  (ワイド文字列は、`wchar_t` の型配列 (つまり、**wchar_t[ ]**) を持ちます)。これは、文字列が型 `char` の要素の配列であることを意味しています。 配列の要素の数は、文字列の文字の数に 1 (終端の null 文字) を足した数と同じです。  
  
## <a name="see-also"></a>関連項目  
 [C 文字列リテラル](../c-language/c-string-literals.md)
