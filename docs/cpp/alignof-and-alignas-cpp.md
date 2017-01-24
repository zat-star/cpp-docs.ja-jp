---
title: "alignof と alignas (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# alignof と alignas (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`alignas` 型指定子は、変数およびユーザー定義型のカスタムの配置を指定する移植可能な C\+\+ の標準的な方法です。  `alignof` 演算子も同様に、指定された型または変数の配置を取得する、標準的で移植可能な方法です。  
  
## 例  
 クラス、スタックまたは共用体、あるいは個々のメンバーで `alignas` を使用できます。  複数の `alignas` 指定子が検出された場合、コンパイラは、最も厳密なもの \(最大値を持つもの\) を選択します。  
  
```  
struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  
…  
cout << alignof(Bar) << endl; // output: 16  
  
```  
  
## 参照  
 [アラインメント](../cpp/alignment-cpp-declarations.md)