---
title: "コンパイラ エラー C2457 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2457
dev_langs: C++
helpviewer_keywords: C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff89bb3635936ae0f797438d73f71adf1ef08de7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2457"></a>コンパイラ エラー C2457

> '*マクロ*': 定義済みマクロは関数本体の外部で表示できません。

など、定義済みマクロを使用しようとしています。 [&#95; &#95;です。関数 &#95; #95](../../preprocessor/predefined-macros.md)、グローバル空間内です。

## <a name="example"></a>例

次の例では、C2457 を生成し、正しい使用法も示しています。

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```