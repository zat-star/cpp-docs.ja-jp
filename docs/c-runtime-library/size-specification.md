---
title: "サイズ指定 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "printf 関数, 書式指定フィールド"
ms.assetid: 525dc5d8-e70a-4797-a6a0-ec504a27355c
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# サイズ指定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

書式指定において、4 番目のフィールドは変換指定子の引数の長さの修飾子です。  修飾する変換指定子に応じて、`size` フィールドの `type` フィールド プレフィクス \(`h`、`l`、`w`、`I`、`I32`、`I64`、および `ll`\) では、対応する引数の "サイズ" \(long、short、32 ビット、64 ビット、1 バイト、またはワイド文字\) を指定します。  次の表に示すように、`type` 系関数または `printf` 系関数では、これらのサイズ プレフィックスを `wprintf` 文字と共に使用して、引数の長さの解釈を指定できます。  一部の引数の型においては、`size` フィールドは省略可能です。  サイズ プレフィックスを指定しない場合: フォーマッタは整数の引数 \(たとえば、符号付きまたは符号なしの `char`、`short`、`int`、`long`、および列挙型\) を 32 ビットの `int` 型として使用します。また、浮動小数点引数は 64 ビット `double` 型として使用されます。  これは、可変引数リストの既定の引数の昇格規則と一致します。  引数の昇格の詳細については、「[省略記号と既定の引数](../misc/ellipses-and-default-arguments.md)」を参照してください。  32 ビット システムと 64 ビット システムの両方で、64 ビット整数の引数の書式設定には `ll` または `I64` のサイズ プレフィックスが含まれる必要があります。  それ以外の場合はフォーマッタの動作は未定義になります。  
  
 32 ビットおよび 64 ビットのコードでは、一部の型のサイズは異なります。  たとえば、 `size_t` は x86 用にコンパイルされたコードでは 32 ビットですが、 x64 用にコンパイルされたコードでは 64 ビットになります。  可変幅の型がプラットフォームに依存しない書式設定コードを作成するには、可変幅引数の長さの修飾子を使用します。  または、64 ビットの引数の長さの修飾子を使用して、可変幅引数の型を明示的に 64 ビットに昇格させます。  Microsoft 固有の `I` 引数の長さの修飾子は、可変幅の整数の引数を処理します。  
  
> [!NOTE]
>  `I`、`I32`、および `I64` の長さの修飾子のプレフィックスは Microsoft 拡張機能であり、ANSI 互換姓がありません。  `h` プレフィックス \(`char` 型のデータと共に使用する場合\)、`w` プレフィックス \(`wchar_t` 型のデータと共に使用する場合\)、および `l` プレフィックス \(`double` 型のデータと共に使用する場合\) は Microsoft 拡張機能です。  `hh`、`j`、`z`、および `t` の長さのプレフィックスはサポートされていません。  
  
### printf および wprintf の書式型指定子のサイズ プレフィックス  
  
|指定する型|プリフィックス|型指定子|  
|-----------|-------------|----------|  
|`long int`|`l` \(小文字の L\)|`d`、`i`、`o`、`x`、または `X`|  
|`long unsigned int`|`l`|`o`、`u`、`x`、または `X`|  
|`long long`|`ll`|`d`、`i`、`o`、`x`、または `X`|  
|`short int`|`h`|`d`、`i`、`o`、`x`、または `X`|  
|`short unsigned int`|`h`|`o`、`u`、`x`、または `X`|  
|`__int32`|`I32`|`d`、`i`、`o`、`x`、または `X`|  
|`unsigned __int32`|`I32`|`o`、`u`、`x`、または `X`|  
|`__int64`|`I64`|`d`、`i`、`o`、`x`、または `X`|  
|`unsigned __int64`|`I64`|`o`、`u`、`x`、または `X`|  
|`ptrdiff_t` \(つまり、32 ビット プラットフォーム上では `__int32`、64 ビット プラットフォーム上では `__int64`\)|`I`|`d`、`i`、`o`、`x`、または `X`|  
|`size_t` \(つまり、32 ビット プラットフォーム上では `unsigned __int32`、64 ビット プラットフォーム上では `unsigned __int64`\)|`I`|`o`、`u`、`x`、または `X`|  
|`long double` \([!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] では、`long double` は別個の型ですが、これには `double` と同じ内部表現があります\)。|`l` または `L`|`a`、`A`、`e`、`E`、`f`、`g`、または `G`|  
|1 バイト文字と `printf` 関数および `wprintf` 関数  \(`hc` または `hC` の型指定子は、`c` 関数の `printf` および `C` 関数の `wprintf` と同じ意味です\)。|`h`|`c` または `C`|  
|ワイド文字と `printf` 関数および `wprintf` 関数  \(`lc`、`lC`、`wc`、または `wC` の型指定子は、`C` 関数の `printf` および `c` 関数の `wprintf` と同じ意味です\)。|`l` または `w`|`c` または `C`|  
|1 バイト文字の文字列と `printf` 関数および `wprintf` 関数  \(`hs` または `hS` の型指定子は、`s` 関数の `printf` および `S` 関数の `wprintf` と同じ意味です\)。|`h`|`s`、`S`、または `Z`|  
|ワイド文字の文字列と `printf` 関数および `wprintf` 関数  \(`ls`、`lS`、`ws`、または `wS` の型指定子は、`S` 関数の `printf` および `s` 関数の `wprintf` と同じ意味です\)。|`l` または `w`|`s`、`S`、または `Z`|  
  
## 参照  
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [書式指定構文: printf 関数と wprintf 関数](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)   
 [フラグ ディレクティブ](../Topic/Flag%20Directives.md)   
 [printf 関数の文字幅指定](../c-runtime-library/printf-width-specification.md)   
 [精度指定](../c-runtime-library/precision-specification.md)   
 [printf 関数の型フィールド文字](../c-runtime-library/printf-type-field-characters.md)