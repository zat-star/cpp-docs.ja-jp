---
title: "コンパイラ エラー C3851 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3851
dev_langs: C++
helpviewer_keywords: C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ed2a62b859e37455041171c81bb6830db372c697
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3851"></a>コンパイラ エラー C3851
'char': ユニバーサル文字名は基本文字セットの文字を指定できません  
  
 C++ としてコンパイルされるコードでは、基本ソース文字セットの文字を表すユニバーサル文字名を使用できません (文字列リテラルまたは文字リテラルの場合を除く)。 詳細については、「 [Character Sets](../../cpp/character-sets2.md)」を参照してください。 C としてコンパイルされるコードでは、0x20 から 0x7f の範囲内 (両端を含む) の文字に対応するユニバーサル文字名を使用できません。ただし、0x24 ('$')、0x40 ('@')、または 0x60 ('`') は使用できます。  
  
 次の例では、C3851 が生成され、その修正方法が表示されます。  
  
```cpp  
// C3851.cpp  
int main()  
{  
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set  
   int test2_A = 0;        // OK  
}  
```