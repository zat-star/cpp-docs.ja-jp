---
title: "コンパイラの警告 C4868 |Microsoft ドキュメント"
ms.date: 10/26/2017
ms.topic: error-reference
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 261e826043a4f922902de91573a16707897ae6b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4868"></a>コンパイラの警告 (レベル 4) C4868

> '_ファイル_(*line_number*)' コンパイラは、中かっこで囲んだ初期化子リストで左から右へ評価順序を強制いない可能性があります

中かっこで囲んだ初期化子リストの要素では、左から右へ順番に評価します。 これで、コンパイラがこの順序を保証できない 2 つのケースがある: 値で渡されるオブジェクトは、一部の要素には、2 つ2 番目にコンパイルするときに、`/clr`オブジェクトのフィールドまたは配列の要素は、要素の一部です。 コンパイラは、左から右へ評価を保証できない場合に警告 C4868 を出力します。

この警告は、Visual C 2015 Update 2 で行ったコンパイラ準拠作業の結果として生成できます。 Visual C 2015 Update 2 の前にコンパイルされたコード C4868 を生成できます。

既定では、この警告はオフに設定されています。 使用して`/Wall`この警告をアクティブにします。

この警告を解決するには、まず初期化子リストの要素の左から右へ評価が要素の評価が順序に依存する副作用を生じる可能性があるときなど、必要かどうかを検討します。 多くの場合、要素が評価される順序に目に見える効果はありません。

評価の順序が左から右である場合は、かどうか、要素を渡すことはことを検討してください`const`代わりに参照します。 この変更は、次のコード サンプルで警告を排除します。

## <a name="example"></a>例

この例では、C4868 を生成し、その修正方法を示しています。

```cpp
// C4868.cpp
// compile with: /c /Wall
#include <cstdio>

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x): x(x) {}

    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)
    {
        printf("Constructing %d\n", h.x);
    }
};

class TripWarning4868
{
public:
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}

    // This variation will not trigger the warning:
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}
};

int main()
{
    HasCopyConstructor a{1};
    HasCopyConstructor b{2};

    // the warning will indicate the below line, the usage of the braced initializer list.
    TripWarning4868 warningOnThisLine{a, b};
};
```