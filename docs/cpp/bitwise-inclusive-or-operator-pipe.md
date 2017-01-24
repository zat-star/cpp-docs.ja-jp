---
title: "ビット処理包括的 OR 演算子: | | Microsoft Docs"
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
  - "bitor"
  - "|"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "| 演算子"
  - "ビット処理演算子, OR 演算子"
  - "包括的 OR 演算子"
  - "OR 演算子, ビットごとの包括的"
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ビット処理包括的 OR 演算子: |
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
expression   
|  
 expression  
  
```  
  
## 解説  
 ビットごとの包括的 OR 演算子 \(         **&#124;** \) は、1 番目のオペランドの各ビットを 2 番目のオペランドの対応するビットと比較します。  どちらかのビットが 1 の場合、対応する結果のビットは 1 に設定されます。  それ以外の場合は、対応する結果ビットが 0 に設定されます。  
  
 ビットごとの包括的 OR 演算子のオペランドは両方とも整数型である必要があります。  オペランドには「[Arithmetic Conversion \(算術変換\)](../misc/arithmetic-conversions.md)」で説明している通常の算術変換が適用されます。  
  
## &#124; の演算子キーワード  
 `bitor` 演算子は、              **&#124;** と等価のテキストです。  プログラムで `bitor` 演算子にアクセスするには、2 つの方法があります。1 つはヘッダー ファイル `iso646.h` を含める方法で、もう 1 つは [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(言語拡張機能を無効にする\) コンパイラ オプションを使用してコンパイルする方法です。  
  
## 使用例  
  
```  
// expre_Bitwise_Inclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise inclusive OR  
#include <iostream>  
using namespace std;  
  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...  
}  
```  
  
## 参照  
 [C\+\+ ビット処理演算子](../Topic/C++%20Bitwise%20Operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C ビット処理演算子](../c-language/c-bitwise-operators.md)