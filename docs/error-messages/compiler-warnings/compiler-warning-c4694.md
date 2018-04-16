---
title: "コンパイラの警告 C4694 |Microsoft ドキュメント"
ms.date: 10/25/2017
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- C4694
dev_langs:
- C++
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f635aad0039812b50bd48a36f307ab5f60cba10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4694"></a>コンパイラの警告 C4694

> '*クラス*': シールされた抽象クラスは基底クラス' を持つことはできません*base_class*'

シールされた抽象クラスは参照型を継承できません。シールされた抽象クラスは、基底クラスの関数を実装することも、それ自体を基底クラスとして使用しすることもできません。

詳細については、次を参照してください。[抽象](../../windows/abstract-cpp-component-extensions.md)、[シール](../../windows/sealed-cpp-component-extensions.md)、および[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)です。

この警告は、自動的にエラーになります。 この動作を変更する場合は、使用[#pragma 警告](../../preprocessor/warning.md)です。

## <a name="example"></a>例

次の例では C4694 が生成されます。

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```