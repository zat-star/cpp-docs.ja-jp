---
title: "コンパイラ エラー C3540 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3540
dev_langs: C++
helpviewer_keywords: C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0ff7a017ce86e567d0aabcf494e11f48d1cdea05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3540"></a>コンパイラ エラー C3540
'type': 'auto' を含む型に sizeof は適用できません  
  
 [Sizeof](../../cpp/sizeof-operator.md)演算子が含まれているので、示された型には適用できません、`auto`指定子。  
  
## <a name="example"></a>例  
 次の例では、C3540 が生成されます。  
  
```  
// C3540.cpp  
// Compile with /Zc:auto  
int main() {  
    auto x = 123;  
    sizeof(x);    // OK  
    sizeof(auto); // C3540  
    return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../../cpp/auto-keyword.md)   
 [/Zc:auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof 演算子](../../cpp/sizeof-operator.md)