---
title: "printf 関数の型フィールド文字 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "printf 関数, 書式指定フィールド"
  - "printf 関数, 型フィールド文字"
ms.assetid: 699cb438-cd14-402e-9f81-c7a32acc3317
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# printf 関数の型フィールド文字
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

書式指定では、`type` 文字 \(変換指定子\) により、対応する引数を文字、文字列、ポインター、整数、または浮動小数点数として解釈するかどうかを指定します。  `type` 文字だけが必須の書式指定フィールドであり、任意の省略可能なフィールドをその後に続けて指定します。  
  
 書式指定文字列に続く引数は、対応する `type` 文字と、省略可能な [size](../c-runtime-library/size-specification.md) プレフィックスに従って解釈されます。  文字型 `char` および `wchar_t` の変換は `c` または `C` を使用して指定し、1 バイト文字列とマルチバイト \(ワイド文字\) 文字列の変換は、書式設定に使用する関数に応じて `s` または `S` を使用して指定します。  `c` および `s` を使用して指定された文字引数と文字列引数は `printf` 系列の関数では `char` および `char*` として解釈され、`wprintf` 系列の関数では `wchar_t` および `wchar_t*` と解釈されます。  `C` および `S` を使用して指定された文字引数と文字列引数は `printf` 系列の関数では `wchar_t` および `wchar_t*` として解釈され、`wprintf` 系列の関数では `char` および `char*` と解釈されます。  
  
 `short`、`int`、`long`、`long long` などの整数型と、その `unsigned` のバリエーションは、`d`、`i`、`o`、`u`、`x`、および `X` を使用して指定します。  `float`、`double`、および `long double` などの浮動小数点型は、`a`、`A`、`e`、`E`、`f`、`g`、および `G` を使用して指定します。  `size` フィールド長プレフィックスで変更しない場合、既定では、整数引数は `int` 型に強制変換され、浮動小数点引数は `double` に強制変換されます。  64 ビット システム上では、`int` は 32 ビット値です。したがって、`ll` または `I64` の `size` プレフィックスを使用しない限り、64 ビット整数は出力用に書式設定される時に切り捨てられます。  `p` によって指定するポインター型では、プラットフォームの既定の長さが使用されます。  
  
> [!NOTE]
>  `C`、`S`、および `Z` の型文字と、`c` と `s` の型文字を `printf` 関数と `wprintf` 関数で使用した場合の動作は、Microsoft の拡張機能であり、ANSI 互換ではありません。  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] では型文字 `F` はサポートされていません。  
  
### printf 関数の型フィールド文字  
  
|型 \(type\) 文字|引数|\[出力形式\]|  
|-------------------|--------|--------------|  
|`c`|文字|`printf` 関数で使用する場合は 1 バイト文字を指定し、`wprintf` 関数で使用する場合はワイド文字を指定します。|  
|`C`|文字|`printf` 関数で使用する場合はワイド文字を指定し、`wprintf` 関数で使用する場合は 1 バイト文字を指定します。|  
|`d`|Integer|符号付き 10 進整数。|  
|`i`|Integer|符号付き 10 進整数。|  
|`o`|Integer|符号なし 8 進整数。|  
|`u`|Integer|符号なし 10 進整数。|  
|`x`|Integer|符号なし 16 進整数。"abcdef" を使用します。|  
|`X`|Integer|符号なし 16 進整数。"ABCDEF" を使用します。|  
|`e`|浮動小数点数|「\[ \- \]`d`**.**`dddd` e \[*符号*\]`dd[d]`」という形式を持つ符号付きの値。`d` は 1 桁の 10 進数字です。`dddd` は 1 桁以上の 10 進数字です。`dd[d]` は 2 桁または 3 桁の 10 進数字で、[出力形式](../c-runtime-library/set-output-format.md)と指数部のサイズに応じて決まります。*符号* は \+ または – です。|  
|`E`|浮動小数点数|指数部の先頭が **e** ではなく **E** であることを除いて、`e` 形式と同じです。|  
|`f`|浮動小数点数|\[ – \]`dddd`**.**`dddd` という形式の符号付きの値です。`dddd` は、1 桁以上の 10 進数を表します。  整数部の桁数は、その数値の絶対値によって決定され、小数部の桁数は要求される精度によって決定されます。|  
|`g`|浮動小数点数|符号付きの値を、書式 `f` または `e` のうち、与えられた値および精度を表現できる短い方の書式で書式設定します。  書式 `e` が使用されるのは、指数部の値が –4 より小さい場合か、`precision` 引数の値以上の場合のみです。  末尾の 0 は切り捨てられ、小数点は 1 桁以上の小数部が続く場合にのみ表示されます。|  
|`G`|浮動小数点数|指数部の先頭が **e** ではなく **E** であること \(該当する場合\) を除いて、`g` 形式と同じです。|  
|`a`|浮動小数点数|符号付き 16 進数の倍精度浮動小数点値。形式は \[−\]0x*h.hhhh* **p±**`dd` です。ここで、*h.hhhh* は仮数部の 16 進数の桁 \(小文字の英字を使用\)、`dd` は 1 桁以上の指数部です。  有効桁数は、小数点より後の桁数を指定します。|  
|`A`|浮動小数点数|符号付き 16 進数の倍精度浮動小数点値。形式は \[−\]0X*h.hhhh* **P±**`dd` です。ここで、*h.hhhh* は仮数部の 16 進数の桁 \(大文字の英字を使用\)、`dd` は 1 桁以上の指数部です。  有効桁数は、小数点より後の桁数を指定します。|  
|`n`|整数へのポインター|現時点までにストリームまたはバッファーに正常に書き込まれた文字数。  この値は、引数として指定したアドレスにある整数に格納されます。  この記事で後述する「セキュリティに関するメモ」を参照してください。|  
|`p`|\[ポインターの種類\]|引数を 16 進数字のアドレスとして表示します。|  
|`s`|文字列|`printf` 関数で使用する場合は 1 バイト文字またはマルチバイト文字の文字列を指定し、`wprintf` 関数で使用する場合はワイド文字の文字列を指定します。  文字は、最初の null 文字が現れるか、`precision` 値に達するまで表示されます。|  
|`S`|文字列|`printf` 関数で使用する場合はワイド文字の文字列を指定し、`wprintf` 関数で使用する場合は 1 バイト文字またはマルチバイト文字の文字列を指定します。  文字は、最初の null 文字が現れるか、`precision` 値に達するまで表示されます。|  
|`Z`|`ANSI_STRING` または `UNICODE_STRING` 構造体|引数として [ANSI\_STRING](http://msdn.microsoft.com/library/windows/hardware/ff540605.aspx) または [UNICODE\_STRING](http://msdn.microsoft.com/library/windows/hardware/ff564879.aspx) 構造体のアドレスを渡すと、構造体の `Buffer` フィールドがポイントしているバッファーに含まれる文字列が表示されます。  長さ修飾子のプレフィックス `w` を使用して指定する \(たとえば `%wZ`\) と、`UNICODE_STRING` 引数を指定できます。  構造体の `Length` フィールドには、文字列の長さ \(バイト単位\) を設定する必要があります。  構造体の `MaximumLength` フィールドには、バッファーの長さ \(バイト単位\) を設定する必要があります。<br /><br /> 通常、型文字 `Z` は、`dbgPrint` や `kdPrint` など、書式指定を使用するドライバー デバッグ関数でのみ使用します。|  
  
 浮動小数点の変換指定子に対応する引数が無限、不定値、または NaN の場合に書式設定される出力を次の表に示します。  
  
|値|出力|  
|-------|--------|  
|\+ 無限大|`1.#INF` *ランダムな桁*|  
|– 無限小|`–1.#INF` *ランダムな桁*|  
|不定 \(quiet NaN と同じ\)|*桁* `.#IND` *ランダムな桁*|  
|NAN|*桁* `.#NAN` *ランダムな桁*|  
  
> [!NOTE]
>  `%Z` に対応する引数の `Buffer` フィールド、あるいは `%s` または `%S` に対応する引数が null ポインターの場合は、"\(null\)" が表示されます。  
  
> [!NOTE]
>  すべての指数形式で、表示される指数部の桁数の既定値は 3 です。  [\_set\_output\_format](../c-runtime-library/set-output-format.md) 関数を使用すると、表示される桁数を 2 桁に設定できますが、指数部のサイズに応じて必要な場合は 3 桁に拡張されます。  
  
> [!IMPORTANT]
>  書式 `%n` は本質的にセキュリティが万全でないため、既定で無効になっています。  書式指定文字列に `%n` がある場合は、「[パラメーターの検証](../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。  `%n` のサポートを有効にするには、「[\_set\_printf\_count\_output](../c-runtime-library/reference/set-printf-count-output.md)」を参照してください。  
  
## 参照  
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [書式指定構文: printf 関数と wprintf 関数](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)   
 [フラグ ディレクティブ](../Topic/Flag%20Directives.md)   
 [printf 関数の文字幅指定](../c-runtime-library/printf-width-specification.md)   
 [精度指定](../c-runtime-library/precision-specification.md)   
 [サイズ指定](../c-runtime-library/size-specification.md)   
 [\_set\_output\_format](../c-runtime-library/set-output-format.md)