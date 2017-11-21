---
title: "コンパイラ エラー C2975 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2975
dev_langs: C++
helpviewer_keywords: C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65644cc13629481941ffdd8676e51311c665f106
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="compiler-error-c2975"></a>コンパイラ エラー C2975

> '*引数*': 無効なテンプレート引数を'*型*'、コンパイル時定数式が必要です

テンプレート引数が、テンプレート宣言と一致しません山かっこ内の定数式が表示されます。 変数は、テンプレートの実引数としては許可されません。 テンプレートの定義を調べて正しい型が指定されていることをご確認ください。

## <a name="example"></a>例

次の例では、C2975 を生成し、正しい使用法も示しています。

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

C2975 にも発生 &#95; &#95; を使用する場合行 &#95; #95コンパイル時定数として[/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)です。 1 つのソリューションは、使用してコンパイルすること[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)の代わりに**/ZI**です。

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```