---
title: "ビット処理排他的 OR 演算子: ^ | Microsoft Docs"
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
helpviewer_keywords: 
  - "^ 演算子"
  - "ビット処理演算子, OR 演算子"
  - "排他的 OR 演算子"
  - "演算子 [C++], ビット処理"
  - "演算子 [C++], 論理"
  - "OR 演算子, ビットごとの排他的"
  - "XOR 演算子"
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ビット処理排他的 OR 演算子: ^
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
expression ^ expression  
```  
  
## 解説  
 ビットごとの排他的 OR 演算子 \(**^**\) は、最初のオペランドの各ビットを 2 番目のオペランドの対応するビットと比較します。  一方のビットが 0 でもう一方のビットが 1 の場合、対応する結果のビットは 1 に設定されます。  それ以外の場合は、対応する結果ビットが 0 に設定されます。  
  
 ビットごとの排他的 OR 演算子のオペランドは両方とも整数型である必要があります。  オペランドには「[Arithmetic Conversion \(算術変換\)](../misc/arithmetic-conversions.md)」で説明している通常の算術変換が適用されます。  
  
## ^ の演算子キーワード  
 **xor** は、テキストの場合に **^** に相当する演算子です。  プログラムで **xor** 演算子にアクセスするには、2 つの方法があります。1 つはヘッダー ファイル `iso646.h` を含める方法で、もう 1 つは [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(言語拡張機能を無効にする\) コンパイラ オプションを使用してコンパイルする方法です。  
  
## 使用例  
  
```  
// expre_Bitwise_Exclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise exclusive OR  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xFFFF;      // pattern 1111 ...  
  
   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...  
}  
```  
  
## 参照  
 [C\+\+ ビット処理演算子](../Topic/C++%20Bitwise%20Operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C ビット処理演算子](../c-language/c-bitwise-operators.md)