---
title: "コンパイラの警告 (レベル 4) C4458 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4458
dev_langs: C++
helpviewer_keywords: C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 455b7173221e05b0da0f73a5c1401d1114297b14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4458"></a>コンパイラの警告 (レベル 4) C4458
  
> 宣言 '*識別子*'、クラス メンバーが非表示にします
  
宣言*識別子*ローカル スコープで、まったく同じ名前の宣言を非表示に*識別子*クラス スコープでします。 この警告を参照するを認識できます。*識別子*このスコープで解決するには、クラス メンバー バージョンではなく、ユーザーの意図ができない可能性がありますが、ローカルに宣言されたバージョンにします。 この問題を修正するのには、クラス メンバーの名前と競合しないローカル変数名を付けるお勧めします。  
    
## <a name="example"></a>例
  
次の例では、ため C4458 が生成されますパラメーター`x`し、ローカル変数`y`で`member_fn`クラスにデータ メンバーと同じ名前があります。 この問題を解決するには、パラメーターおよびローカル変数の別の名前を使用します。  
  
```cpp  
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;  
        // To fix this issue, change the parameter name x
        // and local name y to something that does not 
        // conflict with the data member names.
    }
} s;
```  
