---
title: "コンパイラ エラー C2429 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6882804d1ddf2e4f83947e310cde4c8c114120d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2429"></a>コンパイラ エラー C2429

> '*言語機能*'コンパイラ フラグが必要'*コンパイラ オプション*'

言語機能には、サポートについては、特定のコンパイラ オプションが必要です。

エラー **C2429: 言語機能 '入れ子になった名前空間の定義' コンパイラ フラグが必要 '/std:c:operator++ 17'**定義しようとする場合に生成される、*複合名前空間*、1 つまたは複数を含む名前空間名前空間のスコープにネストされた名前、Visual Studio 2015 更新プログラム 5 以降します。 (Visual Studio 2017 15.3 のバージョンで、 **/std:c + + 最新**スイッチが必要です)。複合の名前空間の定義が、c++ 17 の前に C++ では許可されていません。 コンパイラは、複合名前空間の定義をサポートしているときに、 [/std:c + + 17](../../build/reference/std-specify-language-standard-version.md)コンパイラ オプションを指定します。

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
