---
title: "間接演算子とアドレス演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- address-of operator (&)
- '* operator'
- operators [C++], address-of
- ampersand operator (&)
- '* operator, indirection operator'
- addresses [C++], indirection
- addresses [C++]
- indirection operator
- '& operator, address-of operator'
- null pointers [C++]
- '* operator, address-of operator'
- operators [C++], indirection
ms.assetid: 10d62b00-12ba-4ea9-a2d5-09ac29ca2232
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 715221da8ea960f19e9c4ab0e386afc61c3439fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="indirection-and-address-of-operators"></a>間接演算子とアドレス演算子
間接演算子 (**\***) は、ポインターを介して値に間接的にアクセスします。 オペランドは、ポインター値である必要があります。 演算の結果は、オペランドによってアドレス指定される値です。つまり、オペランドがポイントするアドレスでの値です。 結果の型は、オペランドでアドレス指定する型です。  
  
 オペランドが関数を指している場合、結果は関数指定子になります。 格納場所を指している場合、結果は格納場所を指定する左辺値になります。  
  
 ポインターの値が無効な場合、結果は未定義になります。 次の一覧に、ポインター値が無効になる一般的な条件をいくつか示します。  
  
-   ポインターが null ポインターです。  
  
-   ポインターが、参照時に見えないローカル項目のアドレスを指定しています。  
  
-   ポインターが、指されているオブジェクトの型ではアラインメントが不適切なアドレスを指定しています。  
  
-   ポインターが、実行プログラムで使用されていないアドレスを指定しています。  
  
 アドレス演算子 (**&**) は、オペランドのアドレスを与えます。 アドレス演算子のオペランドは、関数指定子です。または、ビット フィールドではなく、**register** ストレージ クラス指定子で宣言されていないオブジェクトを指定する左辺値です。  
  
 アドレス演算子の結果は、オペランドへのポインターです。 ポインターによってアドレス指定される型は、オペランドの型です。  
  
 アドレス演算子は、ファイル スコープ レベルで宣言された基本型、構造体型、または共用体型を持つ変数、または添字配列参照だけに適用できます。 これらの式では、アドレス演算子を含まない定数式を、アドレス式に加算したりアドレス式から減算できます。  
  
## <a name="examples"></a>使用例  
 以下に挙げる例では、次の宣言を使用します。  
  
```  
int *pa, x;  
int a[20];  
double d;  
```  
  
 このステートメントはアドレス演算子を使用しています。  
  
```  
pa = &a[5];  
```  
  
 アドレス演算子 (**&**) は、配列 `a` の 6 番目の要素のアドレスを受け取ります。 結果は、ポインター変数 `pa` に格納されます。  
  
```  
x = *pa;  
```  
  
 この例では、間接演算子 (**\***) は、`pa` に格納されているアドレスにある `int` 値にアクセスするために使用されます。 その値は整数変数 `x` に代入されます。  
  
```  
if( x == *&x )  
    printf( "True\n" );  
```  
  
 この例では、`True` のアドレスに間接演算子を適用した結果が `x` と同じであることを示す単語 `x` が出力されます。  
  
```  
int roundup( void );     /* Function declaration */  
  
int  *proundup  = roundup;  
int  *pround  = &roundup;  
```  
  
 関数 `roundup` を宣言した後、`roundup` への 2 つのポインターを宣言して、初期化しています。 最初のポインター、`proundup` は、関数名のみを使用して初期化され、2 番目のポインター、`pround` は、初期化時にアドレス演算子が使用されています。 これらの初期化は同じ意味を持ちます。  
  
## <a name="see-also"></a>参照  
 [間接演算子: *](../cpp/indirection-operator-star.md)   
 [address-of 演算子: &](../cpp/address-of-operator-amp.md)