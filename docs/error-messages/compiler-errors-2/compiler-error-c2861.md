---
title: "コンパイラ エラー C2861 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2861
dev_langs:
- C++
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
caps.latest.revision: 9
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
ms.openlocfilehash: 3e53605c9109b5b96e4758b2fa3d729108597b56
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2861"></a>コンパイラ エラー C2861
[関数名]: インターフェイスのメンバー関数を定義することはできません  
  
 メンバーを検出し、コンパイラは、interface キーワードが発生しましたまたは、インターフェイスとして構造体の推測が関数の定義。  インターフェイスは、メンバー関数の定義を含めることはできません。  
  
## <a name="example"></a>例  
 次の例では、c2861 エラーが生成されます。  
  
```  
// C2861.cpp  
// compile with: /c  
#include <objbase.h>   // required for IUnknown definition  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IMyInterface : IUnknown {  
   HRESULT mf(int a);  
};  
  
HRESULT IMyInterface::mf(int a) {}   // C2861  
  
```
