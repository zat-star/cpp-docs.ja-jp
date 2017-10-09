---
title: "break ステートメント (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- break
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: a180c88fc71e4786e8512bc26421825132611ed4
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="break-statement-c"></a>break ステートメント (C)
`break` ステートメントは、それを囲む最も近い `do`、`for`、`switch`、または `while` の各ステートメントの実行を終了します。 制御は、終了したステートメントの後に続くステートメントに移動します。  
  
## <a name="syntax"></a>構文  
 *jump-statement*:  
 `break;`  
  
 `break` ステートメントは、`switch` ステートメント内で個々の case の処理を終了するためによく使用されます。 囲む反復ステートメントまたは `switch` ステートメントがない場合、エラーが生成されます。  
  
 入れ子になったステートメント内では、`break` ステートメントは、それを直接囲む `do`、`for`、`switch`、または `while` の各ステートメントだけを終了させます。 `return` ステートメントまたは `goto` ステートメントを使用して、入れ子構造から別の場所に制御を移すことができます。  
  
 `break` ステートメントの例を次に示します。  
  
```  
#include <stdio.h>  
int main() {  
   char c;  
   for(;;) {  
      printf_s( "\nPress any key, Q to quit: " );  
  
      // Convert to character value  
      scanf_s("%c", &c);  
      if (c == 'Q')  
          break;  
   }  
} // Loop exits only when 'Q' is pressed  
```  
  
## <a name="see-also"></a>関連項目  
 [break ステートメント](../cpp/break-statement-cpp.md)
