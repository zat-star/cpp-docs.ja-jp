---
title: "コンパイラ エラー C2457 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2457
dev_langs:
- C++
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 53686570865df15a1b97a11d5b71e5c99b0c1f8c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2457"></a>コンパイラ エラー C2457
'マクロ': 定義済みマクロは、関数本体の外部で表示できません。  
  
 定義済みマクロを使用しようとしています。 [__FUNCTION\_\_](../../preprocessor/predefined-macros.md)、グローバル空間内です。  
  
## <a name="example"></a>例  
 次の例では、c2457 エラーが生成されます。  
  
```  
// C2457.cpp  
#include <stdio.h>  
  
__FUNCTION__;   // C2457, cannot be global  
  
int main()   
{  
    printf_s("\n%s",__FUNCTION__);   // OK  
}  
```
