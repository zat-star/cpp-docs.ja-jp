---
title: "C++ のラムダ式の constexpr |Microsoft ドキュメント"
ms.custom: 
ms.date: 07/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
caps.latest.revision: 0
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c6221118477c79d683d468469b1f87dfa33efded
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="constexpr-lambda-expressions-in-c"></a>constexpr C++ のラムダ式
**Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): としてラムダ式を宣言することは`constexpr`か指定する定数式で使用時に各データ メンバーの初期化がキャプチャまたはが導入されています、定数式は許可されています。  

```cpp
    int y = 32;
    auto answer = [y]() constexpr 
    {
        int x = 10;
        return y + x; 
    };

    constexpr int Increment(int n) 
    {
        return [n] { return n + 1; }();
    }

``` 
ラムダは、暗黙的に`constexpr`その結果の要件を満たしている場合、`constexpr`関数。
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
場合は、ラムダは、暗黙的または明示的に`constexpr`、関数ポインターに変換するは、結果として得られる関数も`constexpr`:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C++ 標準ライブラリ内の関数オブジェクト](../standard-library/function-objects-in-the-stl.md)   
 [関数呼び出し](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)
