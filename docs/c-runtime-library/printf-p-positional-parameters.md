---
title: "printf_p の位置指定パラメーター | Microsoft Docs"
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
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_printf_p 関数, 位置指定パラメーター"
  - "printf_p 関数, 位置指定パラメーター"
ms.assetid: beb4fd85-a7aa-4665-9085-2c907a5b9ab0
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# printf_p の位置指定パラメーター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

位置指定パラメータを使用すると、書式指定文字列のフィールドに代入する引数を番号で指定することができます。  次の位置指定パラメーター `printf` 関数を使用できます。  
  
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)  
 [\_printf\_p、\_printf\_p\_l、\_wprintf\_p、\_wprintf\_p\_l](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)  
  
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)  
 [\_sprintf\_p、\_sprintf\_p\_l、\_swprintf\_p、\_swprintf\_p\_l](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)  
  
 [\_cprintf、\_cprintf\_l、\_cwprintf、\_cwprintf\_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)  
 [\_cprintf\_p、\_cprintf\_p\_l、\_cwprintf\_p、\_cwprintf\_p\_l](../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)  
  
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)  
 [\_fprintf\_p、\_fprintf\_p\_l、\_fwprintf\_p、\_fwprintf\_p\_l](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)  
  
 [vprintf、\_vprintf\_l、vwprintf、\_vwprintf\_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)  
 [\_vprintf\_p、\_vprintf\_p\_l、\_vwprintf\_p、\_vwprintf\_p\_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)  
  
 [vfprintf、\_vfprintf\_l、vfwprintf、\_vfwprintf\_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)  
 [\_vfprintf\_p、\_vfprintf\_p\_l、\_vfwprintf\_p、\_vfwprintf\_p\_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)  
  
 [vsprintf、\_vsprintf\_l、vswprintf、\_vswprintf\_l、\_\_vswprintf\_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)  
 [\_vsprintf\_p、\_vsprintf\_p\_l、\_vswprintf\_p、\_vswprintf\_p\_l](../Topic/_vsprintf_p,%20_vsprintf_p_l,%20_vswprintf_p,%20_vswprintf_p_l.md)  
  
## 位置指定パラメーターの指定  
  
##### パラメーターのインデックス作成  
 既定では、位置指定関数の動作は、位置指定の書式設定がない場合は、位置指定でないものと同じです。  位置指定パラメーターは、書式設定 "`%m$x`" で指定され、`m` はパラメーター一覧でのパラメーターの位置を示す数値の序数を意味し、前の書式指定文字列と  `x` は、`printf` 関数で指定した型フィールドの文字型を意味します。  一覧内のパラメーターは、一覧の最初の要素の値 1 からインデックス化されています。  型フィールドに関する詳細については、「[printf 関数の型フィールド文字](../c-runtime-library/printf-type-field-characters.md)」を参照してください。  
  
 この動作の例については、次を参照してください。  
  
```  
_printf_p("%1$s %2$s", "November", "10");  
```  
  
 は次を印刷します。  
  
```  
November 10  
```  
  
 使用する数値の順序は、指定された引数の順序と一致している必要はありません。  したがって、次の例も有効です。  
  
```  
_printf_p("%2$s %1$s", "November", "10");  
```  
  
 は次を印刷します。  
  
```  
10 November  
```  
  
 パラメーターは、従来の書式指定文字列とは異なり、書式設定中に複数回使用できるため、  
  
```  
_printf_p("%1$d times %1$d is %2$d", 10, 100);  
```  
  
 は次を印刷します。  
  
```  
10 times 10 is 100  
```  
  
 ただし、書式指定文字列のどこかに、すべての引数を必ず 1 回以上使用する必要があります。  
  
 1 つの書式指定文字列で使用できる位置指定パラメータの最大数は、`_ARGMAX` で指定されます。  
  
##### 幅と精度  
 幅または精度を引数から決定することを指定するために \* 記号を使用すると、幅または精度の値の位置は \* 記号の直後になります。  次に例を示します。  
  
```  
_printf_p("%1$*2$s","Hello", 10);  
```  
  
 または  
  
```  
_printf_p("%2$*1$s",10, "Hello");  
```  
  
##### 位置指定引数とそれ以外の引数の混在  
 同一の書式指定文字列では、位置指定パラメーターと位置指定以外のパラメーターは混在できません。  ただし、位置指定以外のパラメーターを含む書式指定文字列では、`printf_p` および関連する関数は、位置指定以外のパラメーターを引き続きサポートします。  
  
## 使用例  
  
```  
// positional_args.c  
// Positional arguments allow the specification of the order  
// in which arguments are consumed in a formatting string.  
  
#include <stdio.h>  
  
int main(int argc, char *argv[])  
{  
    int     i = 1,  
            j = 2,  
            k = 3;  
    double  x = 0.1,  
            y = 0.2,  
            z = 0.3;  
    char    *s1 = "abc",  
            *s2 = "def",  
            *s3 = "ghi";  
  
    // If positional arguments are unspecified,  
    // normal input order is used.  
    _printf_p("%d %d %d\n", i, j, k);  
  
    // Positional args are numbers indicating the  
    // argument enclosed in curly braces.  
    _printf_p("%3$d %1$d %2$d\n", i, j, k);  
  
    // The same positional argument may be reused.  
    _printf_p("%1$d %2$d %1$d\n", i, j);  
  
    _printf_p("%1$s %2$s %3$s\n", s1, s2, s3);  
  
    _printf_p("%3$s %1$s %2$s\n", s1, s2, s3);  
}  
```  
  
  **1 2 3**  
**3 1 2**  
**1 2 1**  
**abc def ghi**  
**ghi abc def**   
## 参照  
 [printf 関数の型フィールド文字](../c-runtime-library/printf-type-field-characters.md)   
 [printf 関数の文字幅指定](../c-runtime-library/printf-width-specification.md)   
 [精度指定](../c-runtime-library/precision-specification.md)