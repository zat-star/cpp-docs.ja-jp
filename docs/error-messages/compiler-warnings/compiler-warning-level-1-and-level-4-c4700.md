---
title: "コンパイラの警告 (レベル 1 およびレベル 4) C4700 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/21/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4700
dev_langs:
- C++
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00b871d6199338cc3040d6bddedb85f8732dfccd
ms.sourcegitcommit: 4e416049665819ac62f5300ddf86e94adede4ba0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>コンパイラの警告 (レベル 1 およびレベル 4) C4700

> 初期化されていないローカル変数 '*名前*' を使用

ローカル変数*名前*されました*使用*、つまりから、値が割り当てられる前にします。 C と C++ では、ローカル変数は既定では初期化されていません。 初期化されていない変数は、任意の値を含めることができ、それらの使用は、未定義の動作につながります。 警告 C4700 は、ほとんどの場合、プログラムで予期しない結果またはクラッシュを引き起こす可能性のあるバグを示します。

この問題を修正するのには、宣言時にローカル変数を初期化または使用される前に値を代入できます。 関数は、参照パラメーターとして渡されるか、そのアドレスがポインター パラメーターとして渡されたときに変数を初期化するために使用できます。

## <a name="example"></a>例

この例では、これらは初期化され、発生することができますガベージ値の種類を示しています前に変数の t、u、および v を使用する場合、C4700 が生成されます。 変数 x、y、および z 操作を使用する前に初期化されるため、警告が発生しません。

```cpp
// c4700.cpp
// compile by using: cl /EHsc /W4 c4700.cpp
#include <iostream>

// function takes an int reference to initialize
void initialize(int& i)
{
    i = 21;
}

int main()
{
    int s, t, u, v;   // Danger, uninitialized variables

    s = t + u + v;    // C4700: t, u, v used before initialization
    std::cout << "Value in s: " << s << std::endl;

    int w, x;         // Danger, uninitialized variables
    initialize(x);    // fix: call function to init x before use
    int y{10};        // fix: initialize y, z when declared
    int z{11};        // This C++11 syntax is recommended over int z = 11;

    w = x + y + z;    // Okay, all values initialized before use
    std::cout << "Value in w: " << w << std::endl;
}
```

このコードは、実行、t、u および v と初期化、されていないと、s の出力は予測できません。

```Output
Value in s: 37816963
Value in w: 42
```
