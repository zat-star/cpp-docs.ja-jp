---
title: "コンパイラの警告 (レベル 4) C4130 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4130
dev_langs:
- C++
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 282f9755470baca115d0595b002b929874619a93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4130"></a>コンパイラの警告 (レベル 4) C4130
'operator': 文字列定数のアドレスで論理演算が行われました  
  
 文字列リテラルのアドレスで演算子が使用されると、不要なコードが生成されます。  
  
 次の例では C4130 が生成されます。  
  
```  
// C4130.cpp  
// compile with: /W4  
int main()  
{  
   char *pc;  
   pc = "Hello";  
   if (pc == "Hello") // C4130  
   {  
   }  
}  
```  
  
 **if** ステートメントは、ポインター `pc` に格納されている値と、コード内に出現するたびに個別に割り当てられる文字列 "Hello" のアドレスを比較しています。 **if** ステートメントは、 `pc` が指す文字列と、文字列 "Hello" については比較しません。  
  
 文字列を比較するには、 `strcmp` 関数を使用します。