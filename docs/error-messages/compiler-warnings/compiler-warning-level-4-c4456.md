---
title: "コンパイラの警告 (レベル 4) C4456 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4456
dev_langs:
- C++
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
caps.latest.revision: 0
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
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 8698c9a430a79bbec1f6e82b8ac58067317c59a1
ms.contentlocale: ja-jp
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4456"></a>コンパイラの警告 (レベル 4) C4456
  
> 宣言 '*識別子*' 上のローカル宣言を非表示になります
  
宣言*識別子*ローカル スコープでは、同じ名前の前のローカル宣言の宣言を非表示にします。 この警告を参照するを認識できます。*識別子*ローカル スコープで解決するにはローカルに宣言されたバージョンをいない以前ローカル、またはユーザーの意図ができない可能性があります。 この問題を解決するには、その他のローカル名と競合しないローカル変数名を付けることをお勧めします。  
    
## <a name="example"></a>例
  
次の例では、ループ制御変数のため C4456 が生成されます`int x`し、ローカル変数`double x`で`member_fn`名前が同じです。 この問題を解決するには、ローカル変数の別の名前を使用します。  
  
```cpp  
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        } 
        x += u; // uses local double x
    }
} s;
```  

