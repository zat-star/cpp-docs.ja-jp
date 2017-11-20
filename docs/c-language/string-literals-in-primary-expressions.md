---
title: "一次式の文字列リテラル | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: string literals, in primary expressions
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d1ed5731f0b46769ac9f49c34752d8794a0dddc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="string-literals-in-primary-expressions"></a>一次式の文字列リテラル
"文字列リテラル" は、二重引用符で囲まれた文字、ワイド文字、または隣接する文字のシーケンスです。 これらは変数ではないため、文字列リテラルおよびその要素はいずれも代入演算の左側のオペランドにはなりません。 文字列リテラルの型は `char` の配列 (またはワイド文字列リテラルを表す `wchar_t` の配列) です。 式に含まれる配列は、ポインターに変換されます。 文字列の詳細については、[文字列リテラル](../c-language/c-string-literals.md)に関するページをご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [C 一次式](../c-language/c-primary-expressions.md)