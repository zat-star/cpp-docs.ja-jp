---
title: "数値、ブール値、およびポインターのリテラル (C++) | Microsoft Docs"
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
  - "定数, リテラル"
  - "リテラル"
  - "リテラル, C++"
ms.assetid: 17c09fc3-3ad7-47e2-8b48-ba8ae994edc8
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 数値、ブール値、およびポインターのリテラル (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リテラルとは、値を直接に表すプログラム要素です。  ここでは、整数型、浮動小数点型、ブール値型、およびポインター型のリテラルについて説明します。  文字列リテラルおよび文字リテラルについては、「[文字列リテラルおよび文字リテラル \(C\+\+\)](../cpp/string-and-character-literals-cpp.md)」を参照してください。  これらのカテゴリのいずれかに基づく独自のリテラルを定義することもできます。詳細については、「[ユーザー定義リテラル \(C\+\+\)](../Topic/User-Defined%20Literals%20%20\(C++\).md)」を参照してください。  
  
 」を参照してください。  リテラルは多様なコンテキストで使用できますが、最も一般的な用途は、名前付きの変数を初期化することと、関数に引数を渡すことです。  
  
```  
const int answer = 42; // integer literal  
double d = sin(108.87);     //floating point literal passed to sin function  
bool b = true;              // boolean literal  
MyClass* mc = nullptr;      // pointer literal  
  
```  
  
 リテラルの解釈方法やリテラルに与える特定の型を、コンパイラに指示することが重要な場合があります。  リテラルにプレフィックスまたはサフィックスを追加することによってこれを行います。  たとえば、プレフィックス 0x は、それに続く数値を 16 進数値として解釈するようコンパイラに指示します \(0x35 など\)。  ULL サフィックスは、その値を `unsigned long long` 型として扱うようコンパイラに指示します \(5894345ULL など\)。  各リテラル型のプレフィックスおよびサフィックスの完全な一覧については、次のセクションを参照してください。  
  
## 構文  
  
## 整数リテラル  
 整数リテラルは数字で始まり、小数部や指数はありません。  整数リテラルには、10 進数、8 進数、または 16 進数形式を指定できます。  符号付きまたは符号なしの型と、long または short の型を指定できます。  
  
 プレフィックスもサフィックスも付かない場合、コンパイラは整数リテラル値に型 `int` \(32 ビット\) を与えます。値が収まりきらない場合は型 `long long` \(64 ビット\) を与えます。  
  
 10 進数の整数リテラルを指定するには、ゼロ以外の数字で指定を始めます。  次に例を示します。  
  
```  
int i = 157;   // Decimal literal  
int j = 0198;       // Not a decimal number; erroneous octal literal  
int k = 0365;       // Leading zero specifies octal literal, not decimal  
int m = 36'000'000  // digit separators make large values more readable  
int   
```  
  
 8 進数の整数リテラルを指定するには、0 で指定を始め、0 ～ 7 の範囲の一連の桁を続けます。  数字の 8 と 9 は、8 進数のリテラルを指定する場合はエラーになります。  次に例を示します。  
  
```  
int i = 0377;   // Octal literal  
int j = 0397;        // Error: 9 is not an octal digit  
```  
  
 16 進数の整数リテラルを指定するには、`0x` または `0X` \("x" の大文字と小文字は区別されません\) で指定を始め、`0` ～ `9` と `a` \(または `A`\) ～ `f` \(または `F`\) の範囲の一連の桁を続けます。  16 進数の `a` \(または `A`\) ～ `f` \(または `F`\) は、10 ～ 15 の範囲の値を示します。  次に例を示します。  
  
```  
int i = 0x3fff;   // Hexadecimal literal  
int j = 0X3FFF;        // Equal to i  
```  
  
 符号なしの型を指定するには、サフィックスとして **u** または **U** を使用します。  long 型を指定するには、サフィックスとして **l** または **L** を使用します。  64 ビットの整数型を指定するには、サフィックスとして LL、ll を使用します。  i64 サフィックスはまだサポートされていますが、Microsoft に固有なものであり移植性がないため、使用を避けることをお勧めします。  次に例を示します。  
  
```  
unsigned val_1 = 328u;             // Unsigned value  
long val_2 = 0x7FFFFFL;                 // Long value specified   
                                        //  as hex literal  
unsigned long val_3 = 0776745ul;        // Unsigned long value  
auto val_4 = 108LL;                           // signed long long  
auto val_4 = 0x8000000000000000ULL << 16;     // unsigned long long   
```  
  
 **桁区切り記号**: 一重引用符 \(アポストロフィ\) を使用して、大きな数の位取りを人間が読み取りやすいように分割できます。  区切り記号はコンパイルに影響しません。  
  
```  
long long i = 24'847'458'121  
```  
  
## 浮動小数点リテラル  
 浮動小数点リテラルは、小数部分が必要な値を指定します。  これらの値には、小数点 \(**.**\) が含まれ、指数を含めることができます。  
  
 浮動小数点リテラルには、数値の値を指定する "仮数"、数値の大きさを指定する "指数"、およびリテラルの型を指定する省略可能なサフィックスが含まれます。  仮数は、一連の数字の後ろにピリオドを続け、その後ろに数値の小数部分を表す省略可能な一連の数字を続けることで指定されます。  次に例を示します。  
  
```  
18.46  
38.  
```  
  
 指数部がある場合は、次の例に示すように、10 の累乗として数値の大きさを指定します。  
  
```  
18.46e0      // 18.46  
18.46e1           // 184.6  
```  
  
 指数は、同じ意味を持つ **e** または **E** を使用して指定できます。その後に、省略可能な符号 \(\+ または \-\) と一連の数値が続きます。  指数部がある場合、`18E0` などの整数では後続の小数点は不要です。  
  
 浮動小数点リテラルは、既定で **double** 型になります。  サフィックス **f** または **l** \(または、**F** または **L**。サフィックスでは大文字と小文字は区別されません\) を使用して、リテラルをそれぞれ **float** または `long double` として指定できます。  
  
 `long double` と **double** は表現は同じですが、同じ型ではありません。  たとえば、次のようにオーバーロードされた関数を指定できます。  
  
```  
void func( double );  
```  
  
 および  
  
```  
void func( long double );  
```  
  
## ブール型リテラル  
 ブール型リテラルは `true` および `false`です。  
  
## ポインター型リテラル \(C\+\+11\)  
 C\+\+ では、ゼロ初期化ポインターを指定する [nullptr](../Topic/nullptr.md) リテラルを導入しています。  移植可能なコードでは、整数型の 0 または NULL などのマクロの代わりに `nullptr` を使用するようお勧めします。  
  
## バイナリ リテラル \(C\+\+14\)  
 `0B` または `0b` をプレフィックスとして使用することにより、その後に一連の 1 と 0 が続く、バイナリ文字列を指定することができます。  
  
```  
  
auto x = 0B001101 ; // int  
auto y = 0b000001 ; // int  
```  
  
## "マジック定数" としてリテラルを使用しないでください。  
 常に適切なプログラミング方法であるとは言えませんが、リテラルは式およびステートメント内で直接使用できます。  
  
```  
if (num < 100)  
    return "Success";  
  
```  
  
 前の例では、"MAXIMUM\_ERROR\_THRESHOLD"など、明確な意味を伝達する名前付き定数を使用する方がよい場合があります。  戻り値の "Success" がエンドユーザーに表示される場合は、ファイルの 1 つの場所に格納でき他の言語にローカライズできる名前付き文字列定数を使用する方がよい場合があります。  名前付き定数を使用すると、他のユーザーにとってもコードの意図が理解しやすくなります。  
  
## 参照  
 [構文規則](../cpp/lexical-conventions.md)   
 [C\+\+ 整数定数](http://msdn.microsoft.com/ja-jp/1f3b58a4-8346-4533-ba6e-df26d76f8dcf)   
 [C\+\+ 文字リテラル](http://msdn.microsoft.com/ja-jp/a7901c61-524d-47c6-beb6-d9dacc2e72ed)   
 [C\+\+ 浮動小数点定数](http://msdn.microsoft.com/ja-jp/f6273f24-a876-4484-a7a2-e82275692ad3)   
 [C\+\+ 文字列リテラル](../cpp/string-and-character-literals-cpp.md)   
 [C\+\+ ユーザー定義リテラル](../Topic/User-Defined%20Literals%20%20\(C++\).md)