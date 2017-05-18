---
title: "コンパイラの警告 (レベル 4) C4937 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4937
dev_langs:
- C++
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 655bf5154f66e2f641321adbd395c2bc5694e148
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4937"></a>コンパイラの警告 (レベル 4) C4937
'text1' と 'text2' を、'directive' への引数として区別できません  
  
 コンパイラがディレクティブへの引数を処理するしくみにより、複数のテキスト表現 (単一および二重のアンダースコア形式) を持つキーワードなど、コンパイラにとって意味を持つ名前は区別することができません。  
  
 このような文字列の例としては、_ _cdecl と\__forceinline です。  /Za の下では、二重アンダースコア形式のみが有効であることに注意してください。  
  
 次の例では C4937 が生成されます。  
  
```  
// C4937.cpp  
// compile with: /openmp /W4  
#include "omp.h"  
int main() {  
   #pragma omp critical ( __leave )   // C4937  
   ;  
  
   // OK  
   #pragma omp critical ( leave )  
   ;  
}  
```
