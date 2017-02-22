---
title: "to 系関数 | Microsoft Docs"
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
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "To"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "case, 変換"
  - "文字, 変換"
  - "小文字, 変換 (文字列を)"
  - "文字列変換, case"
  - "文字列変換, 別の文字への"
  - "関数への"
  - "大文字, 変換 (文字列を)"
ms.assetid: f636a4c6-8c9f-4be2-baac-064f9dbae300
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# to 系関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**宛先** 関数および関連するマクロの各段階では、別の文字に単一の文字を変換します。  
  
|||  
|-|-|  
|[\_\_toascii](../c-runtime-library/reference/toascii-toascii.md)|[toupper、\_toupper、towupper](../Topic/toupper,%20_toupper,%20towupper,%20_toupper_l,%20_towupper_l.md)|  
|[tolower、\_tolower、towlower](../Topic/tolower,%20_tolower,%20towlower,%20_tolower_l,%20_towlower_l.md)||  
  
## 解説  
 **宛先** 関数とマクロ変換は次のとおりです。  
  
|ルーチン|マクロ|説明|  
|----------|---------|--------|  
|`__toascii`|`__toascii`|ASCII 文字と `c` を変換します。|  
|`tolower`|`tolower`|必要に応じて `c` を小文字に変換します。|  
|`_tolower`|`_tolower`|`c` を小文字に変換します。|  
|`towlower`|なし。|対応するワイド文字の `c` を小文字に変換します。|  
|`toupper`|`toupper`|必要に応じて `c` を大文字に変換します。|  
|`_toupper`|`_toupper`|`c` を大文字に変換します。|  
|`towupper`|なし。|対応するワイド文字の大文字に c を変換します。|  
  
 マクロは、定義されている **宛先** ルーチンの関数のバージョンを使用するには、マクロ定義を `#undef` のディレクティブを削除するか、CTYPE.H.を含めないでください。  \/Za コンパイラ オプションを使用すると、コンパイラは `toupper` または `tolower`の関数のバージョンを使用します。  `toupper` と `tolower` 関数の宣言は、STDLIB.H にあります。  
  
 `__toascii` ルーチンは 0 に変換された値は ASCII 文字セットの文字を表すために、すべて `c` の下位 7 ビットを設定しますが、  `c` が既に ASCII 文字を表す場合、`c` は変更されません。  
  
 `tolower` と `toupper` :ルーチン  
  
-   現在のロケールの `LC_CTYPE` のカテゴリに依存してください。\(`tolower` は `isupper` と `toupper` の呼び出し `islower`を呼び出します\)。  
  
-   `c` は現在のロケールの適切なケースに変換可能な文字を表し、一方のケースは、ロケールの場合 `c` を変換します。  それ以外の場合は `c` は変更されません。  
  
 `_tolower` と `_toupper` :ルーチン  
  
-   `tolower` のロケールに依存しない、より高速なバージョンと **toupper.**です  
  
-   **isascii\(** `c`\#\#\#\) が **isupper\(**`c`\#\#\#\) または **islower\(**`c`\#\#\#\)、それぞれ 0 以外のな場合にのみ使用することができます。  
  
-   `c` が変換の適切な場合の ASCII 文字である結果が定義されていません。  
  
 `towlower` と `towupper` 関数は次の両方の条件に 0 以外のの場合にのみ `c` の変換されたコピーを返します。  それ以外の場合は `c` は変更されません。  
  
-   `c` は、どの `iswupper` または **iswlower,** の場合、0 以外のか\) は、適切なケースのワイド文字です \(つまり。  
  
-   それぞれの `iswlower` または **iswupper,** の場合、0 以外のか\) ターゲット例の対応するワイド文字です \(つまり。  
  
## 使用例  
  
```  
// crt_toupper.c  
/* This program uses toupper and tolower to  
 * analyze all characters between 0x0 and 0x7F. It also  
 * applies _toupper and _tolower to any code in this  
 * range for which these functions make sense.  
 */  
  
#include <ctype.h>  
#include <string.h>  
  
char msg[] = "Some of THESE letters are Capitals.";  
char *p;  
  
int main( void )  
{  
   printf( "%s\n", msg );  
  
   /* Reverse case of message. */  
   for( p = msg; p < msg + strlen( msg ); p++ )  
   {  
      if( islower( *p ) )  
         putchar( _toupper( *p ) );  
      else if( isupper( *p ) )  
         putchar( _tolower( *p ) );  
      else  
         putchar( *p );  
   }  
}  
```  
  
  **これらの文字には、大文字を使用します。**  
**これらの文字には、大文字を使用します。**   
## 参照  
 [データ変換](../c-runtime-library/data-conversion.md)   
 [ロケール](../c-runtime-library/locale.md)   
 [is、isw 系ルーチン](../c-runtime-library/is-isw-routines.md)