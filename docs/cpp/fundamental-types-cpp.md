---
title: "基本的な型 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __wchar_t_cpp
- long_double_cpp
- unsigned
- wchar_t_cpp
- float_cpp
- wchar_t
- char
- char_cpp
- signed
- __wchar_t
- signed_cpp
- short
- double_cpp
- int_cpp
- long
- __intn_cpp
- short_cpp
- double
- unsigned_cpp
- float
- __intn
- long_cpp
- int
- long_double
- unsigned_int
- __int8
- __int8_cpp
- __int16
- __int16_cpp
- __int32
- __int32_cpp
- __int64
- __int64_cpp
- __int128
- __int128_cpp
dev_langs:
- C++
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type, C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type
- double data type, summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers, C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++], C++ data types
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 595c2d84ad18cae0c15ddba36388f66f10fecd49
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="fundamental-types--c"></a>基本型 (C++)
C++ の基本的な型は、整数、浮動小数点、および void の 3 つのカテゴリに分類されます。 整数型は整数を処理できます。 浮動小数点型は小数部分を含む可能性がある値を指定することができます。  
  
 [void](../cpp/void-cpp.md) 型は一連の空の値を示します。 `void` 型の変数は指定できません。値を返さない関数を宣言したり、型指定しないデータまたは任意の型のデータへのジェネリック ポインターを宣言したりする場合に主に使用します。 式は、 `void`型に明示的に変換するか、またはキャストできます。 ただし、このような式は次の用途に制限されています。  
  
-   式ステートメント (詳細については、「 [式](../cpp/expressions-cpp.md)」を参照)。  
  
-   コンマ演算子の左のオペランド (詳細については、「 [コンマ演算子](../cpp/comma-operator.md) 」を参照)。  
  
-   条件演算子の 2 番目または 3 番目のオペランド (`? :`)。 (詳細については、「 [条件演算子を含む式](../cpp/conditional-operator-q.md) 」を参照)。  
  
 型のサイズに適用される制限を次の表に示します。 これらの制限は、Microsoft の実装に依存しません。  
  
### <a name="fundamental-types-of-the-c-language"></a>C++ 言語の基本型  
  
|カテゴリ|型|目次|  
|--------------|----------|--------------|  
|整数型|`char`|`char` 型は、通常は基本実行文字セットのメンバーを含む整数型です。既定で、Microsoft C++ では ASCII です。<br /><br /> C++ コンパイラは、 `char`, `signed` `char`、および `unsigned` `char` 型の変数をそれぞれ異なる型の変数として処理します。 `char` 型の変数は、/J コンパイル オプションが使用されていない限り、 `int`  `signed` `char` に上位変換されます。 この場合、 `unsigned` `char` 型として扱われ、符号拡張なしで `int` に上位変換されます。|  
||`bool`|`bool` 型は、2 つの値 ( `true` または `false`) のいずれかを設定できる整数型です。 そのサイズは、指定されていません。|  
||`short`|`short` `int` 型 (または `short`型) は、 `char`型のサイズ以上、 `int`型のサイズ以下の整数型です。<br /><br /> `short` 型のオブジェクトは `signed` `short` か `unsigned short`として宣言できます。 `Signed short` は `short`のシノニムです。|  
||`int`|`int` 型は、 `short` `int`型のサイズ以上で、 `long`型のサイズ以下の整数型です。<br /><br /> `int` 型のオブジェクトは `signed` `int` か `unsigned` `int`として宣言できます。 `Signed` `int` は `int`のシノニムです。|  
||`__int8`, `__int16`, `__int32`, `__int64`|サイズが設定された整数 `__int n`( `n` は整数変数のビット単位のサイズ) `__int8`、 `__int16`、 `__int32` と `__int64` は Microsoft 固有キーワードです。 すべての型は、すべてのアーキテクチャで使用できます。 `(__int128`サポートされていません。)|  
||`long`|`long` 型 (または `long` `int`) は、 `int`型のサイズ以上の整数型です。<br /><br /> `long` 型のオブジェクトは `signed` `long` か `unsigned` `long`として宣言できます。 `Signed` `long` は `long`のシノニムです。|  
||`long` `long`|符号なしの `long`より大きい。<br /><br /> `long long` 型のオブジェクトは `signed` `long long` か `unsigned` `long long`として宣言できます。 `Signed` `long long` は `long long`のシノニムです。|  
||`wchar_t`, `__wchar_t`|`wchar_t` 型の変数はワイド文字またはマルチバイト文字型を指定します。 既定で、 `wchar_t` はネイティブ型ですが、 [/Zc:wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) を使用して、 `wchar_t` を `unsigned short`の typedef にできます。 `__wchar_t` 型は、ネイティブ `wchar_t` 型の Microsoft 固有のシノニムです。<br /><br /> ワイド文字型を指定するには、文字や文字列リテラルの前に L のプレフィックスを使用します。|  
|浮動小数点数|`float`|`float` 型は最小の浮動小数点型です。|  
||`double`|`double` 型は `float`型のサイズ以上で、 `long` `double`型のサイズ以下の浮動小数点型です。<br /><br /> Microsoft 固有: `long double` と `double` の表現は同じです。 ただし、 `long double` と `double` は別の型です。|  
||`long double`|`long` `double` 型は、 `double`型以上の浮動小数点型です。|  
  
 **Microsoft 固有の仕様**  
  
 次の表は、Microsoft C++ において基本的な型に必要とされるストレージの量の一覧です。  
  
### <a name="sizes-of-fundamental-types"></a>基本型のサイズ  
  
|型|サイズ|  
|----------|----------|  
|`bool`, `char`, `unsigned char`, `signed char`, `__int8`|1 バイト|  
|`__int16`, `short`, `unsigned short`, `wchar_t`, `__wchar_t`|2 バイト|  
|`float`、 `__int32`、 `int`、 `unsigned int`、 `long`、 `unsigned long`|4 バイト|  
|`double`, `__int64`, `long double`, `long long`|8 バイト|  
  
 **Microsoft 固有の仕様はここまで**  
  
 型ごとの値の範囲の概要については、「 [データ型の範囲](../cpp/data-type-ranges.md) 」を参照してください。  
  
 型変換の詳細については、「 [標準変換](../cpp/standard-conversions.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [データ型の範囲](../cpp/data-type-ranges.md)
