---
title: "コンパイラ エラー C2512 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2512
dev_langs:
- C++
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57dbb542eee7e893253e6c3bdd3410c605a8d2db
ms.sourcegitcommit: 8ae12a602244a5853e941e5e8806e3545d876844
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2018
---
# <a name="compiler-error-c2512"></a>コンパイラ エラー C2512

> '*識別子*': 適切な既定コンス トラクターがない使用可能な  

A*既定のコンス トラクター*引数を必要としないコンス トラクターは指定したクラス、構造体、または共用体を使用します。 コンパイラでは、ユーザー定義のコンス トラクターが指定されていない場合にのみ、既定のコンス トラクターが用意されています。

Void 以外のパラメーターを受け取るコンス トラクターを提供する、パラメーターなしで (たとえば、配列の要素) として作成するのには、クラスを許可する場合は、また、既定のコンス トラクターを提供する必要があります。 既定のコンストラクターには、すべてのパラメーターに既定値を使用したコンストラクターを指定できます。

## <a name="example"></a>例

エラー C2512 の一般的な原因は、クラスまたは構造体を受け取るコンス トラクターの引数を定義するとき、しようとする引数を指定せずに構造体、クラスのインスタンスを宣言します。 たとえば、`struct B`以下が必要なコンス トラクターを宣言、`char *`引数、ものではない引数を受け取らないです。 `main`B のインスタンスが宣言されているが、引数が指定されていません。 B. の既定のコンス トラクターが見つからないため、コンパイラが C2512 を生成します。

```cpp
// C2512.cpp
// Compile with: cl /W4 c2512.cpp
// C2512 expected
struct B {
   B (char *) {}
   // Uncomment the following line to fix.
   // B() {}
};

int main() {
   B b;   // C2512 - This requires a default constructor
}
```

など、構造体またはクラスでは、既定のコンス トラクターを定義することによってこの問題を解決する`B() {}`、または、既定値を持つすべての引数など、コンス トラクター`B (char * = nullptr) {}`です。
