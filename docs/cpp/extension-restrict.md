---
title: "__restrict | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__restrict"
  - "__restrict_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__restrict キーワード [C++]"
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __restrict
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\_\_declspec \( [restrict](../cpp/restrict.md) \)** 修飾子と同様に、`__restrict` キーワードは、現在のスコープではシンボルがエイリアス化されないことを示します。  `__restrict` キーワードは、`__declspec ( restrict )` 修飾子とは次の点で相違があります。  
  
-   `__restrict` キーワードは変数に対してのみ有効です。`__declspec ( restrict )` は関数の宣言と定義内でのみ有効です。  
  
-   `__restrict` は C99 仕様の `restrict` に似ていますが、`__restrict` は C\+\+ または C プログラムで使用できます。  
  
-   `__restrict` が使用されていると、コンパイラは変数の非エイリアスのプロパティを伝達しません。  つまり、`__restrict` 変数を `__restrict` ではない変数に割り当てる場合、コンパイラは引き続き non\-\_\_restrict 変数のエイリアス化を許可します。  これは C99 仕様の `restrict` キーワードの動作とは異なります。  
  
 一般に、関数全体の動作に影響を及ぼす場合、キーワードよりも `__declspec ( restrict )` を使用する方が適切です。  
  
 Visual Studio 2015 以降では、C\+\+ 参照で `__restrict` を使用できます。  
  
> [!NOTE]
>  [volatile](../cpp/volatile-cpp.md) キーワードも持っている変数に対して使用すると、`volatile` が優先されます。  
  
## 使用例  
  
```  
// __restrict_keyword.c  
// compile with: /LD  
// In the following function, declare a and b as disjoint arrays  
// but do not have same assurance for c and d.  
void sum2(int n, int * __restrict a, int * __restrict b,   
          int * c, int * d) {  
   int i;  
   for (i = 0; i < n; i++) {  
      a[i] = b[i] + c[i];  
      c[i] = b[i] + d[i];  
    }  
}  
  
// By marking union members as __restrict, tell compiler that  
// only z.x or z.y will be accessed in any given scope.  
union z {  
   int * __restrict x;  
   double * __restrict y;  
};  
```  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)