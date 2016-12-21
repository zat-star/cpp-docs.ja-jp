---
title: "基本型 (C++) | Microsoft Docs"
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
  - "__wchar_t_cpp"
  - "long_double_cpp"
  - "unsigned"
  - "wchar_t_cpp"
  - "float_cpp"
  - "wchar_t"
  - "char"
  - "char_cpp"
  - "signed"
  - "__wchar_t"
  - "signed_cpp"
  - "short"
  - "double_cpp"
  - "int_cpp"
  - "long"
  - "__intn_cpp"
  - "short_cpp"
  - "double"
  - "unsigned_cpp"
  - "float"
  - "__intn"
  - "long_cpp"
  - "int"
  - "long_double"
  - "unsigned_int"
  - "__int8"
  - "__int8_cpp"
  - "__int16"
  - "__int16_cpp"
  - "__int32"
  - "__int32_cpp"
  - "__int64"
  - "__int64_cpp"
  - "__int128"
  - "__int128_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wchar_t キーワード [C++]"
  - "算術演算 [C++], 型"
  - "char キーワード [C++]"
  - "データ型 [C++], void"
  - "Double 型, 型の概要"
  - "float キーワード [C++]"
  - "浮動小数点数, C++ のデータ型"
  - "int データ型"
  - "整数型, C++ のデータ型"
  - "整数型"
  - "整数型, C++"
  - "long double キーワード [C++]"
  - "long キーワード [C++]"
  - "long キーワード [C++], C++ のデータ型"
  - "long long キーワード [C++]"
  - "short データ型"
  - "signed 型 [C++]"
  - "signed 型 [C++], データ型の概要"
  - "指定子 [C++], 型"
  - "ストレージ [C++], 基本型"
  - "型の格納 [C++]"
  - "型指定子 [C++]"
  - "unsigned 型 [C++]"
  - "unsigned 型 [C++], データ型の概要"
  - "void キーワード [C++]"
  - "wchar_t キーワード [C++]"
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
caps.latest.revision: 19
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 基本型 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ の基本的な型は、整数、浮動小数点、および void の 3 つのカテゴリに分類されます。 整数型は整数を処理できます。 浮動小数点型は小数部分を含む可能性がある値を指定することができます。  
  
 [void](../cpp/void-cpp.md) 型は一連の空の値を示します。`void` 型の変数は指定できません。値を返さない関数を宣言したり、型指定しないデータまたは任意の型のデータへのジェネリック ポインターを宣言したりする場合に主に使用します。 式は、`void` 型に明示的に変換するか、またはキャストできます。 ただし、このような式は次の用途に制限されています。  
  
-   式ステートメント  \(詳細については、「[式](../cpp/expressions-cpp.md)」を参照\)。  
  
-   コンマ演算子の左のオペランド  \(詳細については、「[コンマ演算子](../cpp/comma-operator.md)」を参照\)。  
  
-   条件演算子の 2 番目または 3 番目のオペランド \(`? :`\) \(詳細については、「[条件演算子を含む式](../cpp/conditional-operator-q.md)」を参照\)。  
  
 型のサイズに適用される制限を次の表に示します。 これらの制限は、Microsoft の実装に依存しません。  
  
### C\+\+ 言語の基本型  
  
|カテゴリ|型|目次|  
|----------|-------|--------|  
|整数型|`char`|`char` 型は、通常は基本実行文字セットのメンバーを含む整数型です。既定で、Microsoft C\+\+ では ASCII です。<br /><br /> C\+\+ コンパイラは、`char`、`signed` `char`、および `unsigned` `char` 型の変数をそれぞれ異なる型の変数として処理します。`char` 型の変数は、\/J コンパイル オプションが使用されていない限り、`signed` `char` 型であるかのように、既定で `int` に上位変換されます。 この場合、`unsigned` `char` 型として扱われ、符号拡張なしで `int` に上位変換されます。|  
||`bool`|`bool` 型は、2 つの値 \(`true` または `false`\) のいずれかを設定できる整数型です。 そのサイズは、指定されていません。|  
||`short`|`short` `int` 型 \(または `short` 型\) は、`char` 型のサイズ以上、`int` 型のサイズ以下の整数型です。<br /><br /> `short` 型のオブジェクトは `signed` `short` か `unsigned short` として宣言できます。`Signed short` は `short` のシノニムです。|  
||`int`|`int` 型は、`short` `int` 型のサイズ以上で、`long` 型のサイズ以下の整数型です。<br /><br /> `int` 型のオブジェクトは `signed` `int` か `unsigned` `int` として宣言できます。`Signed` `int` は `int` のシノニムです。|  
||`__int8`, `__int16`, `__int32`, `__int64`, `__int128`|サイズが設定された整数 `__int``n` \(`n` は整数変数のビット単位のサイズ\)  \(`__int8`、`__int16`、`__int32`、`__int64`、および `__int128` は Microsoft 固有キーワードです。 すべての型がすべてのアーキテクチャで使用可能というわけではありません\)。|  
||`long`|`long` 型 \(または `long` `int`\) は、`int` 型のサイズ以上の整数型です。<br /><br /> `long` 型のオブジェクトは `signed` `long` または `unsigned` `long` として宣言できます。`Signed` `long` は `long` のシノニムです。|  
||`long` `long`|符号なしの `long` より大きい。<br /><br /> `long long` 型のオブジェクトは `signed` `long long` または `unsigned` `long long` として宣言できます。`Signed` `long long` は `long long` のシノニムです。|  
||`wchar_t`, `__wchar_t`|`wchar_t` 型の変数はワイド文字またはマルチバイト文字型を指定します。 既定で、`wchar_t` はネイティブ型ですが、[\/Zc:wchar\_t\-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) を使用して、`wchar_t` を `unsigned short` の typedef にできます。`__wchar_t` 型は、ネイティブ `wchar_t` 型の Microsoft 固有のシノニムです。<br /><br /> ワイド文字型を指定するには、文字や文字列リテラルの前に L のプレフィックスを使用します。|  
|浮動小数点数|`float`|`float` 型は最小の浮動小数点型です。|  
||`double`|`double` 型は `float` 型のサイズ以上で、`long` `double` 型のサイズ以下の浮動小数点型です。<br /><br /> Microsoft 固有: `long double` と `double` の表現は同じです。 ただし、`long double` と `double` は別の型です。|  
||`long double`|`long` `double` 型は、`double` 型以上の浮動小数点型です。|  
  
 **Microsoft 固有の仕様**  
  
 次の表は、Microsoft C\+\+ において基本的な型に必要とされるストレージの量の一覧です。  
  
### 基本型のサイズ  
  
|型|サイズ|  
|-------|---------|  
|`bool`, `char`, `unsigned char`, `signed char`, `__int8`|1 バイト|  
|`__int16`, `short`, `unsigned short`, `wchar_t`, `__wchar_t`|2 バイト|  
|`float`, `__int32`, `int`, `unsigned int`, `long`, `unsigned long`|4 バイト|  
|`double`, `__int64`, `long double`, `long long`|8 バイト|  
|`__int128`|16 バイト|  
  
 **Microsoft 固有の仕様はここまで**  
  
 型ごとの値の範囲の概要については、「[データ型の範囲](../cpp/data-type-ranges.md)」を参照してください。  
  
 型変換の詳細については、「[標準変換](../cpp/standard-conversions.md)」を参照してください。  
  
## 参照  
 [データ型の範囲](../cpp/data-type-ranges.md)