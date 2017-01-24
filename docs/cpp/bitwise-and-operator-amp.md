---
title: "ビット処理 AND 演算子: &amp; | Microsoft Docs"
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
  - "bitand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& 演算子, ビット処理演算子"
  - "AND 演算子"
  - "ビット処理演算子, AND 演算子"
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ビット処理 AND 演算子: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
expression   
&  
 expression  
  
```  
  
## 解説  
 式は、他の and 式、または \(以下に言及する型制限に基づき\) 等価式、関係式、加算式、乗算式、メンバー式へのポインター、キャスト式、単項式、後置式、または 1 次式である場合もあります。  
  
 ビットごとの AND 演算子 \(**&**\) は、最初のオペランドの各ビットを 2 番目のオペランドの対応するビットと比較します。  両方のビットが 1 の場合、対応する結果のビットは 1 に設定されます。  それ以外の場合は、対応する結果ビットが 0 に設定されます。  
  
 ビットごとの AND 演算子のオペランドは両方とも整数型である必要があります。  オペランドには「[Arithmetic Conversion \(算術変換\)](../misc/arithmetic-conversions.md)」で説明している通常の算術変換が適用されます。  
  
## & の演算子キーワード  
 `bitand` 演算子は **&** の代替表現です。  プログラムで `bitand` 演算子にアクセスするには、2 つの方法があります。1 つはヘッダー ファイル `iso646.h` を含める方法で、もう 1 つは [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(言語拡張機能を無効にする\) コンパイラ オプションを使用してコンパイルする方法です。  
  
## 使用例  
  
```  
// expre_Bitwise_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise AND  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0xFFFF;      // pattern 1111 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...  
}  
```  
  
## 参照  
 [C\+\+ ビット処理演算子](../Topic/C++%20Bitwise%20Operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C ビット処理演算子](../c-language/c-bitwise-operators.md)