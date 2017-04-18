---
title: "コンパイラの警告 (レベル 1) C4052 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4052
dev_langs:
- C++
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d893ae8ca212c04fd11e0d86c1bd8fc3d6912e22
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4052"></a>コンパイラの警告 (レベル 1) C4052
関数に対する宣言の&1; つに可変個の引数が含まれていません。  
  
 関数の&1; つの宣言に、可変個の引数が含まれません。 これは無視されます。  
  
 次の例では C4052 が生成されます。  
  
```  
// C4052.c  
// compile with: /W4 /c  
int f();  
int f(int i, ...);   // C4052  
```
