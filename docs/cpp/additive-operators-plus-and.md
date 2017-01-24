---
title: "加法演算子: + および - | Microsoft Docs"
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
  - "-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "- 演算子, 加法演算子 (C++)"
  - "+ 演算子, 加法演算子"
  - "加法演算子"
  - "算術演算子 [C++], 加法演算子"
  - "演算子 [C++], 加算"
  - "減算演算子, 加法演算子"
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 加法演算子: + および -
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
expression + expression   
expression – expression  
```  
  
## 解説  
 加法演算子を次に示します。  
  
-   加算 \(**\+**\)  
  
-   減算 \(**\-**\)  
  
 これらの二項演算子の結合規則は、左から右方向です。  
  
 加法演算子は、数値型またはポインター型のオペランドを受け取ります。  加算 \(**\+**\) 演算子の結果はオペランドの合計です。  減算 \(**–**\) 演算子の結果は、オペランド間の差です。  オペランドの一方または両方がポインターの場合、これらのオペランドは、関数ではなくオブジェクトのポインターである必要があります。  両方のオペランドがポインターの場合、両方とも同じ配列のオブジェクトへのポインターでない限り意味がありません。  
  
 加法演算子は、*数値*、*整数*、および*スカラー*型のオペランドを受け取ります。  次の表にこれらの定義を示します。  
  
### 加法演算子と併用される型  
  
|型|説明|  
|-------|--------|  
|*arithmetic*|整数型および浮動型はまとめて "演算" 型と呼ばれます。|  
|*integral*|すべてのサイズ \(long、short\) の char 型と int 型、および列挙型は "整数" 型です。|  
|*scalar*|スカラー オペランドは、数値型またはポインター型のオペランドです。|  
  
 これらの演算子の有効な組み合わせは以下のとおりです。  
  
 *arithmetic* \+ *arithmetic*  
  
 *scalar* \+ *integral*  
  
 *integral* \+ *scalar*  
  
 *arithmetic* – *arithmetic*  
  
 *scalar* – *scalar*  
  
 加算と減算が同等の操作ではないことに注意してください。  
  
 オペランドが両方とも数値型である場合、「[算術変換](../misc/arithmetic-conversions.md)」で説明されている変換がオペランドに適用され、結果は変換後の型になります。  
  
## 使用例  
  
```  
// expre_Additive_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
#define SIZE 5  
using namespace std;  
int main() {  
   int i = 5, j = 10;  
   int n[SIZE] = { 0, 1, 2, 3, 4 };  
   cout  << "5 + 10 = " << i + j << endl  
         << "5 - 10 = " << i - j << endl;  
  
   // use pointer arithmetic on array  
  
   cout << "n[3] = " << *( n + 3 ) << endl;  
}  
```  
  
## ポインターの加算  
 加算演算のオペランドの 1 つがオブジェクトの配列へのポインターである場合、もう一方は整数型である必要があります。  結果は、元のポインターと同じ型のポインターで、他の配列要素をポイントします。  この概念を次のコードに示します。  
  
```  
short IntArray[10]; // Objects of type short occupy 2 bytes  
short *pIntArray = IntArray;  
  
for( int i = 0; i < 10; ++i )  
{  
    *pIntArray = i;  
    cout << *pIntArray << "\n";  
    pIntArray = pIntArray + 1;  
}  
```  
  
 整数値 1 が `pIntArray` に追加されますが、これは "アドレスに 1 を追加する" ことを意味しません。そうではなく、2 バイト \(または `sizeof( int )`\) 移動するように、"配列内の次のオブジェクトを指すようにポインターを調整する" ことを意味します。  
  
> [!NOTE]
>  `pIntArray = pIntArray + 1` のような形式のコードは、C\+\+ プログラムではあまり見られません。インクリメントを行う場合は、`pIntArray++` または `pIntArray += 1` のような形式を使用することをお勧めします。  
  
## ポインターの減算  
 両方のオペランドがポインターの場合、減算の結果は、オペランド間の \(配列要素内の\) 差になります。  減算式は ptrdiff\_t 型 \(標準インクルード ファイル STDDEF.H で定義\) の符号付き整数の結果を生成します。  
  
 それが 2 番目のオペランドである限り、オペランドの 1 つは整数型にできます。  減算の結果は、元のポインターと同じ型です。  減算の値は \(*n* – *i*\) 番目の配列要素へのポインターです。*n* は元のポインターが指す要素、*i* は 2 番目のオペランドの整数値です。  
  
## 参照  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [ポインター型の追加](../misc/addition-of-pointer-types.md)   
 [ポインター型の減算](../misc/subtraction-of-pointer-types.md)   
 [C 加法演算子](../c-language/c-additive-operators.md)