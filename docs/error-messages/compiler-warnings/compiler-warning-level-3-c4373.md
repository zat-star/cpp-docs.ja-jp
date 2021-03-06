---
title: コンパイラの警告 (レベル 3) C4373 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C4373
dev_langs:
- C++
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1694c8d15ad65b39a27af8ae5aae02e9c729896
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-warning-level-3-c4373"></a>コンパイラの警告 (レベル 3) C4373

> '*関数*': 仮想関数のオーバーライド*base_function*'、const/volatile 修飾子によってのみと一致しません。 パラメーターと、以前のバージョンのコンパイラはオーバーライドしませんでした。

## <a name="remarks"></a>コメント

アプリケーションには、基底クラスの仮想メソッドをオーバーライドする派生クラスのメソッドが含まれ、オーバーライドする側のメソッドのパラメーターは、 [const](../../cpp/const-cpp.md) または [volatile](../../cpp/volatile-cpp.md) 修飾子についてのみ、仮想メソッドのパラメーターと異なります。 つまり、コンパイラでは、基底クラスまたは派生クラスのいずれかにおけるメソッドに、関数参照をバインドする必要があります。

バージョンの Visual Studio 2008 の前に、コンパイラは、基底クラスでメソッドに関数をバインドし、警告メッセージを発行します。 以降のバージョンのコンパイラを無視する、`const`または`volatile`修飾子は、派生クラス内のメソッドに関数をバインドし、警告が発行**C4373**です。 この後者の動作は、C++ 標準に準拠しています。

## <a name="example"></a>例

次のコード例では、警告 C4373 が生成されます。 この問題を解決するには、基本メンバー関数として同じ CV 修飾子を使用して、上書きを行うことができますか、またはに上書きを作成しなかった場合、関数、派生クラスで、別の名前を付けています。

```cpp
// c4373.cpp
// compile with: /c /W3
#include <stdio.h>
struct Base
{
    virtual void f(int i) {
        printf("base\n");
    }
};

struct Derived : Base
{
    void f(const int i) {  // C4373
        printf("derived\n");
    }
};

void main()
{
    Derived d;
    Base* p = &d;
    p->f(1);
}
```

```Output
derived
```