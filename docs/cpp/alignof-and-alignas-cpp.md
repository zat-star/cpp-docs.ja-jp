---
title: "alignof と alignas (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a506a3c44c3304e786c41a2eb049939d317778e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="alignof-and-alignas-c"></a>alignof と alignas (C++)
`alignas` 型指定子は、変数およびユーザー定義型のカスタムの配置を指定する移植可能な C++ の標準的な方法です。 `alignof` 演算子も同様に、指定された型または変数の配置を取得する、標準的で移植可能な方法です。  
  
## <a name="example"></a>例  
 クラス、スタックまたは共用体、あるいは個々のメンバーで `alignas` を使用できます。 複数の `alignas` 指定子が検出された場合、コンパイラは、最も厳密なもの (最大値を持つもの) を選択します。  
  
```cpp  
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  

int main()
{  
    std::cout << alignof(Bar) << std::endl; // output: 16  
}  
```  
  
## <a name="see-also"></a>参照  
 [アラインメント](../cpp/alignment-cpp-declarations.md)