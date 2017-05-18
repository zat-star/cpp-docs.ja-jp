---
title: "コンパイラ エラー C2448 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2448
dev_langs:
- C++
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b88dcb6b594ed6034d612f8f43f853a7c28fbe60
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2448"></a>コンパイラ エラー C2448
'identifier': 関数形式の初期化子が、関数定義を  
  
 関数の定義が正しくありません。  
  
 このエラーは、旧式の C 言語仮引数リストで発生することができます。  
  
 次の例では、c2448 エラーが生成されます。  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```
