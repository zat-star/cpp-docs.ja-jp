---
title: "データ型の範囲 | Microsoft Docs"
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
  - "unsigned"
  - "wchar_t"
  - "char"
  - "signed"
  - "short"
  - "long"
  - "double"
  - "float"
  - "int"
  - "long_double"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "float キーワード [C++]"
  - "char キーワード [C++]"
  - "unsigned long"
  - "__wchar_t キーワード [C++]"
  - "unsigned short int"
  - "enum キーワード"
  - "unsigned char キーワード [C++]"
  - "整数データ型、データ型の範囲"
  - "int データ型"
  - "データ型 [C++]、範囲"
  - "unsigned int"
  - "short データ型"
  - "short int データ"
  - "符号付きデータ型 [C++]、データ型の範囲"
  - "long long キーワード [C++]"
  - "long double キーワード [C++]"
  - "倍精度浮動小数点データ型、データ型の範囲"
  - "signed short int"
  - "unsigned short"
  - "サイズ指定された整数型"
  - "signed int"
  - "signed long int"
  - "signed char キーワード [C++]"
  - "wchar_t キーワード [C++]"
  - "long キーワード [C++]"
  - "範囲 [C++]"
  - "符号なしデータ型 [C++]、データ型の範囲"
  - "浮動小数点数、データ型の範囲"
  - "範囲 [C++]、データ型"
  - "long int キーワード [C++]"
  - "unsigned long int"
ms.assetid: 3691ceca-05fb-4b82-b1ae-5c4618cda91a
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# データ型の範囲
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C++ の 32 ビットおよび 64 ビット コンパイラは、この記事の次の表に示す型を認識します。  
  
-   `int` (`unsigned``int`)  
  
-   `__int8` (`unsigned``__int8`)  
  
-   `__int16` (`unsigned``__int16`)  
  
-   `__int32` (`unsigned``__int32`)  
  
-   `__int64` (`unsigned``__int64`)  
  
-   `short` (`unsigned``short`)  
  
-   `long` (`unsigned``long`)  
  
-   `long` `long` (`unsigned``long``long`)  
  
 データ型の名前が 2 つのアンダースコア (`__`) で始まる場合、その型は非標準です。  
  
 次の表で指定している範囲にはその最大値と最小値も含まれます。  
  
|型の名前|バイト|その他の名前|値の範囲|  
|---------------|-----------|-----------------|---------------------|  
|int|4|signed|-2,147,483,648 ～ 2,147,483,647|  
|unsigned int|4|unsigned|0 ～ 4,294,967,295|  
|__int8|1|char|-128 ～ 127|  
|unsigned __int8|1|unsigned char|0 ～ 255|  
|__int16|2|short、short int、signed short int|-32,768 ～ 32,767|  
|unsigned __int16|2|unsigned short、unsigned short int|0 ～ 65,535|  
|__int32|4|signed、signed int、int|-2,147,483,648 ～ 2,147,483,647|  
|unsigned __int32|4|unsigned、unsigned int|0 ～ 4,294,967,295|  
|__int64|8|long long、signed long long|– 9,223,372,036,854,775,808 ～ 9,223,372,036,854,775,807|  
|unsigned __int64|8|unsigned long long|0 ～ 18,446,744,073,709,551,615|  
|bool|1|none|false または true|  
|char|1|none|既定では -128 ～ 127<br /><br /> [/J](../build/reference/j-default-char-type-is-unsigned.md) を使用してコンパイルするときは 0 〜 255|  
|signed char|1|none|-128 ～ 127|  
|unsigned char|1|none|0 ～ 255|  
|short|2|short int、signed short int|-32,768 ～ 32,767|  
|unsigned short|2|unsigned short int|0 ～ 65,535|  
|long|4|long int、signed long int|-2,147,483,648 ～ 2,147,483,647|  
|unsigned long|4|unsigned long int|0 ～ 4,294,967,295|  
|long long|8|none (__int64 と同等ではない)|– 9,223,372,036,854,775,808 ～ 9,223,372,036,854,775,807|  
|unsigned long long|8|none (unsigned __int64 と同等ではない)|0 ～ 18,446,744,073,709,551,615|  
|enum|可変|none|この記事の「[解説](#bkmkRemarks)」を参照してください。|  
|フローティング|4|none|3.4E +/- 38 (7 桁)|  
|double|8|none|1.7E +/- 308 (15 桁)|  
|long double|double と同じ|none|double と同じ|  
|wchar_t|2|__wchar_t|0 ～ 65,535|  
  
 `__wchar_t` 型の変数には、その使用方法に応じて、ワイド文字型またはマルチバイト文字型のいずれかを指定します。 ワイド文字型の定数を指定するには、文字または文字列定数の前に `L` のプレフィックスを使用します。  
  
 `signed` と `unsigned` は、`bool` 以外の任意の整数型と組み合わせて使用できる修飾子です。 `char`、`signed char`、`unsigned char` は、オーバーロードやテンプレートのようなしくみのために用意された、3 つの異なる型であることに注意してください。  
  
 `int` 型と `unsigned``int` 型のサイズは 4 バイトです。 ただし、移植可能なコードでは `int` 型のサイズに依存しないようにしてください。言語の標準では、そのサイズは実装固有になるためです。  
  
 Visual Studio での C/C++ では、サイズが設定された整数型をサポートしています。 詳細については、「[__int8、\__int16、\__int32、\__int64](../cpp/int8-int16-int32-int64.md)」および「[整数の制限](../Topic/Integer%20Limits.md)」を参照してください。  
  
 型ごとのサイズの制限の詳細については、「[基本的な型](../cpp/fundamental-types-cpp.md)」を参照してください。  
  
 列挙型の範囲は、言語コンテキストと指定したコンパイラ フラグによって異なります。 詳細については、「[C 列挙体の宣言](../c-language/c-enumeration-declarations.md)」および「[列挙型](../cpp/enumerations-cpp.md)」を参照してください。  
  
## 関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [基本型](../cpp/fundamental-types-cpp.md)