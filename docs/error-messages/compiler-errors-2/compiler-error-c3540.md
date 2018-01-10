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
ms.workload: cplusplus
ms.openlocfilehash: b3befc331c4f43f4efd4e5039258e0faddae97db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [auto キーワード](../../cpp/auto-keyword.md)   
 [/Zc:auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof 演算子](../../cpp/sizeof-operator.md)