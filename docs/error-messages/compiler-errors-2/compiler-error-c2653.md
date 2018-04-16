---
title: "コンパイラ エラー C2653 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2653
dev_langs:
- C++
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f18e3d6210c5d9b9aba4fdfaab296a01d32b6d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2653"></a>コンパイラ エラー C2653

> '*識別子*': クラスまたは名前空間名ではありません

言語の構文では、クラス、構造体、共用体、または名前空間の名前は、ここが必要です。

このエラーは、クラス、構造体、共用体、またはスコープ演算子の前に名前空間として宣言されていない名前を使用するときに発生することができます。 この問題を解決するには、名前を宣言またはを使用前に、名前を宣言するヘッダーをインクルードします。

C2653 ことも可能です定義しようとする場合、*複合名前空間*、1 つまたは複数のスコープの入れ子になった名前空間名を含む名前空間。 複合の名前空間の定義が、c++ 17 の前に C++ では許可されていません。 複合名前空間を指定すると、Visual Studio 2015 Update 3 以降がサポートされて、 [/std:c + + 最新](../../build/reference/std-specify-language-standard-version.md)コンパイラ オプション。 以降 Visual C++ 2017 15.5 のバージョンでは、コンパイラは複合名前空間の定義をサポートと、 [/std:c + + 17](../../build/reference/std-specify-language-standard-version.md)オプションを指定します。

## <a name="examples"></a>使用例

この例では、スコープ名を使用するが、宣言されていないために、C2653 が生成されます。 コンパイラでは、クラス、構造体、共用体、またはスコープ演算子 (:) の前に名前空間の名前が必要です。

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

C++ 17 または以降の標準のコンパイルされていないコードで入れ子になった名前空間は、入れ子になった各レベルで明示的な名前空間宣言を使用する必要があります。

```cpp
// C2653b.cpp
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,
                          // C2429 thereafter. Use /std:c++17 or /std:c++latest to fix.

namespace a {             // Use this form for compliant code under /std:c++14 (the default)
   namespace b {          // or when using compilers before Visual Studio 2015 update 3.
      int i;
   }
}

int main() {
   a::b::i = 2;
}
```
